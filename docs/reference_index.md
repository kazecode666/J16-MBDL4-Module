# 参考资料索引

沿用 DOC-01 已有资料，仅保留原理图设计所需的来源、版本、用途与页码。原件位于 Git 忽略的 `.local/references/`。ALINX 原理图带 Confidential 标记，TI 文件含再发布限制，其余厂家资料的公开授权尚未取得，原件继续保留本地。

页码按 PDF 从 1 开始的页序。MBDL4 手册印刷页码比 PDF 页序少 5 页。

| 编号 | 文件与版本 | 已有来源 | 用途及关键位置 |
|---|---|---|---|
| A1 | AXU5EVB-E开发板原理图.pdf，图框 Rev1.0，相关页日期 2022-06-24 | 当前工作区根目录，AXU5EV 厂家底板资料亦有副本 | p2 板间连接，p18 J15/J16，p19 电源。图框标题保留 AXU3EG 字样 |
| A2 | ACU5EV核心板原理图.pdf，Rev1.0，2020-09-30 | 当前工作区根目录，AXU5EV 厂家核心板资料亦有副本 | p4 Bank43–46，p18/p19 板间接口，p21 PMIC |
| A3 | AXU5EVB-E开发板用户手册.pdf，版本记录至 REV1.2 | AXU5EV/资料/ | p2 版本记录，p41 J16，p42 J15 |
| A4 | 核心板管脚定义.xls | 当前工作区根目录，AXU5EV 厂家核心板资料亦有副本 | J29/J30/J31/J32 四个工作表的针号与 FPGA 球号 |
| A5 | extender.xdc，工程使用 J45/J46 别名 | AXU5EV/资料/factory_file/factory_vivado/board_test.srcs/constrs_1/new/ | 第 1–34 行与 J16 球号对照 |
| M1 | YXPHM-MBDL4驱动板原理图.pdf，源图文件名含 motor_driver_60V-V1.1，日期字符串 9/03/2024 | 当前工作区根目录；AXU5EV/资料/28335、驱动板原理图/；FPGA_XC7A200T/硬件说明/ | p1 数字口、电源、PWM 光耦、U12、U21、U22 |
| M2 | YXPHM-MDBL4电机驱动板硬件说明书.pdf，封面 YXPHM-MDBL4-60-12-1 | 同 M1 的已有资料目录 | 图 2-3 及 p11 表 2-1，p20–22 极性与反馈电路 |
| M3 | MDBL4转接板.pdf，日期字符串 4-09-2026 | 同 M1 的已有资料目录 | p1 历史转接连接线索 |
| H1 | 28335B PLUS.pdf，日期字符串 10/07/2023，图内源名含 V2.0 | 当前工作区根目录；AXU5EV/资料/28335、驱动板原理图/ | p1 PWM&CAP&QEP、U19/U20/U22/R57，p2 PCB 布局/装配图 |
| H2 | 28335BPLUS迁移至28388D注意事项.txt，二手设计讨论 | FPGA_XC7A200T/硬件说明/；AXU5EV/资料/28335、驱动板原理图/ | 第五节电平转换、第六节故障路径，仅作历史对照 |
| T0 | sn74lxc8t245.pdf，SCES916A，2023-03，38 页 | 当前工作区根目录 | 已有手册副本，保留本地 |
| T1 | sn74lxc8t245_official.pdf，SCES916A Rev.A，2023-03，39 页 | TI 官方数据手册入口 | p3 管脚，p19–22 功能，p24 供电/布局，本轮器件核验依据 |
| T2 | MPDS363A_PW0024A.pdf，PW0024A，4220208/A 02/2017 | TI PWR 零件页的封装资料链接 | p1 外形，p2 焊盘，p3 钢网 |

A1–A5 位于 `.local/references/alinx_axu5evb_e/`，M1–M3 位于 `.local/references/mbdl4/`，H1–H2 位于 `.local/references/tms320f28335_bplus/`，T0–T2 位于 `.local/references/ti_sn74lxc8t245/`。

[TI 产品入口](https://www.ti.com/product/SN74LXC8T245)、[PWR 零件页](https://www.ti.com/product/SN74LXC8T245/part-details/SN74LXC8T245PWR)、[官方数据手册](https://www.ti.com/lit/ds/symlink/sn74lxc8t245.pdf)和[PW0024A 封装图](https://www.ti.com/lit/pdf/MPDS363A)用于器件与封装核验。T0 与 T1 分别保留，设计引用 T1。
