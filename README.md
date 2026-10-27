# Roblox Cache Cleaner Pro

Roblox never deletes its cache. This does.

Windows 10 / 11, 64-bit. No installer, no admin rights, nothing to install first.

**English** · [中文](#中文)

---

## Download

**[Get the latest release](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

Unzip it anywhere and run `Roblox Cache Cleaner Pro.exe`.

[VirusTotal](https://www.virustotal.com/gui/file/2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759): 66 of 67 engines find nothing. The one that does is Bkav, and it's wrong. More on that below.

SHA-256: `2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759`

![Main window](docs/img/main.png)

## What it actually does

Two things.

**1. Checks whether Roblox is running.** If it is, the Clean button stays disabled. You don't get to fight a live process for its own files.

**2. Deletes the contents of five folders**, all under `%LOCALAPPDATA%\Roblox\`:

```
rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
```

The folders stay. Only what's inside them goes. Anything not on that list is never opened.

You can untick any of the five before cleaning, and the total on the right only counts what's ticked.

## What it doesn't do

Here's the entire import list from the core module. Not a summary, the whole thing:

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

No `socket`. No `requests`. No `subprocess`. No `winreg`.

So it can't go online, can't write to the registry, can't start other programs, can't read game memory. There is no code for any of it.

It also doesn't touch your game files, saves, settings or account.

## Antivirus

The exe isn't code-signed, and it's packed as a single file that unpacks itself at launch. Both of those look suspicious to scanners, so Defender, Huorong or 360 may pop up a warning.

That's a packaging problem, not a behaviour problem. But you shouldn't just take my word for it, so here's the VirusTotal report for the exact file you're downloading: [66 clean, 1 wrong](https://www.virustotal.com/gui/file/2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759).

The one flag is Bkav, a Vietnamese engine that's known for this. Its signature is `W32.Malware.7028EDDD`, which is generic, not a behaviour it observed.

If you want to allow it anyway:

- **Windows Defender** → Virus & threat protection → Manage settings → Exclusions → Add an exclusion → File
- **Huorong** → tray icon → Trust Zone → Add file
- **360 / PC Manager** → click "Add to trust" in the popup, or restore it from quarantine

Or don't run it at all. Deleting the contents of `%LOCALAPPDATA%\Roblox\rbx-storage\` by hand does the same thing.

## Questions

**Will this get me banned?**
No. It deletes local files. Nothing is uploaded, and Roblox rebuilds the cache next launch.

**Do I need to close the game first?**
Yes. The button won't let you start otherwise.

**Can I undo it?**
No. But it's cache, not your data. It comes back on its own, just slower the first time.

**Why is it so small?**
It only does one job. There's no updater, no telemetry, no background service.

## Disclaimer

Not affiliated with, endorsed by, or supported by Roblox Corporation. "Roblox" is a trademark of Roblox Corporation.

Something broken? Aflyres@outlook.com

---

## 中文

Roblox 自己不清缓存。这个工具清。

Windows 10 / 11，64 位。免安装，不用管理员权限，也不用先装别的东西。

## 下载

**[下载最新版本](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

解压到任意位置，双击 `Roblox Cache Cleaner Pro.exe`。

[VirusTotal 报告](https://www.virustotal.com/gui/file/2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759)：67 家引擎里 66 家没报。报的那家是 Bkav，它报错了。

SHA-256：`2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759`

![主界面](docs/img/main.png)

## 它到底做什么

就两件事。

**一、看 Roblox 在不在运行。** 在运行的话「开始清理」按钮点不了。不跟正在跑的游戏抢文件。

**二、删掉五个目录里的东西**，都在 `%LOCALAPPDATA%\Roblox\` 下面：

```
rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
```

目录留着，只清里面的东西。这个清单之外的，一概不碰。

清理前可以取消勾选任意几项，右边的合计只算你勾上的部分。

## 它不做什么

核心模块的 import 就这几行。不是概括，是全部：

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

没有 `socket`，没有 `requests`，没有 `subprocess`，没有 `winreg`。

所以它联不了网、写不了注册表、起不了别的程序、读不了游戏内存。这些代码根本不存在。

游戏文件、存档、设置、账号数据，它也不碰。

## 杀毒软件

exe 没做代码签名，而且是单文件自解压，启动时会释放出东西来。这两点都容易让杀软弹窗，Defender、火绒、360 都可能。

这是打包方式的问题，不是行为的问题。但光我说没用，你下载的那个文件在 VirusTotal 上是 [66 家干净、1 家误报](https://www.virustotal.com/gui/file/2c17052d89a5d1052d0571be7f82f6be75f9a8c7d58393c6ea6dd580e1311759)。

报的那家叫 Bkav，越南的引擎，这类误报挺出名。它给的签名是 `W32.Malware.7028EDDD`，通用签名，不是真检测到什么行为。

还是想加白的话：

- **Windows Defender** → 病毒和威胁防护 → 管理设置 → 排除项 → 添加或删除排除项 → 文件
- **火绒** → 托盘图标 → 信任区 → 添加文件
- **360 / 电脑管家** → 弹窗点「添加信任」，或从隔离区恢复

或者干脆别用。手动删 `%LOCALAPPDATA%\Roblox\rbx-storage\` 里的内容，效果一样。

## 常见问题

**会被封号吗？**
不会。删的是本地文件，不上传任何东西，游戏下次启动自己重建。

**要先关游戏吗？**
要。不关的话按钮不让你点。

**能撤销吗？**
不能。但那是缓存不是你的数据，会自己回来，只是下次加载慢一点。

**为什么这么小？**
它只干一件事。没有更新器，没有统计上报，没有后台服务。

## 免责声明

本项目与 Roblox Corporation 无任何关联，未获其认可或支持。「Roblox」是 Roblox Corporation 的商标。

出问题了？Aflyres@outlook.com

---

Copyright © 2026. All rights reserved.
Binary redistribution is permitted. Re-uploading this build as your own work is not.
