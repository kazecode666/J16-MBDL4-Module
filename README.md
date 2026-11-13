# J16—MBDL4 数字接口板

AXU5EVB-E J16—MBDL4 专用 3.3 V/5 V 数字接口板，V0.3 交付单页 A3 原理图与首版双层 PCB。

- [嘉立创 EDA 工程、原理图及 PCB 预览](hardware/v0.1/)
- [引脚连接表](hardware/v0.1/pin_connections.csv)
- [51 件 BOM](hardware/v0.1/bom.csv)
- [PCBA装配检查、BOM、CPL及装配图](hardware/v0.1/pcba/)
- [供电、OE 与默认状态](docs/schematic_v0.1.md)
- [设计依据](docs/design_basis.md)、[参考资料索引](docs/reference_index.md)、[接口证据](docs/interface_evidence.md)
- [样机待验证项目](docs/open_questions.md)
- [25项统一审查清单](docs/review_checklist.md)

按最新设计决定，J1采用连兴旺254PM-2x20P-V/C53202170无凸键底装排母，目标为嘉立创供料并完成底面J1、顶面J2及49件顶面SMT共51件装配，DNP为0。C10/C11及邻近4件元件已局部调整，J1顶面焊盘/阻焊开窗至全部49件SMT本体/焊盘/开窗的最小净距为5.22838mm。成品保持60×55mm，按底装插件与顶面SMT/插件混合装配提交工艺审核。标准型70×70mm下限所需工艺拼板或可拆工艺框、51件订单匹配及本单受理仍待厂家确认。J1实际插合列首板实测。[J1选型及装配说明](hardware/v0.1/pcba/j1_selection.md)、[最新设计决定](https://github.com/kazecode666/J16-MBDL4-Module/pull/4#issuecomment-6849230634)

厂家原件保存在 Git 忽略的 `.local/references/`。公开权限不明的原件继续仅保留本地，仓库提供必要来源与页码。
