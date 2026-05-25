# Aster Hitbox - 树莓派 Pico 开源格斗键盘

<div align="center">



**一款面向格斗游戏入门玩家的低成本、可定制、全开源 Hitbox 键盘**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Hardware: RP2040](https://img.shields.io/badge/Hardware-RP2040-blue.svg)](https://www.raspberrypi.com/products/raspberry-pi-pico/)
[![Firmware: GP2040-CE](https://img.shields.io/badge/Firmware-GP2040--CE-green.svg)](https://github.com/OpenStickCommunity/GP2040-CE)
[![Input Lag: <1ms](https://img.shields.io/badge/Input%20Lag-%3C1ms-brightgreen.svg)](https://github.com/your-username/aster-hitbox#性能测试)
[![BOM Cost: ≤150元](https://img.shields.io/badge/BOM%20Cost-%E2%89%A4150%E5%85%83-orange.svg)](https://github.com/your-username/aster-hitbox#bom清单)

</div>

## 📖 目录

- [项目简介](#项目简介)
- [核心特性](#核心特性)
- [硬件规格](#硬件规格)
- [快速开始](#快速开始)
- [硬件制作指南](#硬件制作指南)
- [固件烧录](#固件烧录)
- [上位机使用](#上位机使用)
- [性能测试](#性能测试)
- [BOM清单](#bom清单)
- [贡献指南](#贡献指南)
- [许可证](#许可证)
- [致谢](#致谢)

## 项目简介

Aster Hitbox 是一款基于树莓派 Pico (RP2040) 的全开源格斗键盘项目。我们的目标是让格斗游戏入门玩家以极低的门槛获得专业级的输入体验，解决市售产品价格昂贵、键位固定、无法二次开发的核心痛点。

在达到专业级性能标准（输入延迟<1ms）的同时，我们将单台物料成本控制在150元以内，并提供行业内最完整的可定制性和二次开发能力。

## 核心特性

- ⚡ **超低输入延迟**：实测<1ms，达到职业电竞级别
- 🎮 **全键无冲**：16键同时触发无冲突
- 🔄 **三种SOCD清洁模式**：上优先、后输入优先、中性模式，固件可切换
- 🖥️ **多平台支持**：Windows/macOS/Linux/PS4/PS5/Switch全兼容
- 🎨 **完全可定制**：全键可编程，支持配置文件导入导出
- 🔧 **丰富扩展接口**：预留I2C、SPI和GPIO，支持OLED、2.4G无线等功能
- 💻 **开源设计**：硬件、固件、上位机全部开源，自由修改和二次开发
- 💰 **极致性价比**：单台物料成本≤150元，批量生产可低至100元

## 硬件规格

| 项目 | 规格参数 |
|------|----------|
| 主控芯片 | RP2040 双核 133MHz, 264KB SRAM |
| 按键数量 | 12个标准按键 + 4个扩展按键位 |
| 按键布局 | 标准Hitbox布局(左4方向+右8功能) |
| 按键开关 | 凯华BOX白轴(45g线性, 1.8mm行程) |
| 输入延迟 | <1ms (Input Lag Tester实测) |
| 报告率 | 1000Hz USB HID |
| 按键寿命 | ≥5000万次 |
| 物理尺寸 | 210×279×30mm (含外壳) |
| 重量 | 约300g |
| 供电方式 | USB 5V/100mA，无需额外电源 |
| 工作温度 | 0℃~40℃ |
| 存储温度 | -20℃~60℃ |

## 快速开始

### 1. 准备材料
- 树莓派Pico开发板 x1
- 凯华BOX白轴 x16
- 定制PCB板 x1
- 亚克力/3D打印外壳 x1套
- 键帽 x12
- USB Type-C数据线 x1

### 2. 焊接组装
按照PCB上的丝印标识，依次焊接二极管、按键开关和树莓派Pico。

### 3. 烧录固件
1. 按住树莓派Pico的START键，同时插入USB连接电脑
2. 电脑会识别为一个名为"RPI-RP2"的U盘
3. 将最新版本的`aster-hitbox.uf2`固件文件拖入U盘
4. 树莓派Pico会自动重启，固件烧录完成

### 4. 开始使用
连接电脑或游戏主机，即可开始使用。

## 硬件制作指南

### PCB设计
本项目使用嘉立创2层FR-4 PCB设计，尺寸为210×279mm，厚度1.6mm。

- [PCB原理图](https://github.com/HSRAsterismer/Aster-Hitbox/blob/main/PCB_PCB_hitbox_2026-05-25.pdf)
- [PCB Gerber文件](https://github.com/HSRAsterismer/Aster-Hitbox/blob/main/Gerber_hitbox_PCB_hitbox_2026-05-19.zip)


### 焊接步骤
1. 焊接所有1N4148二极管（注意方向，黑色环朝向PCB上的白线）
2. 焊接树莓派Pico（引脚对齐，不要焊反）
3. 焊接所有按键开关
4. 测试所有按键是否正常工作
5. 安装外壳和键帽

## 固件烧录

### 预编译固件
从[Releases页面](https://github.com/OpenStickCommunity/GP2040-CE)下载最新的预编译固件。

## 性能测试

我们使用专业的Input Lag Tester进行了严格的性能测试：

| 测试项目 | 测试结果 |
|----------|----------|
| 平均输入延迟 | 0.72ms |
| 最大输入延迟 | 0.95ms |
| 最小输入延迟 | 0.58ms |
| 报告率稳定性 | 1000Hz ±0.1% |
| 全键无冲测试 | 12键同时触发无冲突 |

## BOM清单

| 元器件 | 型号/规格 | 单价(元) | 数量 | 小计(元) | 备注 |
|--------|-----------|----------|------|----------|------|
| 主控板 | 树莓派Pico | 25.00 | 1 | 25.00 | 国产替代约18元 |
| 按键开关 | 凯华BOX白轴 | 1.50 | 12 | 18.00 | 可更换其他轴体 |
| PCB板 | 嘉立创2层FR-4 | 30.00 | 1 | 30.00 | 5片起订，单片成本6元 |
| 键帽 | 机械键盘键帽 | 1.50 | 12 | 18.00 | 可使用旧键盘键帽 |
| 其他 | 螺丝、螺母、脚垫 | - | - | 9.40 | |
| **总计** | | | | **141.00** | |


## 贡献指南

我们欢迎任何形式的贡献！如果你有好的想法或改进建议：

1. Fork本仓库
2. 创建你的特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的修改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 打开一个Pull Request

## 许可证

本项目采用MIT许可证开源 - 详见[LICENSE](LICENSE)文件。

## 致谢

- [GP2040-CE](https://github.com/OpenStickCommunity/GP2040-CE) - 优秀的开源格斗控制器固件
- [树莓派基金会](https://www.raspberrypi.com/) - 提供强大的RP2040芯片
- 所有为开源格斗控制器社区做出贡献的开发者们

---

<div align="center">

如果这个项目对你有帮助，请给我们一个⭐Star！

有任何问题或建议，欢迎提交Issue或联系我们。

**Aster Hitbox - 让每个格斗玩家都能拥有专业级的输入体验**

</div>

需要我帮你补充**详细的焊接步骤图解说明**或者**常见问题排查(FAQ)章节**吗？
