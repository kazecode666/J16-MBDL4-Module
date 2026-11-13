# 样机待验证项目

- 六路 PWM 接入原 MBDL4 后测量带载高低电平、光耦输入电流、脉宽和关断状态，覆盖 PWM_EN 禁止与驱动板原有故障关断路径。
- 按实际 AQM 编码器位移分辨率、解码倍率和最大线速度核对边沿间隔，测量线缆负载下的反馈高电平及边沿。
- J16 电源持续存在、核心 VCCO 单独骤降时，检查 OE 关断过程及 FPGA 引脚注入。CTRL_EN 仅表示软件使能。
- 核对 F_Reset 空闲高、低→高清锁存及 OE 切换边沿。初始化先 PWM_EN=0、RELCON/ENCON=0、F_RESET=1，再 CTRL_EN=1 读取反馈。清故障先撤销运行请求并消除故障原因，再发复位沿、检查 ERRI/ERRU，由 PWM_EN 独立放行。切换 CTRL_EN 前恢复 F_Reset 空闲高。
- 原生BRD已核对J15/J16中心距64.76238mm、40针与键侧，MBDL4库编号/键侧及Q1/Q2原厂引脚已闭合。当前需补齐连接器内腔及有效接触尺寸、AN9238近边Y偏置和实际叠高、散热器/风扇及线缆包络。详见[25项审查清单](review_checklist.md)与[叠合图](../hardware/v0.1/review/assembly_overlay.png)。

测量可使用现有 C10/C11、R13/R19 和 J2 焊盘，定位见[设计说明](schematic_v0.1.md)。以上实物测量和机械装配项目尚未执行。当前原理图与 PCB 的实际检查结果见[交付检查结果](../hardware/v0.1/review/check_results.json)。
