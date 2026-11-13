# V0.3 兼容接口板样机

使用嘉立创 EDA 专业版打开[可编辑工程](<J16-MBDL4/J16-MBDL4 V0.3.eprj3>)，保留整个 J16-MBDL4 目录。总原理图_A3 为单页横向总图，PCB1 为同工程中的首版双层板。

- [单页 A3 PNG](review/schematic_A3.png)、[PDF 审阅版](review/schematic_A3.pdf)、[原生矢量 SVG](review/schematic_A3.svg)
- [PCB 顶面](review/pcb_top.png)、[底面](review/pcb_bottom.png)
- [3D 顶侧预览](review/pcb_3d_top.png)、[底侧预览](review/pcb_3d_bottom.png)
- [引脚连接表](pin_connections.csv)
- [51 件 BOM](bom.csv)
- [全料PCBA BOM、CPL、双面装配图及就绪检查](pcba/)
- [实际 ERC、DRC 与逐端子检查结果](review/check_results.json)
- [人工审核用 Gerber 与钻孔 ZIP](review/J16-MBDL4_V0.3_Gerber.zip)
- [电路与初始化说明](../../docs/schematic_v0.1.md)
- [25项统一审查清单](../../docs/review_checklist.md)
- [原生BRD尺寸核对与装配叠合图](review/assembly_overlay.png)

本板设计尺寸为60 × 55 mm，双层FR4、1.6 mm标称板厚、约1oz铜。J1采用Sullins SFH11-PBPC-D20-ST-BK实体带键母座，底装180°，PCB顶视1脚左下、2脚左上。J2为Hanxia HX JN2.54-2x13P ZZ H8.9无扳扣简牛，顶装、红边接1脚，两连接器孔径均1.02mm。J16位于载板上边，子板朝板外伸出，双子板X间距已核对。实际插合及支撑留首板安装确认。

原生 ZIP 的 Drill_PTH_Through.DRL 已包含全部 106 个通孔及过孔，人工 CAM 导入这一合并文件一次。Drill_PTH_Through_Via.DRL 为其中 40 个过孔的分类参考。PDF 由原生 4096 像素 PNG 等比排入 A3，保留可编辑工程用于电路修改。

本轮在b004404和用户保存的当前工程上读取原生AXU BRD及MBDL4库，核对40/26针与键侧，生成带尺寸叠合图。J1盘径增至1.60mm、孔仍1.02mm；六段逻辑线由10改8mil，中心线及全部元件位置保留。Q1/Q2改为onsemi MMBT3904LT1G/C81464，复用经原厂尺寸核对的焊盘。C10/C11位置及用户A3分区保留。所有受影响图面及制造文件已重导。

现有电气检查记录为ERC 0错误、2条封装标题属性警告，原因及兼容性依据见25项清单。DRC与飞线均0，232焊盘映射差异0。最终六图CAM实际查看了两面铜/阻焊、顶焊膏、丝印、板框及钻孔。本轮通过MCP导出原生BOM/CPL并核对当前51个元件，物料、坐标、安装面和旋转差异0。全料PCBA仍需厂家供货及工艺审核，实际插合与电气性能留首板无功率检查。

当前要求为嘉立创全料PCBA，全部51件由厂家焊接。成品单板60×55mm、双层FR4、1.6mm、1oz，建议绿油白字、无铅喷锡。标准型最小生产外形70×70mm，工艺拼板/可拆工艺框、钢网、顶面SMT加双面插件流程及底装J1供货均待厂家审核。审核数据与待办详见[PCBA检查](pcba/)。

PDF使用原生4096px PNG等比排入A3，原生SVG另行交付。原生光追接口在本环境超时，3D预览由MCP导出的实际OBJ模型离线渲染，显示颜色供观察，机械尺寸按厂家图。两张PCB层图均从顶面坐标观察。实际Gerber已独立解析预览，见[制造层预览](review/gerber_preview.png)。

可探测位置使用已有顶层焊盘与连接器焊点。3.3 V 为 C10.1，5 V 为 C11.1，GND 为 C10.2，OE_PWM_N 为 R13.2，OE_CTRL_N 为 R19.2，F_RESET_B 为 J2.9，ERRI_B/ERRU_B 为 J2.19/20。测量参考接控制侧 GND。

三颗转换器正常 3.3 V/5 V 供电，U1 的 PWM_EN 独立，U2/U3 共用 CTRL_EN。PWM 带载、反馈边沿、核心独立掉电等[实机项目](../../docs/open_questions.md)尚未测量。

同目录原有四张分区 PNG 对应上一版 V0.1，仅用于查看此前图面。当前审查使用本页链接的单页总图。
