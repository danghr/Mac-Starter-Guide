# 运行 Windows 软件

> 就（Windows on ARM + 高通 X Elite）目前的游戏兼容性来说，它恐怕都没有比 Mac 用 CrossOver 转译 Windows 游戏好多少。
>
> ——[极客湾对高通 X Elite 的评测视频](https://www.bilibili.com/video/BV1jJSzYTEbr/?t=1763)


## 使用兼容层

Mac（以及Linux）通过一些特定的转译工具可以运行 Windows 软件。这类软件将 Windows 系统 API 调用动态地翻译为 macOS 使用的 POSIX API，因此被称作兼容层。

macOS 下界面比较友好的兼容层工具主要包括 [CrossOver](https://www.codeweavers.com/crossover) 和 [Whisky](https://getwhisky.app)。前者体验更好但是付费软件，后者则是免费的开源软件。这两者的底层均是基于 [Wine](https://www.winehq.org)，同时使用 [Rosetta 2](https://support.apple.com/zh-cn/102527) 完成 x86 到 ARM64 的架构翻译，以及使用 [Game Porting Toolkit](https://developer.apple.com/games/game-porting-toolkit/) 完成 Windows 图形 API 向 macOS 图形 API 的翻译。

提示：

- 建议在 CrossOver 中打开 D3DMetal 以获得最好的性能。
- CrossOver 会自动安装中文字体以解决一部分常见软件（例如 Steam）显示中文的问题，但 Whisky 对中文应用的兼容性仍不太好。在 Whisky 主界面右下角“Winetrick”中运行“字体”选项卡里的 `cjkfonts` 可能能解决部分问题。建议使用各类应用的英文版以避免此类问题。
- Apple 于 2024 年 6 月推出了性能更好的[Game Porting Toolkit 2.0](https://developer.apple.com/games/game-porting-toolkit/)，如果有需要可以按提示注册 Apple Developer 后，在打开的 More Downloads 页面下载 Evaluation environment for Windows games 2.0 beta，打开后按照 Read Me.rtf 文件中的说明，根据自己使用的兼容层，在终端中运行相应命令即可。

*Tip：注册 Apple Developer 无需付费。*


## 使用虚拟机

Mac 也可以通过虚拟机安装运行 Windows on ARM。常用的虚拟机软件包括 [Parallels Desktop](https://www.parallels.cn) 和 [UTM](https://mac.getutm.app)，同样是前者体验更好但是付费软件，后者则是免费的开源软件。如需制作 Windows 安装镜像（包括为其他电脑制作），可在 Mac App Store 中免费下载 [CrystalFetch](https://apps.apple.com/cn/app/crystalfetch-iso-downloader/id6454431289?mt=12)，亦可通过 `brew install crystalfetch` 安装。


## 不建议长期依赖此方法使用 Windows 软件

由于涉及到对 API 和二进制代码的动态翻译，转译过程会导致一定的性能损失。对于二进制翻译而言，转译 64 位 x86 应用的性能损失通常可以接受，但转译 32 位 x86 应用可能会产生巨大的性能下降。macOS 早在数年前便已结束了对 32 位应用的支持，因此使用体验基本不存在问题，但转译 Windows 应用时，部分应用可能会出现明显的性能下降。此外，转译 Windows 应用运行的稳定性通常远不及原生应用，部分功能也会受到限制。

因此，只建议将转译作为临时解决方案，或仅用于解决个别软件的兼容性问题。如果发现您所需的大部分软件均没有 macOS 上的原生版本，建议您将其二手卖出后换回 x86 平台的机型。Mac 电脑的保值率普遍较高，而在 Windows 阵营中，[Lunar Lake 架构的 Intel Core Ultra 200V 系列处理器能提供媲美 MacBook 的续航](https://www.bilibili.com/video/BV1FN4VewEWp)，也有很多功耗虽高但性能更强、价格更便宜的选择。当然，无论如何都不建议选择搭载高通 X Elite 和 X Plus 处理器的 Windows 笔记本。


---

<small>
更新于 2024-11-20
</small>
