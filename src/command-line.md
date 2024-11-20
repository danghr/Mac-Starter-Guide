# 一旦适应就非常好用的命令行

macOS 内置了 Zsh 终端，其操作逻辑与 Linux 下的默认终端 Bash 较为相近，但支持通过更多配置达到更美观的效果或更多的功能。关于终端的使用，请参见[计算机教育中缺失的一课](https://missing-semester-cn.github.io/)，其中[课程概览与 shell](https://missing-semester-cn.github.io/2020/course-shell/) 一节介绍了常用的基础 shell 命令。

考虑到国内的网络情况，本指南均使用[清华大学开源软件镜像站](https://mirrors.tuna.tsinghua.edu.cn)提供的镜像进行安装。您也可以根据实际情况换用[中科大开源镜像站](https://mirrors.ustc.edu.cn)或其他镜像站。强烈建议依据本指南安装 [Homebrew](./homebrew.md)，本指南后续安装其他命令行工具时均会使用 Homebrew。


## 安装 Command Line Tools

Mac 仅自带少量命令行工具，而诸如 `git`、`gcc` 等工具均包含在 Command Line Tools 中。在安装 Homebrew、Oh My Zsh 等命令行工具前，通常也需要安装 Command Line Tools。

打开“终端”，在 shell 中输入

```bash
xcode-select --install
```

在弹出的窗口中同意协议，等待下载安装完成即可。
