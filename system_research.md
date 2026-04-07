
# Android 系统底层研究笔记

## Zygote 进程启动流程
1. `init` 进程解析 `init.rc` 启动 `app_process`。
2. `AndroidRuntime.cpp` 初始化 ART 虚拟机。
3. `ZygoteInit.java` 预加载系统资源和类。
4. 进入 `ZygoteServer.runSelectLoop()` 等待 Socket 请求。

## LSPosed Hook 原理
- 基于 ART 虚拟机的 `EntryPoint` 替换。
- 动态修改 `ArtMethod` 结构体中的 `native_method_` 指针。
