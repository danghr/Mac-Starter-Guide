# 一旦适应就非常好用的命令行

macOS 内置了 Zsh 终端，其操作逻辑与 Linux 下的默认终端 Bash 较为相近，但支持通过更多配置达到更美观的效果或更多的功能。关于终端的使用，请参见[计算机教育中缺失的一课](https://missing-semester-cn.github.io/)，其中[课程概览与 shell](https://missing-semester-cn.github.io/2020/course-shell/) 一节介绍了常用的基础 shell 命令。Mac 还有非常强大的包管理器 [Homebrew](https://brew.sh)，不仅可以安装命令行应用，也可以安装大量常用的桌面应用。

考虑到国内的网络情况，在下面的安装过程中均使用[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn)进行安装，也可以根据实际情况换用[中科大开源镜像站](https://mirrors.ustc.edu.cn)或其他镜像站。


## 安装 Command Line Tools

Mac 仅自带少量命令行工具，而诸如 `git`、`gcc` 等工具均包含在 Command Line Tools 中。

打开“终端”，在 shell 中输入

```bash
xcode-select --install
```

在弹出的窗口中同意协议，等待下载安装完成即可。


## 安装 Homebrew

参照镜像站 [Homebrew](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew/)、[Homebrew Bottles](https://mirrors.tuna.tsinghua.edu.cn/help/homebrew-bottles/) 和 [PyPI](https://mirrors.tuna.tsinghua.edu.cn/help/pypi/) 镜像的说明，在终端中输入设置环境变量的命令：

```bash
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"
export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"
export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"
export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"
export HOMEBREW_PIP_INDEX_URL="https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
```

*Tip：可以将上述命令（包含换行）一次性粘贴到终端中，再按回车即可。下同。*

下载并运行安装脚本：

```bash
git clone --depth=1 https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/install.git brew-install
/bin/bash brew-install/install.sh
rm -rf brew-install
```

遇到要求输入密码的地方时，输入当前账户的登陆密码即可。注意 shell 在输入密码时没有显示。输入完成后按回车即可。

安装成功后需将 brew 程序的相关路径加入到环境变量中：

```bash
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> ~/.zprofile
eval "$(/opt/homebrew/bin/brew shellenv)"
```

同时也需要将上述环境变量的设置加入到环境变量文件中：

```bash
test -r ~/.zprofile && echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' >> ~/.zprofile
test -r ~/.zprofile && echo 'export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"' >> ~/.zprofile
test -r ~/.zprofile && echo 'export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"' >> ~/.zprofile
test -r ~/.zprofile && echo 'export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"' >> ~/.zprofile
test -r ~/.zprofile && echo 'export HOMEBREW_PIP_INDEX_URL="https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"' >> ~/.zprofile
```


## 使用 Homebrew

Homebrew的命令可分大致为以下几种：

- `brew search`：搜索软件包
- `brew info`：查看软件包信息
- `brew install`：安装软件包
- `brew upgrade`：升级软件包
- `brew reinstall`：卸载并重新安装软件包
- `brew uninstall`：卸载软件包
- `brew help`：查看帮助

下面以安装 Visual Studio Code 为例，展示这一流程：


### 搜索软件包

在终端中输入 `brew search visual-studio-code` 搜索是否有相应的软件包。

*Tip：一般使用软件英文名的全小写，且使用 `-` 代替空格，即可找到相应的软件包。如果找不到，可以尝试连写（如百度网盘 `baidunetdisk`）或缩写（如阿里云盘 `adrive`）。*

得到的结果如下：
```
==> Casks
visual-studio    visual-studio-code    visual-studio-code@insiders
```

*Tip: 若某个软件包后面有打勾，则说明已安装该软件包。*

*Tip: 部分命令行工具和桌面软件可能重名，请按照搜索结果，使用 `xxxx` 和 `homebrew/cask/xxxx` 进行区分。*


### 确认软件包信息

在终端中输入 `brew info visual-studio-code` 确认软件包信息：

```
==> visual-studio-code: 1.95.3 (auto_updates)
https://code.visualstudio.com/
Not installed
From: https://github.com/Homebrew/homebrew-cask/blob/HEAD/Casks/v/visual-studio-code.rb
==> Names
Microsoft Visual Studio Code
VS Code
==> Description
Open-source code editor
==> Artifacts
Visual Studio Code.app (App)
/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code (Binary)
==> Analytics
install: 28,957 (30 days), 83,924 (90 days), 323,447 (365 days)
```

### 安装软件包

确认是我们需要安装的软件之后，使用 `brew install visual-studio-code` 即可安装，按照提示完成安装即可。


### 更新软件包

对于通过 Homebrew 安装的一些不支持自动更新的软件，可通过 `brew upgrade` 命令手动进行更新。如果后面不加任何软件包名称，则会更新所有可以更新的软件包。

对于支持自动更新的软件，请使用软件内的自动更新功能。Homebrew 不会更新这些软件。


## 美化 Shell

默认的 Shell 确实太丑了，这里推荐一些配置和插件来让它更加好用。Oh My Zsh 提供了一系列针对 Zsh 的皮肤和主题。按照笔者的使用习惯，我推荐进行如下配置。

### 安装 Oh My Zsh

参考[镜像站的说明](https://mirrors.tuna.tsinghua.edu.cn/help/ohmyzsh.git/)，在终端中运行下述命令：

```bash
git clone --depth=1 https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git
cd ohmyzsh/tools
REMOTE=https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git sh install.sh
cd ../.. && rm -rf ohmyzsh
```


### 使用插件、更改主题

功能丰富的插件是 Zsh 相比 Bash 的强大之处。笔者本人推荐 `zsh-syntax-highlighting` 和 `zsh-autosuggestions` 两个插件，以实现代码高亮和自动补全。同时，默认的 `robbyrussell` 主题仅显示当前目录名称，而不显示用户名和完整目录，这在一些场景下可能不太方便。笔者本人推荐使用 `ys` 主题。

使用 Homebrew 安装 `zsh-syntax-highlighting` 和 `zsh-autosuggestions`：

```bash
brew install zsh-syntax-highlighting zsh-autosuggestions
```

使用文件编辑器打开 `~/.zshrc` 文件：

```bash
open ~/.zshrc
```

*Tip: 可以使用 `open` 命令打开文件或文件夹。Mac 将使用默认应用打开该文件。*

将第 11 行的 `ZSH_THEME="robbyrussell"` 修改为

```
ZSH_THEME="ys"
```

在文件结尾加上
```
source /opt/homebrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh
source /opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

按 Command-S 保存，然后关闭。关闭并重新打开终端即可使用插件和主题。

---

更新于 2024-11-20
