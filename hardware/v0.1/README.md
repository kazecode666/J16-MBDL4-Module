# V0.3 兼容接口板样机

使用嘉立创 EDA 专业版打开[可编辑工程](<J16-MBDL4/J16-MBDL4 V0.3.eprj3>)，保留整个 J16-MBDL4 目录。总原理图_A3 为单页横向总图，PCB1 为同工程中的首版双层板。

- [单页 A3 PNG](review/schematic_A3.png)、[PDF 审阅版](review/schematic_A3.pdf)、[原生矢量 SVG](review/schematic_A3.svg)
- [PCB 顶面](review/pcb_top.png)、[底面](review/pcb_bottom.png)
- [3D 顶侧预览](review/pcb_3d_top.png)、[底侧预览](review/pcb_3d_bottom.png)
- [引脚连接表](pin_connections.csv)
- [51 件 BOM](bom.csv)
- [51件厂装BOM、CPL、DNP及双面装配图](pcba/)
- [实际 ERC、DRC 与逐端子检查结果](review/check_results.json)
- [人工审核用 Gerber 与钻孔 ZIP](review/J16-MBDL4_V0.3_Gerber.zip)
- [电路与初始化说明](../../docs/schematic_v0.1.md)
- [25项统一审查清单](../../docs/review_checklist.md)
- [原生BRD尺寸核对与装配叠合图](review/assembly_overlay.png)

本板设计尺寸为60 × 55 mm，双层FR4、1.6 mm标称板厚、约1oz铜。J1采用连兴旺254PM-2x20P-V/C53202170无凸键母座，底装180°，PCB顶视1脚左下、2脚左上。J2为Hanxia HX JN2.54-2x13P ZZ H8.9无扳扣简牛，顶装、红边接1脚，两连接器孔径均1.02mm。J16位于载板上边，子板朝板外伸出，双子板X间距已核对。实际插合及支撑留首板安装确认。

新版ZIP的Drill_PTH_Through.DRL包含全部108个通孔及过孔，CAM导入这一合并文件一次。Drill_PTH_Through_Via.DRL为其中42个过孔的分类参考。PDF由原生4096像素PNG等比排入A3，保留可编辑工程用于电路修改。

本轮接续e4dc6c44，按最新决定采用C53202170。两款候选的国内可贴库、厂图与尺寸核对见J1选型说明，J16护框内腔、有效针长和止挡的实际配合留首板断电试插。C10/C11移至y13.5mm，Q1/Q2移至y13.8mm，R27/R29移至y13.6mm，并完成受影响局部布线与铺铜。J1顶面焊盘/阻焊开窗至全部49件SMT本体/焊盘/开窗的最小净距为5.22838mm。[J1选型及装配说明](pcba/j1_selection.md)

本轮ERC为0错误、3条J1/Q1/Q2封装标题属性警告，原因及兼容性依据见25项清单。J1使用按厂图修正孔径、本体并保留本板编号的本地底装封装，订单需人工确认该封装名及方向。DRC与飞线均0。设计为51个元件，生产BOM/CPL各51行，全51件装配范围均要求厂家供料和焊接，DNP表仅含表头。新版Gerber的CAM复核状态、网络映射及输出一致性见[检查记录](review/check_results.json)。实际插合与电气性能留首板无功率检查。

当前生产目标为嘉立创完成底面J1、顶面J2及49件顶面SMT。成品单板60×55mm、双层FR4、1.6mm、1oz，建议绿油白字、无铅喷锡。按本单双面混合装配审核，标准型70×70mm下限所需工艺拼板或可拆工艺框、J1/J2代焊及钢网工艺由厂家确定。仅在厂家明确拒绝J1代焊后启用用户自购后焊备选。[PCBA检查](pcba/)

PDF使用原生4096px PNG等比排入A3，原生SVG另行交付。3D预览由MCP导出的实际OBJ模型离线渲染，显示颜色供观察，机械尺寸按厂家图。两张PCB层图均从顶面坐标观察，制造层预览与新版Gerber的复核状态见[检查记录](review/check_results.json)。

可探测位置使用已有顶层焊盘与连接器焊点。3.3 V 为 C10.1，5 V 为 C11.1，GND 为 C10.2，OE_PWM_N 为 R13.2，OE_CTRL_N 为 R19.2，F_RESET_B 为 J2.9，ERRI_B/ERRU_B 为 J2.19/20。测量参考接控制侧 GND。

三颗转换器正常 3.3 V/5 V 供电，U1 的 PWM_EN 独立，U2/U3 共用 CTRL_EN。PWM 带载、反馈边沿、核心独立掉电等[实机项目](../../docs/open_questions.md)尚未测量。

同目录原有四张分区 PNG 对应上一版 V0.1，仅用于查看此前图面。当前审查使用本页链接的单页总图。
