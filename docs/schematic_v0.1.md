# 总原理图 V0.2 审查稿

本轮在 [PR #4](https://github.com/kazecode666/J16-MBDL4-Module/pull/4) 的现有工程内，将四页重排为一张可编辑的 A3 横向总图。工程沿用现有项目目录，工程文件及图内版本更新为 V0.2。当前关键电气审查停在 PWM 驱动问题，PCB 阶段等待该项闭合。

## 实际电路

- J1 对接 AXU5EVB-E J16，2 脚供 5 V，39/40 脚供接口 3.3 V，1/37/38 脚为 GND。J2 对接 MBDL4 数字口，25/26 脚为 GND。接口针号和 FPGA 球号沿用既有手册。
- U1/U2/U3 均为 SN74LXC8T245PWR。23/24 脚接 5 V，11/12/13 脚接 GND。U1/U2 的 VCCA.1 接接口 3.3 V。U3 的 VCCA.1 由 CTRL_EN_A 经 R35 470 Ω 供给，C7 100 nF 位于该电源脚旁。
- 每个转换器的三个电源脚各配置 100 nF。入口 C10/C11 为 1 µF。U1/U2 DIR 接 VCCA，U3 DIR 接 GND。未用输入接 GND，相应输出标 NC。
- PWM_EN_A 经 R26/Q1 控制 U1 /OE，CTRL_EN_A 经 R28/Q2 控制 U2 /OE。各使能端有 1 kΩ 下拉，各 /OE 有 4.7 kΩ 上拉。两组电阻、三极管及局部实线连接已集中到所属 OE 电路。
- PWM A/B 端分别保留 100 kΩ/10 kΩ 下拉。RELCON、ENCON 两侧各有 10 kΩ 下拉，F_RESET_A 有 10 kΩ 下拉。F_RESET_B 高阻默认值由原驱动板 R106 5.1 kΩ 上拉提供。
- 五路反馈从 U3 A1–A5 经 R30–R34 33 Ω 串联至 FPGA，B1–B5 输入各有 10 kΩ 下拉。U3 /OE 经 R25 0 Ω 接 GND。本版以 U3 自身的断电隔离处理核心板关闭时的反馈注入，采用 GPIO 供给 A 侧电源。原 U4、D1、C12 及开漏上拉结构已由这一接法替换。

## 反馈条件与初始化

额定使用条件采用 VCCO 3.0–3.4 V、LVCMOS33、CTRL_EN DRIVE 12 mA，反馈脚关闭内部上下拉。每路周期频率上限为 100 kHz，A/B 相邻有效边沿间隔至少 2 µs，A 侧每路总负载不大于 50 pF，FPGA 同步时钟至少 50 MHz。这些是本板选定的接口条件。现有手册没有给出实际编码器的 PPR 和最高转速。

按 GPIO VOH 最低 2.6 V、A 侧总电流预算 0.25 mA、R35 最大 474.7 Ω、U3 低负载 VOH 再扣 0.1 V 计算，FPGA 端高电平约 2.38 V。相对 VIH 2.0 V 的裕量约 0.38 V。33 Ω 上 15 µA 漏电压降约 0.5 mV。动态电流预算使用典型 Cpd 加工程余量估算。100 nF 去耦承担五路同时充电的瞬态，五路各 50 pF 的电荷步进对应约 8.5 mV 电源跌落。时序使用 2.3–2.7 V A 侧工作区间的器件参数并给接口传播留 0.1 µs 预算，33 Ω 与 50 pF 的额外 RC 约 1.65 ns。该预算需要在后续控制集成中落实负载和输入边沿条件。[TI SN74LXC8T245 p7/p12/p15/p19–22](https://www.ti.com/lit/ds/symlink/sn74lxc8t245.pdf) [AMD PL I/O 电平](https://docs.amd.com/r/en-US/ds925-zynq-ultrascale-plus/PL-I/O-Levels)

启动时先保持 PWM_EN=0、RELCON=0、ENCON=0，预置 F_RESET=1，再置 CTRL_EN=1，等待 1 ms 后使用反馈。PWM 停机时保留 CTRL_EN=1。CTRL_EN=0 时反馈读数无效。R35/C7 的标称时间常数为 47 µs，1 ms 约为 21 个时间常数。最坏 3.4 V 启动时，R35 充电电流、1 kΩ 下拉和 Q2 基极电流合计约 11.1 mA。

## PWM 关键阻塞

MBDL4 原理图 p1 每路为 300 Ω 串联、1 kΩ 跨光耦输入，六路共用 Q7 下拉的 CATH。输入电流按 IF=(VOH−VF−VCATH)/Rseries−VF/Rparallel 计算。

- 5 V、VF=2.1 V、CATH=0 V 的典型计算为 7.57 mA。
- 即便理想 5 V 输出，VF=2.4 V、CATH=0.2 V 时标称为 5.60 mA，计入原电阻 ±5% 后约 5.09 mA。
- TI 的 VOH=3.8 V 对应 4.5 V 供电、32 mA 测试条件。代入该保守组合得到 1.6 mA，这是边界计算。当前电路实际输出电压没有经过实物测量。

CA-IS3211 推荐导通电流为 7–16 mA，开关参数也有对应电流条件。4 mA 是开启阈值最大值，不能据此代替完整时序条件。当前 5 V 直驱的保证条件没有闭合。[CA-IS3211 §6.3/6.9/6.10/8.4](https://e.chipanalog.com/Public/Uploads/uploadfile/files/20250123/CAIS3211datasheetVersion1.09en20250122.pdf)

已审查约 7 V 升压和独立输出级候选。该方向还须让输出级受 ENCON、ERRI、ERRU 共同限定，保持原板 Q7 的故障关断关系。原图 Q7 仅标 J3Y，现有资料缺少可确认的厂商、档位及温区，CATH 的最大带载电位没有保证依据。候选 UCC27524A 的 7.5 Ω 最大上拉电阻条款对应 12 V，不能直接用于 7 V 的最坏值证明。升压电源还须计入基准、分压、纹波和输出级压降。因此候选电路尚未写入工程。[UCC27524A p6](https://www.ti.com/lit/ds/symlink/ucc27524a.pdf) [TPS61040 p5](https://www.ti.com/lit/ds/symlink/tps61040.pdf)

## 实际检查与停止点

原生严格 ERC 的完整返回值及网表核对统计见交付目录的检查结果。独立只读审查已实际查看导出的单页 PNG、原板输入和使能图，以及实际网表。两轮审查均保留同一 PWM 关键问题，按本轮结束条件保存成果并停止该项迭代。PCB 电气前提尚未满足。

下一步需用户选择是否把 MBDL4 六路输入阻值及共 CATH 下拉回路调整纳入设计，或保持驱动板固定并取得厂家数字口的输入电压、电流、温区和 CATH 负载包络。手册 TLP5701 与原图 IS3211 的差异也应由这一电气条件一并落实。
