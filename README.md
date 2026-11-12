# J16—MBDL4 数字接口板

AXU5EVB-E J16—MBDL4 专用 3.3 V/5 V 数字接口板，V0.3 交付单页 A3 原理图与首版双层 PCB。

- [嘉立创 EDA 工程、原理图及 PCB 预览](hardware/v0.1/)
- [引脚连接表](hardware/v0.1/pin_connections.csv)
- [51 件 BOM](hardware/v0.1/bom.csv)
- [供电、OE 与默认状态](docs/schematic_v0.1.md)
- [设计依据](docs/design_basis.md)、[参考资料索引](docs/reference_index.md)、[接口证据](docs/interface_evidence.md)
- [样机待验证项目](docs/open_questions.md)
- [25项统一审查清单](docs/review_checklist.md)

本轮以 `5622d72` 和用户保存的当前工程为基础，在同一Draft PR #4中按25项清单修订连接器、入口电容间距及丝印，更新实际检查与制造文件。三颗SN74LXC8T245正常供电，U1独立PWM_EN，U2/U3共用CTRL_EN，沿用原28335BPLUS直接5V转换方案。连接器实体插合、同装空间与实机项目的待办详见清单。[Draft PR #4](https://github.com/kazecode666/J16-MBDL4-Module/pull/4)

厂家原件保存在 Git 忽略的 `.local/references/`。公开权限不明的原件继续仅保留本地，仓库提供必要来源与页码。
