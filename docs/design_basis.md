# 设计依据

本轮按 [Issue #3](https://github.com/kazecode666/J16-MBDL4-Module/issues/3) 最新正文完成原理图，并按 PR #4 评论重排为单页 A3 V0.2。已有资料文件与关键页码见[参考索引](reference_index.md)，原始接口事实见[接口证据](interface_evidence.md)。

## 用户确定的边界

- 一块专用接口板，3 颗 SN74LXC8T245PWR。A 侧为控制器 3.3 V 域，B 侧为驱动板 5 V 域。
- U1 转换六路互补 PWM，A→B。U2 转换 RELCON、ENCON、F_Reset，A→B。U3 转换 QEPA、QEPB、QEPZ、ERRI、ERRU，B→A。
- 14 路功能信号和 2 路使能控制分配具体 J16 GPIO。J15 继续专用于 AN9238。
- 接口板仅经 J16 与控制器插接。3.3 V 与 5 V 使用独立电源网，数字地共参考，每颗芯片本地去耦。
- 输出默认禁止。PWM 停机时反馈继续工作。处理 FPGA 未供电时的反灌，清故障与 PWM 放行独立。
- 本板范围为数字接口、电平转换及所需偏置。ADC、功率级、编码器差分接收器、物理限位开关和控制算法扩展在本任务范围之外。

## 接口与器件依据

- AXU5EVB-E 手册 p41 的 J16 表与底板原理图 p18、核心板原理图 p4 共同确定端子、网络、球号及 Bank。保留 J45/J46 历史别名的球号对照。
- MBDL4 手册 p11 表 2-1 确定数字口针号，图 2-3 确定观察方向。按该图观察，1 脚在右上、2 脚在右下，上排由右至左为奇数，下排由右至左为偶数。连接器符号与线缆按端子号对应。
- MBDL4 手册 p20–22 和原理图 p1 提供 ENCON、RELCON、故障反馈、复位及编码器电路依据。
- TI 手册 p3 核验 PW/TSSOP-24 引脚。1 为 VCCA，23、24 均为 VCCB，11–13 为 GND。新器件使用 A1–A8/B1–B8 通道编号。
- TI 手册 p19–22 给出 OE、DIR 和掉电隔离行为，p24 给出去耦建议。封装图 PW0024A p1–3 提供外形、焊盘与钢网尺寸。

## 当前实际连接

U1、U2 的 DIR 接 VCCA，两个 OE 独立控制并有外部上拉。U3 的 DIR 接 GND，VCCA 由 CTRL_EN 经 470 Ω 供给，五路 A 输出经 33 Ω 串联至 FPGA。反馈有效条件保持独立于 PWM 停机。完整供电、使能、必要偏置与未用输入处理以[原理图说明](schematic_v0.1.md)和可编辑工程为准。

[连接表](../hardware/v0.1/pin_connections.csv)记录 J16 针号/FPGA 球号、转换器真实引脚和 MBDL4 针号，[BOM](../hardware/v0.1/bom.csv)记录所用元件。原理图审查集中于[当前电气事项](open_questions.md)。
