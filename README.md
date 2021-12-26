# 8051 Uno Development Board based on STC8G & STC8H

⭐ 基于 STC8G 与 STC8H 系列单片机的 8051 Uno 开发板 ⭐

[GitLab (Homepage)](https://gitlab.soraharu.com/XiaoXi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H) | [OSHWHub](https://oshwhub.com/yanranxiaoxi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H)

![实拍图](https://downloadserver.soraharu.com:7000/8051%20Uno%20Development%20Board%20based%20on%20STC8G%20and%20STC8H/Image/Product_quality_5.jpg)

## 🤔 这是什么

这是一个基于 STC8G 与 STC8H 系列国产单片机的 8051 Uno 开发板，使用 [立创 EDA](https://lceda.cn/) 进行开发。

`JUMP1` 为单片机供电选择跳线，你可以自由选择 3.3V 或 5V 作为单片机的供电（使用跳线帽将相应电源与 VCC 短接），该跳线不会影响 CH340N 芯片的供电（CH340N 始终工作在 5V）。

`SW2` 为单片机的串口烧录开关（实际为控制 VCC 网络的开关），在进行串口烧录时，首先保证 `SW2`、`SW4` 处于断开状态，使用 `USB1` 或 `USB2` 与计算机连接，在 STC-ISP 软件内选中新增的串口并配置单片机参数后点击 下载/编程 按钮，之后按下 `SW2` 即可烧录程序。

`SW4` 为单片机模拟 USB 直接烧录开关，在进行模拟 USB 直接烧录时，首先保证 `SW2` 处于断开状态，`SW4` 处于接通（按下）状态，按下 `SW3` 的同时使用 `USB3` 与计算机连接，在 STC-ISP 软件内等待识别出 `STC USB Writer`，松开 `SW3`，即进入模拟 USB 直接烧录模式，可进行后续配置并烧录。

`SW3` 为模拟 USB 直接烧录上电启动开关，仅需要在进行模拟 USB 直接烧录的芯片上电时接通（按下），上电后即可断开，具体操作可查看上条。

注意：使用模拟 USB 直接烧录功能不可以调节内部 IRC 频率，也不可以进行片上仿真，建议使用串口进行烧录，在工程内提供有 `无模拟 USB 直接烧录功能（Without USB Writer）` 的 PCB 设计，可直接选择使用。

本 PCB 设计已通过完整功能性测试，且已添加 [嘉立创](https://www.jlc.com/) SMT 定位孔，可直接进行 SMT 贴片生产。但请注意，本设计完整开源并遵循 [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) 开源协议，开源作者不对作品的安全性、完整性作任何承诺，且不对因此产生的任何损失承担后果。

你可以使用本项目的 焊接助手（[标准版](https://htmlpreview.soraharu.com/?https://gitlab.soraharu.com/XiaoXi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H/-/raw/master/InteractiveHtmlBom/index.html) | [无模拟 USB 直接烧录功能](https://htmlpreview.soraharu.com/?https://gitlab.soraharu.com/XiaoXi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H/-/raw/master/InteractiveHtmlBom/index_Without-USB-Writer.html)） 有效地提升手工焊接效率，本助手通过 [InteractiveHtmlBom](https://gitlab.soraharu.com/XiaoXi/InteractiveHtmlBom) 自动生成。

## 🛠️ 生产电路板

本项目的 Gerber 文件可以从 [Releases](https://gitlab.soraharu.com/XiaoXi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H/-/releases) 页面获取，并允许在开源许可范围内的商业目的使用。

*建议使用 [嘉立创](https://www.jlc.com/) 生产高品质电路板。

*It is recommended to use [JLCPCB](https://jlcpcb.com/) to produce high-quality circuit boards.

## ⚙️ 部署至 EasyEDA

1. 克隆本项目 [源代码](https://gitlab.soraharu.com/XiaoXi/8051-Uno-Development-Board-based-on-STC8G-and-STC8H/-/archive/master/8051-Uno-Development-Board-based-on-STC8G-and-STC8H-master.zip) 到本地
2. 在立创 EDA 标准版编辑器中选择 `文件` -> `打开` -> `立创EDA...`
3. 选择本项目源代码中的 `/EasyEDA/*.json` 文件并分别导入

## 🔤 字体

- NotoSerifCJKsc-Medium | [下载](https://github.com/googlefonts/noto-cjk/raw/main/Serif/NotoSerifCJKsc-Medium.otf) | [官方](https://github.com/googlefonts/noto-cjk) | [SIL Open Font License 1.1](https://choosealicense.com/licenses/ofl-1.1/)

## 📄 支持 MCU

本项目 MCU 为 LQFP-32 封装，以下所有支持 MCU 均需选用其 LQFP-32 封装版本。

注意：STC8G 系列单片机如需使用模拟 USB 直接烧录功能，需要确保固件版本高于或等于 `7.3.12U`。

| Model       | Test   | Remark             |
| ----------- | ------ | ------------------ |
| STC8G2K32S4 |        |                    |
| STC8G2K48S4 |        |                    |
| STC8G2K60S4 |        |                    |
| STC8G2K64S4 | Tested | Recommend          |
| STC8H1K16   | Tested |                    |
| STC8H1K24   |        |                    |
| STC8H1K28   |        | Recommend          |
| STC8H1K33   |        | Without USB Writer |

## 📜 开源许可

基于 [GNU General Public License v3.0](https://choosealicense.com/licenses/gpl-3.0/) 许可进行开源。

本设计已在 [中国版权保护中心](https://www.ccopyright.com.cn/) 登记注册。
