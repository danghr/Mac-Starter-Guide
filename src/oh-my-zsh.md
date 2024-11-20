# 美化 Shell

默认的 Shell 确实太丑了，而且所有地方用一样的字体也会导致无法分辨关键信息。本节按照笔者的习惯，推荐使用 Oh My Zsh 和一些插件来让它更加好用。

## 安装 Oh My Zsh

参考[镜像站的说明](https://mirrors.tuna.tsinghua.edu.cn/help/ohmyzsh.git/)，在终端中运行下述命令：

```bash
git clone --depth=1 https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git
cd ohmyzsh/tools
REMOTE=https://mirrors.tuna.tsinghua.edu.cn/git/ohmyzsh.git sh install.sh
cd ../.. && rm -rf ohmyzsh
```


## 使用插件、更改主题

功能丰富的插件是 Zsh 相比 Bash 的强大之处。笔者推荐 `zsh-syntax-highlighting` 和 `zsh-autosuggestions` 两个插件，以实现代码高亮和自动补全。同时，默认的 `robbyrussell` 主题仅显示当前目录名称，而不显示用户名和完整目录，这在一些场景下可能不太方便。笔者推荐使用 `ys` 主题。

使用 Homebrew 安装 `zsh-syntax-highlighting` 和 `zsh-autosuggestions`：

```bash
brew install zsh-syntax-highlighting zsh-autosuggestions
```

使用文件编辑器打开 `~/.zshrc` 文件：

```bash
open ~/.zshrc
```

*Tip: 可以使用 `open` 命令打开文件或文件夹。Mac 将选择该文件的默认应用打开该文件。*

将第 11 行的 `ZSH_THEME="robbyrussell"` 修改为

```
ZSH_THEME="ys"
```

在文件结尾加上
```
source /opt/homebrew/share/zsh-autosuggestions/zsh-autosuggestions.zsh
source /opt/homebrew/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
```

按 Command-S 保存，然后关闭编辑器。关闭并重新打开终端即可使用插件和主题。


---

<small>
更新于 2024-11-20
</small>
