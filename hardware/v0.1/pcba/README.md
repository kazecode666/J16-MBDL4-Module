# PCBA装配就绪检查

2026-11-13，按PR #4工艺路线变更评论核查，输入为`3a4d900`与当前嘉立创EDA工程。交付要求为嘉立创供全部物料并焊好全部51件，包含J1底面插件和J2顶面插件。全部位号均列为必装，DNP为0。当前全料PCBA接单仍待厂家审核。[本轮要求](https://github.com/kazecode666/J16-MBDL4-Module/pull/4#issuecomment-6845780688)

## 结果

| 检查 | 本轮证据与状态 |
|---|---|
| 资料覆盖 | BOM/CPL各51位号，顶面49件SMT、顶面J2一件THT、底面J1一件THT。原生BOM的11种物料与逐位号BOM精确MPN/C编码一致，CPL与当前MCP元件坐标、安装面、旋转比较差异0。 |
| 可贴库 | 国际官方装配库11种现用物料均启用，覆盖51位号，49件为SMT，J1/J2为THT/manualWeld。公开库级工艺已核实。 |
| 供料 | 国际接口10种料、50位号显示正库存。J1 C5909928库存及可预售量均为0。中国登录后的可贴库也命中J1扩展库条目并显示库存0，J2命中韩下扩展库条目并显示库存。 |
| 本工程确认 | 中国订单级51件匹配、旋转预览、底装J1及双面插件工艺、报价和拼板均待确认。厂家已受理并确认全装配的位号数为0。 |
| 全装配下单条件 | 待J1供货、混合装配工艺及生产拼板获厂家认可。当前文件用于审核。 |

国际库存为北京时间14:31查询快照，未锁料。逐料号来源、时刻、库存及工艺字段见[物料核对表](material_check.csv)。中国与国际平台的供料范围及工艺受理分别审核，订单确认状态在[检查数据](check_results.json)中记录。

本轮实际打开已登录的嘉立创下单助手，查询中国可贴库的J1/J2，并进入SMT页面。点击上传BOM与坐标时，页面要求先选择对应PCB订单。当前列表没有本设计的PCB订单，页面停在该步骤，订单级BOM匹配、工艺报价及旋转预览尚待进行。

## 审核资料

- [完整PCBA BOM](bom_pcba.csv)，逐位号51行，每件均要求厂家供料和装配，DNP全部为No。
- [完整CPL](cpl.csv)，包含49件SMT与J1/J2两件插件。坐标单位mm，Layer为Top/Bottom，角度采用EDA原生角度归一化至0…359°。
- [原生BOM导出](native_bom.tsv)与[原生CPL导出](native_cpl.tsv)，通过嘉立创EDA MCP直接导出，保留原列名及分组。
- [顶面装配图](assembly_top.svg)与[PNG预览](assembly_top.png)，顶面50件。包含U1–U3的1脚及Q1/Q2的1B、2E、3C放大图。
- [底面装配图](assembly_bottom.svg)与[PNG预览](assembly_bottom.png)，底面J1。底图采用实物底视镜像，CPL仍使用顶视坐标。
- [Gerber与钻孔](../review/J16-MBDL4_V0.3_Gerber.zip)，沿用本轮输入的60×55mm单板。综合DRL包含全部106孔，其中40个过孔子集文件仅供分类参考。
- [可编辑工程](<../J16-MBDL4/J16-MBDL4 V0.3.eprj3>)、[原25项清单](../../../docs/review_checklist.md)与[电气检查记录](../review/check_results.json)。

本轮未发生电路、封装、坐标、走线或板框修改，Gerber沿用已验证的同版输出。装配图按当前原生PCB的焊盘/元件轮廓与MCP导出CPL生成。工厂拼板工程稿获确认后，生产拼板的Gerber、位号数量和坐标偏移需同步采用工程稿。

## 安装面、旋转与极性

| 对象 | 安装要求与核对依据 |
|---|---|
| J1 | Bottom，中心(30,5)mm，180°，40针。顶视1脚(5.87,3.73)mm、2脚(5.87,6.27)mm。母座朝板底插接，键侧见底视图，厂家须完成插件焊接。 |
| J2 | Top，中心(30,47)mm，0°，26针。顶视1脚(14.76,45.73)mm，键槽及红边1脚见顶视图，厂家须完成插件焊接。 |
| U1/U2/U3 | Top，0°，1脚分别(11.425,26.22)/(25.425,22.22)/(40.425,26.22)mm，依实际焊盘编号核对。 |
| Q1/Q2 | Top，0°，自定义SOT-23焊盘。1脚分别(22,12.05)/(36,12.05)mm。原厂引脚1B、2E、3C。实际焊盘按onsemi CASE318核对，保留2条ATTRMATCHCODE封装标题警告，订单预览需核对旋转/1脚及焊盘适配。 |
| C/R | 均Top，无极性。所有44件阻容的原生角度、位号与MPN均逐项进入CPL/BOM。 |

C/R总计44件，另有3颗U、2颗Q及2个J，共51件。CPL各元件的Ref X/Y与Mid X/Y在本工程相同，使用原生器件参考点。机器贴装角度校正以工厂物料库和1脚预览为准，当前数据为审核输入。[onsemi引脚和封装资料](https://www.onsemi.com/pdf/datasheet/mmbt3904lt1-d.pdf)

## 工艺及供料待审

1. 标准型公开支持单/双面贴片与插件，经济型为单面。本板为顶面SMT、顶面J2和底面J1，按标准型审核。2026-11能力表规定最小生产外形70×70mm。60×55mm单板需要厂家评估可拆工艺框或拼板，工艺边、Mark、定位孔、分板方式和最终坐标由工程稿确认。[工艺能力](https://www.jlc-smt.com/vtechnology)、[尺寸及类型说明](https://www.jlc.com/portal/server_guide_26.html)、[帮拼流程](https://www.jlc.com/portal/server_guide_4069.html)
2. 2026-03手工焊说明仍有SMT与插件同面限制，当前标准型能力表又列双面贴片加插件。需厂家明确受理本工程的顶面SMT+顶面J2+底面J1组合，并给出全部51件的厂内焊接流程。J2网页列Wave Soldering，国际API列manualWeld，具体后焊方式由工厂审核。[手工焊说明](https://www.jlc.com/portal/server_guide_21925.html)、[J2装配库](https://jlcpcb.com/partdetail/hanxia-HX_JN2_54_2x13P_ZZ_H89/C42455950)
3. J1为PBT系列，Sullins ECB #10008 p1允许人工或波峰焊，不推荐回流。需SMT回流后由厂家插装焊接J1。J1底装的焊接面位于顶层，当前原生几何实测J1.40至C10.1铜隙1.338mm、至C10本体轮廓1.641mm，J1.2至C11.1铜隙1.330mm、至C11本体轮廓1.630mm，需厂家评估治具/喷嘴避让。嘉立创治具指南给焊接面SMT到插件焊盘至少5mm的条件，当前布局需要个案工艺确认。[Sullins PBT通告](https://www.sullinscorp.com/wp-content/uploads/2013/02/ECB-10008-HEADER-PBT-PRODUCT-SERIES.pdf)、[治具指南](https://www.jlc.com/portal/q7i49377.html)、[选择焊指南](https://www.jlc.com/portal/q7i49023.html)
4. J1 C5909928当前无库存。已查同系列NYLON带键直插备选SFH11-NBPC-D20-ST-BK/C7000675，国际库启用状态为no、库存/预售为0。尚无已核实可供本单的兼容替代料。保留J1底装、防呆和既有针序，待厂家供货/代采或可用替代确认。[J1可贴库](https://www.jlc-smt.com/lcsc/detail/C5909928.html)、[备选商品](https://www.lcsc.com/product-image/C7000675.html)
5. 顶层66个0603焊膏开窗为原生U形，既有CAM与原生形状一致。全料PCBA的钢网厚度、锡量、开口与焊接曲线由厂家审核。全部51位号须进入工厂最终装配清单并通过安装面/旋转预览。

建议工厂审核沿用双层FR4、1.6mm、1oz、绿油白字及无铅喷锡基线，表面处理和钢网工艺随PCBA审核确定。全料采购数量还需加上工厂确认的损耗数量。当前已列明51件厂内必装范围，工艺和供货批准待取得。
