# J16—MBDL4 数字接口板

AXU5EVB-E J16—MBDL4 专用 3.3 V/5 V 数字接口板，V0.3 交付单页 A3 原理图与首版双层 PCB。

- [嘉立创 EDA 工程、原理图及 PCB 预览](hardware/v0.1/)
- [引脚连接表](hardware/v0.1/pin_connections.csv)
- [51 件 BOM](hardware/v0.1/bom.csv)
- [供电、OE 与默认状态](docs/schematic_v0.1.md)
- [设计依据](docs/design_basis.md)、[参考资料索引](docs/reference_index.md)、[接口证据](docs/interface_evidence.md)
- [样机待验证项目](docs/open_questions.md)

本轮以 `e4c6efa` 和用户手工整理的当前图面为基础，在同一 [Draft PR #4](https://github.com/kazecode666/J16-MBDL4-Module/pull/4) 中完成收尾。三颗 SN74LXC8T245 正常供电，U1 独立 PWM_EN，U2/U3 共用 CTRL_EN，沿用原 28335BPLUS 直接 5 V 转换方案。去耦支路、局部地线及复位/故障注释已完善，带载与掉电瞬态测量留待无功率接口联调。

厂家原件保存在 Git 忽略的 `.local/references/`。公开权限不明的原件继续仅保留本地，仓库提供必要来源与页码。
