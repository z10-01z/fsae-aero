# 开始使用

1. 从 [Releases](https://github.com/z10-01z/fsae-aero/releases) 下载 Windows ZIP 及其 SHA256 文件。
2. 可用 PowerShell 的 `Get-FileHash 文件名.zip -Algorithm SHA256` 比较下载摘要。
3. 完整解压到自己的可写目录，运行 `FSAE_Aero.exe`；不要只复制 EXE，`_internal` 内运行库须保留。
4. 程序默认在旁边的 `workspace` 创建输入、项目、配置和结果目录。也可通过 `FSAE_Aero.exe --workspace "D:\AeroWorkspace"` 指定工作区。
5. 从“帮助 → 关于”记录构建号。保存新项目，再按左侧工作流操作。

升级时保留旧目录，将新版本解压到新目录；通过项目菜单打开自己的项目副本。工作区中含外部路径引用，备份时不要只复制项目JSON而丢弃其引用的数据。需要回退时使用旧程序和事先保存的项目副本。

CATIA、WSL及OpenFOAM均需单独安装。没有计算环境时可以先熟悉项目、参数和已有报告；环境检查通过不代表车型或工程精度通过。

程序没有数字签名时系统可能显示发布者未知；请仅使用本仓库Release并核对摘要。不要关闭系统安全功能来运行来源不明的文件。
