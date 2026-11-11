# J16—MBDL4 数字接口板

AXU5EVB-E J16—MBDL4 专用数字接口板，当前交付单页 A3 总原理图 V0.2 审查稿。

- [原理图工程与审查图片](hardware/v0.1/)
- [引脚连接表](hardware/v0.1/pin_connections.csv)
- [初版 BOM](hardware/v0.1/bom.csv)
- [供电、OE 与默认状态说明](docs/schematic_v0.1.md)
- [设计依据](docs/design_basis.md)、[参考资料索引](docs/reference_index.md)、[接口证据](docs/interface_evidence.md)
- [原理图审查项](docs/open_questions.md)

按 [Issue #3](https://github.com/kazecode666/J16-MBDL4-Module/issues/3) 使用嘉立创 EDA 完成本轮设计，从最新 main 建立分支，通过 Draft PR 提交原理图审查。接口板仅经 J16 与控制器插接。本轮已授权在原理图关键电气问题闭合后继续 PCB。当前两轮审查仍保留 PWM 驱动问题，具体计算与停止点见设计说明。

既有厂家原件保存在 Git 忽略的 `.local/references/`。公开权限不明的原件继续仅保留本地，仓库提供必要来源与页码。
