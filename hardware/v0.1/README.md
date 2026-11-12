# V0.3 兼容接口板样机

使用嘉立创 EDA 专业版打开[可编辑工程](<J16-MBDL4/J16-MBDL4 V0.3.eprj3>)，保留整个 J16-MBDL4 目录。总原理图_A3 为单页横向总图，PCB1 为同工程中的首版双层板。

- [单页 A3 PNG](review/schematic_A3.png)、[PDF 审阅版](review/schematic_A3.pdf)、[原生矢量 SVG](review/schematic_A3.svg)
- [PCB 顶面](review/pcb_top.png)、[底面](review/pcb_bottom.png)
- [3D 顶侧预览](review/pcb_3d_top.png)、[底侧预览](review/pcb_3d_bottom.png)
- [引脚连接表](pin_connections.csv)
- [51 件 BOM](bom.csv)
- [实际 ERC、DRC 与逐端子检查结果](review/check_results.json)
- [人工审核用 Gerber 与钻孔 ZIP](review/J16-MBDL4_V0.3_Gerber.zip)
- [电路与初始化说明](../../docs/schematic_v0.1.md)

本板设计尺寸为 60 × 55 mm，双层 FR4、1.6 mm 标称板厚。J1 底装，工程内封装已保存底装所需的局部 Y 镜像针位，顶视 1 脚为左下方焊盘。J2 顶装，按端子号与 MBDL4 线缆一一对应，红边接 1 脚。叠合净高、散热器避让及固定方式仍需装配核对。

原生 ZIP 的 Drill_PTH_Through.DRL 已包含全部 106 个通孔及过孔，人工 CAM 导入这一合并文件一次。Drill_PTH_Through_Via.DRL 为其中 40 个过孔的分类参考。PDF 由原生 4096 像素 PNG 等比排入 A3，保留可编辑工程用于电路修改。

本轮基于用户手工整理的 A3 图面，将去耦电容与芯片拉开间距，各电容及 C10/C11 分别使用独立电源和地支路。同一芯片上相同电源的引脚局部合并，使用 +3V3_A、+5V_B 电源网络标识。U3 DIR 地符号朝上，下拉电阻与芯片接地引脚采用局部合并，复位和故障注释完整保留。SVG 转 PDF 时标题栏文字基线发生错位，审阅 PDF 采用上面的原生 PNG，同时交付原生 SVG。PCB 已同步原理图并重新执行 ERC/DRC。布局、布线、铺铜和丝印的几何与输入工程一致，现有正反面及 3D 预览继续对应当前板。

可探测位置使用已有顶层焊盘与连接器焊点。3.3 V 为 C10.1，5 V 为 C11.1，GND 为 C10.2，OE_PWM_N 为 R13.2，OE_CTRL_N 为 R19.2，F_RESET_B 为 J2.9，ERRI_B/ERRU_B 为 J2.19/20。测量参考接控制侧 GND。

三颗转换器正常 3.3 V/5 V 供电，U1 的 PWM_EN 独立，U2/U3 共用 CTRL_EN。PWM 带载、反馈边沿、核心独立掉电等[实机项目](../../docs/open_questions.md)尚未测量。

同目录原有四张分区 PNG 对应上一版 V0.1，仅用于查看此前图面。当前审查使用本页链接的单页总图。
