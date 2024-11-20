#  安装与卸载软件

## 安装软件

Mac 安装软件主要有三种方式
- 使用 Mac App Store
- 使用 Homebrew
- 手动运行安装包

推荐首先查找 Mac App Store 中是否有相应的软件。这是安装软件最安全、最方便的方式。微信、QQ、网易云音乐、QQ 音乐、腾讯会议、百度网盘、Microsoft Office、Final Cut Pro X、Logic Pro 等 App 均在 Mac App Store 中提供，也可以安装部分 iOS 和 iPadOS 的软件。关于 Mac App Store 的使用说明，请参见苹果技术支持的[文档](https://support.apple.com/zh-cn/111105)。

Homebrew 则如前文所述也是较为方便的安装软件的方法。阿里云盘、Visual Studio Code、Adobe Acrobat Reader、Keka、OBS、Steam、EndNote、Zotero 以及 Noto 字体均可通过 Homebrew 下载。

如上述两个方法均找不到相应的软件，或学校提供的版本需要特定的安装包（Office、EndNote 等可能会有这种问题），则可以通过安装包进行安装。Mac 下的安装包可以归为三种格式：

- `dmg`：最常见的安装包格式，大多在打开后会包含一个 App 文件和一个“应用程序”文件夹的快捷方式，将 App 文件拖入应用程序文件夹即可。也可能会包含一个 `pkg` 文件，打开安装即可。
- `pkg`：较为常见的安装文件格式。双击打开并按提示安装即可。
- App 文件：如果发现下载下来的应用就是一个单独的 App 文件，则将其手动拖入“应用程序”文件夹即可完成安装。

请参考[在 Mac 上安装和卸载来自互联网或光盘的 App](https://support.apple.com/zh-cn/guide/mac-help/mh35835/mac)。

少部分应用会将其安装程序包装为 App 文件，这种应用的安装方法更接近于 `pkg` 文件，双击打开后按提示操作即可。

如果看到一个警告对话框，提示正在安装无法识别的开发者开发的 App，请参阅[打开来自未知开发者的 Mac App](https://support.apple.com/zh-cn/guide/mac-help/mh40616/15.0/mac/15.0)。


## 卸载软件

对于使用 Homebrew 安装的软件，请使用 `brew uninstall` 命令卸载。

对于其他软件，请参考[在 Mac 上卸载 App](https://support.apple.com/zh-cn/102610)。


## 一些常用的软件推荐

以下均为笔者根据自己习惯长期使用的软件，仅供参考。

- IINA：基于 mpv 的播放器，支持比系统自带 QuickTime Player 更多的格式，采用与现代 macOS 相同的设计语言。可通过 `brew install iina` 安装
- Keka：基于 7-zip 的压缩解压工具，亦支持 zip、tar.gz 等格式的压缩解压，以及 rar 的解压。可通过 `brew install keka` 安装。
- Motrix：支持 HTTP、FTP、BitTorrent、Magnet 等格式的下载器。可通过 `brew install motrix` 安装。


## 运行 Windows 软件

Mac 通过一些特定的转译工具可以运行 Windows 软件，例如 [CrossOver](https://www.codeweavers.com/crossover) 和 [Whisky](https://getwhisky.app)，前者体验更好但是付费软件，后者则是免费的开源软件。

Mac 也可以通过虚拟机安装运行 Windows on ARM。常用的虚拟机软件包括 [Parallels Desktop](https://www.parallels.cn) 和 [UTM](https://mac.getutm.app)，同样是前者体验更好但是付费软件，后者则是免费的开源软件。如需制作 Windows 安装镜像（包括为其他电脑制作），可在 Mac App Store 中免费下载 [CrystalFetch](https://apps.apple.com/cn/app/crystalfetch-iso-downloader/id6454431289?mt=12)，亦可通过 `brew install crystalfetch` 安装。
