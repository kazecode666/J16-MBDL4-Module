# J16—MBDL4 数字接口板

AXU5EVB-E J16—MBDL4 专用 3.3 V/5 V 数字接口板，V0.3 交付单页 A3 原理图与首版双层 PCB。

- [嘉立创 EDA 工程、原理图及 PCB 预览](hardware/v0.1/)
- [引脚连接表](hardware/v0.1/pin_connections.csv)
- [51 件 BOM](hardware/v0.1/bom.csv)
- [全料PCBA装配检查、BOM、CPL及装配图](hardware/v0.1/pcba/)
- [供电、OE 与默认状态](docs/schematic_v0.1.md)
- [设计依据](docs/design_basis.md)、[参考资料索引](docs/reference_index.md)、[接口证据](docs/interface_evidence.md)
- [样机待验证项目](docs/open_questions.md)
- [25项统一审查清单](docs/review_checklist.md)

当前交付要求为嘉立创供料并焊好全部51件，含顶面49件SMT、顶面J2和底面J1插件。BOM与CPL覆盖51/51，DNP为0。国际可贴库11种材料均命中，50位号有库存，J1库存0。底装混合焊接、J1供货与标准型工艺拼板仍待厂家审核，当前PCBA下单就绪状态为待审核。前轮已完成的电气/裸板制造检查及本轮装配检查在同一PR维护。[Draft PR #4](https://github.com/kazecode666/J16-MBDL4-Module/pull/4)

厂家原件保存在 Git 忽略的 `.local/references/`。公开权限不明的原件继续仅保留本地，仓库提供必要来源与页码。
