# Chromium源码下载

官方文档

[Checking out and Building Chromium for Windows](https://chromium.googlesource.com/chromium/src/+/main/docs/windows_build_instructions.md)

下载安装Visual Studio 2022

> You must install the “Desktop development with C++” component and the “MFC/ATL support” sub-components.
> 

> You must have the version 10.0.20348.0 [Windows 10 SDK](https://developer.microsoft.com/en-us/windows/downloads/sdk-archive/) installed.
> 

启用Debugging Tools

> Control Panel → Programs → Programs and Features → Select the “Windows Software Development Kit” → Change → Change → Check “Debugging Tools For Windows” → Change.
> 

下载depot_tools

[https://storage.googleapis.com/chrome-infra/depot_tools.zip](https://storage.googleapis.com/chrome-infra/depot_tools.zip)

配置环境变量

```bash
PATH=C:\src\depot_tools:$PATH
DEPOT_TOOLS_WIN_TOOLCHAIN=0
```

运行gclient

```bash
gclient
```

调整python环境变量

配置Git

```bash
$ git config --global user.name "My Name"
$ git config --global user.email "my-name@chromium.org"
$ git config --global core.autocrlf false
$ git config --global core.filemode false
$ git config --global branch.autosetuprebase always
```

创建目录

生成.gclient文件

```bash
gclient config https://chromium.googlesource.com/chromium/src.git
gclient config --cache-dir C:\chromium_git_cache https://chromium.googlesource.com/chromium/src.git
```

获取源码

[Chromium Dash](https://chromiumdash.appspot.com/releases?platform=Windows)

```bash
gclient sync --revision src@{rev} --with_tags --with_branch_heads
```