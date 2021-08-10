---
title: 工作环境配置备忘录
date: 2021-08-08 19:19:54
tags:
  - 工具
  - 配置
  - 备忘录
---

# 系统环境

我的系统是 Windows ，我习惯保持 Windows 桌面简洁 ，不在桌面上放置过多图标 ，所以我将一些工具配置在`path`环境变量中 ，可以在 shell 中快捷启动

### shell

由于我使用 Windows 系统 ，所以 shell 方面我使用新版的`power shell` ，较旧版功能更多 ，更加好用。例如新增的别名`rm` ，删除`node_modules`更快了。 我使用`Windows terminal`作为外壳 ，`oh-my-posh`作为美化工具。字体方面由于 git 提示符和 emoji 支持的缘故 ，大部分字体不支持这些特殊符号 ，所以我选用了`jet brains mono`

除此之外 ，windows 新增的`wsl(Windows subsystem for Linux)`功能使得 Linux 可以运行在 Windows 中 ，我使用发行版是`Ubuntu`。
现在 wsl 支持 gui 功能 ，可以依据[这篇文档](https://docs。microsoft。com/en-us/windows/wsl/tutorials/gui-apps) 进行配置。[WSL Windows Toolbar Launcher](https://github。com/cascadium/wsl-windows-toolbar-launcher/blob/master/README。md#troubleshooting) 是一个在状态栏快捷启动 wsl-gui 应用的工具 ，这个仓库的 readme 也讲了一些 wsl-gui 可能出现的 bug 以及解决方法

### 实用软件清单

- [nvm for windows](https://github。com/coreybutler/nvm-windows)  ， windows 版 nvm ，用来控制 node 版本
- [oh my posh](https://ohmyposh。dev/docs/pwsh)  ，用来美化 power shell
- [power shell](https://github。com/PowerShell/PowerShell)  ，powershell 的最新版 ，不同于 Windows 自带的 powershell v1
- [windows terminal](https://www。microsoft。com/zh-cn/p/windows-terminal/9n0dx20hk701?activetab=pivot:overviewtab)  ，
  微软官方的终端外壳
- [jet brains mono](https://www。jetbrains。com/lp/mono/)  ， jet brains 的字体 ，支持各种特殊符号 ，我用在终端
- [fira code](https://github。com/tonsky/FiraCode)  ， 一款开源的字体 ， 字体连字比较好看 ，我用在编辑器
- [draw io](https://draw。io/)  ，流程图工具 ，全部功能都集成在网站 ，当然也有客户端
- [typora](https://typora。io/)  ，所见即所得的 markdown 编辑器
- [power toys](https://github。com/microsoft/PowerToys)  ，微软官方的 Windows 功能增强工具
- [WinDbg preview](https://www。microsoft。com/zh-cn/p/windbg/9pgjgd53tn86?rtc=1)  ，微软官方的 Windows debug 工具 ，可以用来解析 minidump 文件 ，我用来查看引起系统蓝屏的来源
- [oh my fish](https://github。com/oh-my-fish/oh-my-fish)  ，美化 Linux shell
- [oh my zsh](https://ohmyz。sh/)  ，美化 Linux shell
- [nvm](https://github。com/nvm-sh/nvm)  ，用来在 wsl 中进行 node 版本控制

# 配置项

### nvm 和 npm

npm 的配置项主要为更改`registry`地址 ，或者设置代理 ，
使用`nvm`时 ，因为 npm 的配置文件在`~/。npmrc`中 ，切换 node 版本后并不会使配置项失效
大部分工具的配置文件在`~/`目录下 ，比如 git 的`。gitconfig` ，node repl 的历史记录`。node_repl_history` ，

### power shell

在 power shell 中输入`$profile`可以获取它的配置文件路径 ，这个文件可能没有被创建 ，需要手动创建。
power shell 的配置文件用来配置它的加载项 ，如`oh-my-posh`的主题和一些自定义的别名 ，函数

### wsl

wsl 的配置和 windows 下大同小异 ，仅下载时较为麻烦 ，可以通过换源 ，设置代理 ，git 安装等方法解决

### 编辑器

编辑器我同时使用`visual studio code`和`webstorm` ，vscode 更加轻量 ，更加开放 ，有一些特色功能 ，webstorm 相对 vscode 来说 ，内建的功能更智能

- 字体

  - 编辑器字体使用`fira code` ，不过它不支持中文字体 ，如果不设置一个次要字体用来显示中文 ，就会默认为宋体
  - 终端字体和 power shell 字体一致 ，使用 jet brains mono

- 插件/扩展
  - `代码片段生成`:我习惯使用`JavaScript (ES6) code snippets`这个扩展
  - `终端`:在 vscode 中可以使用`remote-ssh`来连接服务器进行远程开发 ，也可以使用`remote-wsl`在 wsl 中进行 Linux 环境下的开发
  - `格式化`:我习惯使用`prettier`
  - `主题`:颜色主题使用`One Dark Pro`或`Material Theme` ，文件图标主题使用`Material Icons` ，我个人比较喜欢 material 的风格
