# J16—MBDL4 数字接口板 V0.3

AXU5EVB-E 的 J16 与 MBDL4 的 PWM 数字口之间使用本板完成 3.3 V/5 V 电平转换。V0.3 采用单页 A3 原理图与双层 PCB，设计资料沿用仓库目录名 `hardware/v0.1/`。J15 上的 AN9238 另行接收 MBDL4 模拟口的电流采样信号。

14 路业务信号分为 6 路 PWM、3 路控制输出和 5 路反馈。另有两路板内使能，U1 使用独立的 `PWM_EN`，U2/U3 共用 `CTRL_EN`。

## 首板状态

- **装配**。设计资料保留原 51 件全厂装方案。首板实际由厂家装配顶面的 49 件 SMT 和 J2，用户自行焊接 J1 并已插入 J16。自购 J1 的精确型号待核实。[实际装配说明](hardware/v0.1/pcba/)
- **空载静态测试**（`USER_REPORTED`）。用户确认 6 路 PWM、3 路控制输出和 QEPA 一路反馈在记录条件下通过。QEPB、QEPZ、ERRI、ERRU 只观察到默认低，尚待外部高电平逐路验证。[首板空载静态测试记录](docs/writing/interface_board_static_test_record.md)
- **后续验收**。MBDL4 数字口联调、动态 PWM 与死区、真实驱动器负载、编码器计数、故障与继电器动作、掉电瞬态和电机运动仍待验证。[样机待验证项目](docs/open_questions.md)

## 资料入口

- [设计交付与可编辑 EDA 工程](hardware/v0.1/) · [总原理图](hardware/v0.1/review/schematic_A3.png) · [引脚连接表](hardware/v0.1/pin_connections.csv)
- [电路与默认状态](docs/schematic_v0.1.md) · [25 项设计审查清单](docs/review_checklist.md) · [接口依据与资料页码](docs/interface_evidence.md)
- [AXU5EV VIO 静态测试工程](https://github.com/kazecode666/AXU5EV/blob/main/hardware/axu5ev/j16_level_test/README.md) · [论文审阅背景](docs/writing/interface_board_review_context.md) · [两节论文待审原稿](docs/writing/interface_board_draft_sections.md)
- [设计依据](docs/design_basis.md) · [参考资料索引](docs/reference_index.md)

公开权限不明的厂家原件保留在 Git 忽略的 `.local/references/`。
