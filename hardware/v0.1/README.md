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
- [25项统一审查清单](../../docs/review_checklist.md)
- [原生BRD尺寸核对与装配叠合图](review/assembly_overlay.png)

本板设计尺寸为60 × 55 mm，双层FR4、1.6 mm标称板厚、约1oz铜。J1改用Sullins SFH11-PBPC-D20-ST-BK实体带键母座，底装180°，保留厂家库针号，PCB顶视1脚左下、2脚左上。J2为Hanxia HX JN2.54-2x13P ZZ H8.9无扳扣简牛，顶装、红边接1脚，两连接器孔径均1.02mm。实际插合、AN9238同时安装的空间及支撑仍待检查，细项见清单。

原生 ZIP 的 Drill_PTH_Through.DRL 已包含全部 106 个通孔及过孔，人工 CAM 导入这一合并文件一次。Drill_PTH_Through_Via.DRL 为其中 40 个过孔的分类参考。PDF 由原生 4096 像素 PNG 等比排入 A3，保留可编辑工程用于电路修改。

本轮在b004404和用户保存的当前工程上读取原生AXU BRD及MBDL4库，核对40/26针与键侧，生成带尺寸叠合图。J1盘径增至1.60mm、孔仍1.02mm；六段逻辑线由10改8mil，中心线及全部元件位置保留。Q1/Q2改为onsemi MMBT3904LT1G/C81464，复用经原厂尺寸核对的焊盘。C10/C11位置及用户A3分区保留。所有受影响图面及制造文件已重导。

当前ERC为0错误、2条封装标题属性警告，原因及兼容性依据见25项清单。DRC与飞线均0，232焊盘映射差异0。最终六图CAM实际查看了两面铜/阻焊、顶焊膏、丝印、板框及钻孔。完整插合高度、内腔与散热器/线缆空间仍待尺寸依据，当前交付供人工审核。

本轮生产建议为裸板、60×55mm、双层FR4、1.6mm、1oz、绿油白字、无铅喷锡，后续人工装配，SMD先焊、插件后按厂商允许工艺装配。工厂钢网及SMT参数随贴装方式另定。

PDF使用原生4096px PNG等比排入A3，原生SVG另行交付。原生光追接口在本环境超时，3D预览由MCP导出的实际OBJ模型离线渲染，显示颜色供观察，机械尺寸按厂家图。两张PCB层图均从顶面坐标观察。实际Gerber已独立解析预览，见[制造层预览](review/gerber_preview.png)。

可探测位置使用已有顶层焊盘与连接器焊点。3.3 V 为 C10.1，5 V 为 C11.1，GND 为 C10.2，OE_PWM_N 为 R13.2，OE_CTRL_N 为 R19.2，F_RESET_B 为 J2.9，ERRI_B/ERRU_B 为 J2.19/20。测量参考接控制侧 GND。

三颗转换器正常 3.3 V/5 V 供电，U1 的 PWM_EN 独立，U2/U3 共用 CTRL_EN。PWM 带载、反馈边沿、核心独立掉电等[实机项目](../../docs/open_questions.md)尚未测量。

同目录原有四张分区 PNG 对应上一版 V0.1，仅用于查看此前图面。当前审查使用本页链接的单页总图。
