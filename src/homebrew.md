# Homebrew

[Homebrew](https://brew.sh) 是 macOS 环境中一款非常强大的包管理器。其不仅能安装各种命令行工具，也可以安装大量常用的桌面应用，能够节省大量查找安装包、下载和安装的时间。对于部分提供源代码的应用，如果预编译包安装失败，Homebrew 还会尝试下载源码编译，更是非常方便。


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


echo '# Set PATH, MANPATH, etc., for Homebrew.' >> ~/.zprofile
echo 'export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"' >> ~/.zprofile
echo 'export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"' >> ~/.zprofile
echo 'export HOMEBREW_API_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles/api"' >> ~/.zprofile
echo 'export HOMEBREW_BOTTLE_DOMAIN="https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles"' >> ~/.zprofile
echo 'export HOMEBREW_PIP_INDEX_URL="https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"' >> ~/.zprofile
export HOMEBREW_BREW_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/brew.git"
export HOMEBREW_CORE_GIT_REMOTE="https://mirrors.tuna.tsinghua.edu.cn/git/homebrew/homebrew-core.git"

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


### 卸载软件包

仍以 Visual Studio Code 为例，如需卸载，只需使用下述命令：

```bash
brew uninstall visual-studio-code
```


---

<small>
更新于 2024-11-20
</small>
