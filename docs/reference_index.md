# 逐份参考资料索引

核查日期 2026-11-11。13 份文件已经复制/下载到 `.local/references/`，逐份 SHA-256 由实际文件计算。全部为仅本地归档，公开版本提供出处和原创核查摘要。ALINX 原理图带 Confidential，TI 文件含再发布限制，其他第三方资料尚无明确公开再分发授权。公开 PDF 下载入口与公开再分发授权分别审核。

本地精确绝对来源和同哈希副本清单保存在 Git 忽略的 `.local/manifest.json`。下文用工作区/来源项目相对路径定位。取得日期与文件修订日期分别记录。

## A1 AXU5EVB-E开发板原理图.pdf

- 厂商/来源为 ALINX。原始来源为 当前工作区根目录/AXU5EVB-E开发板原理图.pdf。
- 版本为 图框 Rev1.0，相关 p18 日期 2022-06-24；标题残留 AXU3EG。用途与关键位置为 p2 板间连接，p18 J15/J16，p19 电源。
- 状态为仅本地归档，路径 `.local/references/alinx_axu5evb_e/AXU5EVB-E开发板原理图.pdf`，大小 535824 字节，19 页。
- SHA-256 为 `cfec1d26542f935009ecb8923210c4f6ed23ca72609d4b463a293b58aeee304f`。

## A2 ACU5EV核心板原理图.pdf

- 厂商/来源为 ALINX。原始来源为 当前工作区根目录/ACU5EV核心板原理图.pdf。
- 版本为 Rev1.0，2020-09-30。用途与关键位置为 p4 Bank43–46，p18/p19 板间接口，p21 PMIC。
- 状态为仅本地归档，路径 `.local/references/alinx_axu5evb_e/ACU5EV核心板原理图.pdf`，大小 362555 字节，21 页。
- SHA-256 为 `d564b945d9363c2d74f793d07e18b21fe866cf031bd48475d7aafa884946c5cb`。

## A3 AXU5EVB-E开发板用户手册.pdf

- 厂商/来源为 ALINX。原始来源为 AXU5EV/资料/AXU5EVB-E开发板用户手册.pdf。
- 版本为 p2 版本记录至 REV1.2；无明确修订日期。用途与关键位置为 p2 版本记录，p41 J16，p42 J15。
- 状态为仅本地归档，路径 `.local/references/alinx_axu5evb_e/AXU5EVB-E开发板用户手册.pdf`，大小 4524065 字节，51 页。
- SHA-256 为 `0b500b6cb4de21f9d49999e15036916c0662cc634da9dda2b8959da452546f81`。

## A4 核心板管脚定义.xls

- 厂商/来源为 ALINX 厂家包。原始来源为 当前工作区根目录/核心板管脚定义.xls。
- 版本为 文内修订未确认，保持原始文件名。用途与关键位置为 J29/J30/J31/J32 四个工作表，分别 60 个针号数据行。
- 状态为仅本地归档，路径 `.local/references/alinx_axu5evb_e/核心板管脚定义.xls`，大小 56320 字节。
- SHA-256 为 `1a4d3e3754ac133d9d0cf9670ada05f8f889491e9a2f93411d8815c314191e77`。

## A5 extender.xdc

- 厂商/来源为 ALINX factory_vivado。原始来源为 AXU5EV/资料/factory_file/factory_vivado/board_test.srcs/constrs_1/new/extender.xdc。
- 版本为 文件无独立修订，工程使用 J45/J46 别名。用途与关键位置为 第1–34行与 J16 球号对照。
- 状态为仅本地归档，路径 `.local/references/alinx_axu5evb_e/extender.xdc`，大小 4246 字节。
- SHA-256 为 `53c631efb8d276f305f0f02a7f186e140769cca6af577170c93faad95ba1010d`。

## H1 28335B PLUS.pdf

- 厂商/来源为 既有 28335 资料。原始来源为 当前工作区根目录/28335B PLUS.pdf。
- 版本为 修订栏空，日期字符串 10/07/2023 保留原文；图内源名含 V2.0。用途与关键位置为 p1 PWM&CAP&QEP、U19/U20/U22/R57，p2 PCB 布局/装配图。
- 状态为仅本地归档，路径 `.local/references/tms320f28335_bplus/28335B PLUS.pdf`，大小 1981382 字节，2 页。
- SHA-256 为 `98fce88d8f99d7d04296afd2583a47eea932d49ce227307f1571ca245d5d7349`。

## H2 28335BPLUS迁移至28388D注意事项.txt

- 厂商/来源为 既有项目说明，作者/审核状态未确认。原始来源为 FPGA_XC7A200T/硬件说明/28335BPLUS迁移至28388D注意事项.txt。
- 版本为 无明确修订，二手讨论。用途与关键位置为 第五节电平转换，第六节故障路径，仅历史对照。
- 状态为仅本地归档，路径 `.local/references/tms320f28335_bplus/28335BPLUS迁移至28388D注意事项.txt`，大小 11567 字节。
- SHA-256 为 `909bca4b96337f643ff0248c42c26f9a8a5751b7cb5c6fe5f80a038c8c92f99b`。

## M1 YXPHM-MBDL4驱动板原理图.pdf

- 厂商/来源为 研旭/既有硬件资料。原始来源为 当前工作区根目录/YXPHM-MBDL4驱动板原理图.pdf。
- 版本为 源图文件名含 motor_driver_60V-V1.1；日期字符串 9/03/2024，格式含歧义。用途与关键位置为 p1 电源、PWM 数字口、U12、U21、U22。
- 状态为仅本地归档，路径 `.local/references/mbdl4/YXPHM-MBDL4驱动板原理图.pdf`，大小 1355131 字节，1 页。
- SHA-256 为 `b987e1a106759907b5528b0a8ccad4388530ab5acf7d5b9e4e3f8a7323af011b`。

## M2 YXPHM-MDBL4电机驱动板硬件说明书.pdf

- 厂商/来源为 研旭。原始来源为 当前工作区根目录/YXPHM-MDBL4电机驱动板硬件说明书.pdf。
- 版本为 封面 YXPHM-MDBL4-60-12-1；修订/日期未明确。用途与关键位置为 PDF p11 表2-1，p20–22 极性及反馈电路。
- 状态为仅本地归档，路径 `.local/references/mbdl4/YXPHM-MDBL4电机驱动板硬件说明书.pdf`，大小 2402298 字节，22 页。
- SHA-256 为 `c4dc0c8824a794d2a70102277e4ab65b5cb2ed70c24c7741b71f6c89cff6cbc3`。

## M3 MDBL4转接板.pdf

- 厂商/来源为 既有硬件资料。原始来源为 当前工作区根目录/MDBL4转接板.pdf。
- 版本为 修订栏空，日期字符串 4-09-2026 保留原文。用途与关键位置为 p1 旧转接连接线索。
- 状态为仅本地归档，路径 `.local/references/mbdl4/MDBL4转接板.pdf`，大小 239975 字节，1 页。
- SHA-256 为 `03189630cdc0bd6ccb6b1221b9865fbe60ace988fba94238f24d27079118ab34`。

## T0 sn74lxc8t245.pdf

- 厂商/来源为 工作区用户提供副本。原始来源为 当前工作区根目录/sn74lxc8t245.pdf。
- 版本为 SCES916A，2023-03；38页。用途与关键位置为 p1 修订，p3 管脚，与官方下载分别保留。
- 状态为仅本地归档，路径 `.local/references/ti_sn74lxc8t245/sn74lxc8t245.pdf`，大小 2104714 字节，38 页。
- SHA-256 为 `755e328a4288cff2aabfa845fa986016eb7453ecbc87cd2a79a39a3d3d6c0c0f`。

## T1 sn74lxc8t245_official.pdf

- 厂商/来源为 Texas Instruments 官方下载。原始来源为 [官方原件入口](https://www.ti.com/lit/ds/symlink/sn74lxc8t245.pdf)。
- 版本为 SCES916A Rev.A，2023-03；39页。用途与关键位置为 p3 管脚，p19–22 功能，p24 供电/布局，后附封装资料。
- 状态为仅本地归档，路径 `.local/references/ti_sn74lxc8t245/sn74lxc8t245_official.pdf`，大小 1852391 字节，39 页。
- SHA-256 为 `814fce99965a6d693b49708c97d7c2499e91070a9f929e4685f7e7852c5bd32c`。

## T2 MPDS363A_PW0024A.pdf

- 厂商/来源为 Texas Instruments 官方 PWR 零件页链接。原始来源为 [官方原件入口](https://www.ti.com/lit/pdf/MPDS363A)。
- 版本为 PW0024A，4220208/A 02/2017；MPDS363A。用途与关键位置为 p1 外形，p2 焊盘，p3 钢网，p4 使用限制。
- 状态为仅本地归档，路径 `.local/references/ti_sn74lxc8t245/MPDS363A_PW0024A.pdf`，大小 145840 字节，4 页。
- SHA-256 为 `2eb8155a790b51e4dd673364e59760d0c1347564f40d42d2651eefd3d7b9a3b8`。

## 来源核对与有限搜索结果

当前工作区最初有 7 个 PDF 和 1 个 XLS，均保留原位并复制必要原件。补充 AXU5EV 已有手册、extender.xdc、历史迁移说明和两份 TI 官方文件，共 13 份本地归档。

AXU5EV/资料/28335、驱动板原理图 与 FPGA_XC7A200T/硬件说明 中的 M1/M2/M3 副本哈希分别一致，当前工作区副本亦一致。H1 与 AXU5EV 资料副本一致。A1/A2/A4 与 AXU5EV 厂家硬件目录副本一致。重复文件按一个资料记录处理。

T0 与 T1 的正文均标 SCES916A，页数和哈希存在差异，因此以 T1 为本轮官方核验依据，保留 T0。两份文件均无原位覆盖。

[TI 产品入口](https://www.ti.com/product/SN74LXC8T245) 与 [PWR 零件页](https://www.ti.com/product/SN74LXC8T245/part-details/SN74LXC8T245PWR) 用于核对器件与 PW/TSSOP-24 封装身份。T2 来自零件页 Packaging information 链接。ALINX 资料来自已有厂家包，MBDL4/历史转接板的原始下载 URL 尚未取得，保留项目相对来源。未取得原件和版权状态见[待确认项](open_questions.md)。

## 本轮归档核查

13 份文件的归档哈希核查通过，所有复制来源文件与归档副本哈希一致。10 个 PDF 共 198 页均成功渲染，XLS 可解析；关键接口电路页、TI 管脚/封装资料和历史 PCB 图完成视觉核查。公开 Markdown 相对链接全部可解析，34 个 J16 信号球号与既有 XDC 顺序一致。公开提交仅含 Markdown 与忽略规则，原件、截图、工具脚本和精确本地路径保持在 Git 忽略区。
