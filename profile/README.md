<div align="center">
  <img src="assets/banner.svg" alt="PICO4yita — PICO × YITA Dynamics" width="100%">
</div>

<h3 align="center">让智能触达真实世界</h3>

<p align="center">
  高性能关节模组 · 拟人力控双臂 · 人形机器人软件栈
</p>

<p align="center">
  <a href="https://www.yitadynamics.com/cn/"><b>YITA 官网</b></a> &nbsp;·&nbsp;
  <a href="https://github.com/PICO4robot"><b>PICO 软件栈</b></a> &nbsp;·&nbsp;
  <a href="#联系"><b>联系我们</b></a>
</p>

---

## 关于 PICO4yita

**PICO4yita** 是 PICO 机器人软件栈与 YITA（伊塔动力）关节模组的工程交汇点。

YITA 提供从动力关节到力控双臂的硬件底座 —— 高集成、力矩感知、全栈自研；PICO 提供从模型资产、运动数据、强化学习训练到整机部署的软件通路。PICO4yita 把两者接在一起：**一颗关节的物理特性，直接进入仿真、训练与真机部署的同一条链路。**

> 从零件精度，到系统确定性。

## 硬件底座 · YITA-C 系列关节模组

一体化关节模组，全系中空走线、双编码器、EtherCAT & CAN FD 通信，控制精度 < 0.01°。

| 型号 | 额定转矩 | 峰值扭矩 | 额定转速 | 外形尺寸 | 重量 | 额定功率 | 减速比 | 中空 | 输入电压 |
| --- | ---: | ---: | ---: | --- | ---: | ---: | ---: | ---: | ---: |
| **YITA-50P-C** | 2.2 N·m | 11 N·m | 155 RPM | D50 × 60 mm | 0.3 kg | 0.03 kW | 25 | 4 mm | 48 V |
| **YITA-65P-C** | 7.8 N·m | 39 N·m | 151 RPM | D65 × 65 mm | 0.5 kg | 0.12 kW | 22.6757 | 4.5 mm | 200 V |
| **YITA-84P-C** | 12 N·m | 60 N·m | 231 RPM | D84 × 67 mm | 0.7 kg | 0.28 kW | 21.5686 | 4.5 mm | 48 V |
| **YITA-100P-C** | 44 N·m | 220 N·m | 135 RPM | D100 × 69 mm | 1.1 kg | 0.59 kW | 22.1538 | 7.5 mm | 48 V |
| **YITA-122P-C** | 62 N·m | 314 N·m | 151 RPM | D122 × 69 mm | 1.6 kg | 0.95 kW | 25.1428 | 5 mm | 48 V |

编码器：双编码器，输入端 ABS 17-bit / 输出端 19-bit。

### 工程特性

| | 特性 | 说明 |
| --- | --- | --- |
| 01 | **工业级可靠** | 2 万小时使用寿命设计，5 倍额定扭矩、百万次冲击承载能力 |
| 02 | **模块化快装** | 模块化抱箍式安装结构，大幅减少螺钉与装配工序，安装快、维护易 |
| 03 | **全系中空** | 全系中空结构，电源与通信线束内走线，布线更简洁、空间利用更高效 |
| 04 | **静音抗冲击传动** | 高硬度斜齿传动 + 高刚度交叉滚子轴承，顺滑传动与高动态抗冲击 |

## 机器人平台

### Yita GR3 Mini · v3.0.0

25-DOF 双足人形机器人，Yita 定制版整机。

| 指标 | 数值 |
| --- | --- |
| 自由度 | 25（另有 4 个 fixed joint：torso / IMU / 左右末端） |
| 整机质量 | 43.89 kg |
| 站立高度 | 1.218 m |
| 执行器 | YITA-100P-C / 84P-C / 65P-C，限值 199.4 / 75.5 / 68 / 31.2 / 11 N·m |
| 碰撞变体 | 原始 primitive · `_footpts` 足底球 · `_wbpts` 全身球（526 球） |

### Yita Alita · v1.0.1

23-DOF 双足人形机器人，并联膝 / 踝 / 腰设计。

| 指标 | 数值 |
| --- | --- |
| 自由度 | 23（23 电机 → 23 输出关节，8 个被动闭链输出） |
| 整机质量 | 41.98 kg |
| 站立高度 | 1.443 m |
| 执行器 | YITA-122P-C / 100P-C / 84P-C / 65P-C |
| 闭链机构 | 膝平行四边形、踝 / 腰曲柄推拉杆，10 组 `equality/connect` |

## 软件栈 · PICO

| 层 | 组件 | 职责 |
| --- | --- | --- |
| 模型资产 | `PICO-robot` | MJCF / URDF、网格（LFS）、版本化 `model.yaml`、并联闭链运动学 |
| 运动数据 | `PICO-dataset` | 动捕与重定向数据注册表：DVC 指针 + 策展元数据 |
| 训练 | `PICO-rl` | 基于 mjlab 的强化学习训练、评估、导出与录制 |
| 建模工具 | `PICO-momp`、`PICO-tool-*` | CAD / URDF → 标准化 MJCF 打磨，网格 / MJCF / 动捕浏览器 |
| 部署 | `PICO-sdk`、`PICO-navigation`、`PICO-fleet`、`PICO-ui` | ROS 2 控制、导航与 SLAM、集群调度、上位机 |

软件栈仓库见 [**PICO4robot**](https://github.com/PICO4robot)。

## 本组织的方向

PICO4yita 聚焦 YITA 硬件平台相关的工程资产：

- 关节模组的驱动、标定与 CAN FD / EtherCAT 接入
- YITA 平台整机模型（MJCF / URDF）、碰撞体与执行器参数标定
- PICO 软件栈在 YITA 硬件上的训练配置、Sim2Real 与部署说明
- 硬件在环（HIL）测试、数据采集与端到端验证脚本

## 联系

- 官网：[www.yitadynamics.com](https://www.yitadynamics.com/cn/)
- 销售与技术支持：sales@yitadynamics.com
- 地址：广东省深圳市南山区同方科兴科学园 F 栋 9 楼 901

## 许可

本组织文档内容采用 **CC BY-NC 4.0**（署名 — 非商业性使用 4.0 国际）许可，禁止商用。
各代码仓库以仓库内 `LICENSE` 为准。

<div align="center">
  <sub>© 2026 PICO4yita · PICO × YITA Dynamics</sub>
</div>
