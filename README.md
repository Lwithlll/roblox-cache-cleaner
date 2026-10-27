# Roblox Cache Cleaner Pro

Windows 10 / 11, 64-bit

**English** · [中文](#中文)

## Download

**[Get the latest release](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

Unzip it anywhere after downloading.

## How to use

**1. Unzip, then double-click `Roblox Cache Cleaner Pro.exe`**

**2. The program checks whether Roblox is running.** If it is, close the game first, otherwise you may run into problems.

**3. Pick which items to clean before cleaning (all ticked by default)**

## Safety

[VirusTotal report](https://www.virustotal.com/gui/file/ca6057cfaf73988610ac4bfa0c13179030ec64fb7bdf0d8a08acc0684fa5d4c7): 66 of 67 engines report nothing.

SHA-256: `ca6057cfaf73988610ac4bfa0c13179030ec64fb7bdf0d8a08acc0684fa5d4c7`

The complete import list of the core module

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

No `socket`, `requests`, `subprocess`, `winreg`.

Cleaning only removes the five cache folders under %LOCALAPPDATA%\Roblox\

```
rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
```

Doesn't modify game files, saves, settings or account data.

## Antivirus

Because the exe has no code signature and is a single self-extracting file, it unpacks files at launch, which may cause antivirus software to block it, but the chance is low.

If it does get blocked, add it to the whitelist manually:

- **Windows Defender** → Virus & threat protection → Manage settings → Exclusions → Add an exclusion → File
- **Huorong** → tray icon → Trust Zone → Add file
- **360 / PC Manager** → click "Add to trust" in the popup, or restore it from quarantine

## Questions

**Does this affect my account's safety?**
No. It deletes local files, uploads nothing, and the game rebuilds the cache on its next launch.

**Do I need to close the game first?**
Yes, close the game first, otherwise you may run into problems in-game.

Not affiliated with, endorsed by, or supported by Roblox Corporation. "Roblox" is a trademark of Roblox Corporation.

Something broken? Aflyres@outlook.com

---

Copyright © 2026. All rights reserved.
Binary redistribution is permitted. Re-uploading this build as your own work is not.

---

## 中文

# Roblox Cache Cleaner Pro

Windows 10 / 11，64 位

## 下载

**[下载最新版本](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

下载完成后解压到任意位置

## 使用教程

**一、解压后双击启动 `Roblox Cache Cleaner Pro.exe`**

**二、程序会自动检测 Roblox 在不在运行。** 如正在运行，请退出 Roblox 再使用，避免问题

**三、清理前可任意勾选清理项（默认全部勾选）**

## 安全性

[VirusTotal 报告](https://www.virustotal.com/gui/file/ca6057cfaf73988610ac4bfa0c13179030ec64fb7bdf0d8a08acc0684fa5d4c7)：67 家引擎里 66 家无报错

SHA-256：`ca6057cfaf73988610ac4bfa0c13179030ec64fb7bdf0d8a08acc0684fa5d4c7`

核心模块的全部 import

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

不含 `socket`，`requests`，`subprocess`，`winreg`。

清理只删除 %LOCALAPPDATA%\Roblox\ 下五个缓存文件

```
rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
```

不修改游戏本体文件、存档、设置、账号数据

## 杀毒软件问题

由于 exe 无代码签名，而且是单文件自解压，启动时会释放出东西来，可能导致杀毒软件拦截，但概率较低。

如果导致拦截请手动添加白名单：

- **Windows Defender** → 病毒和威胁防护 → 管理设置 → 排除项 → 添加或删除排除项 → 文件
- **火绒** → 托盘图标 → 信任区 → 添加文件
- **360 / 电脑管家** → 弹窗点「添加信任」，或从隔离区恢复

## 常见问题

**会影响账号安全性吗？**
不会。删的是本地文件，不上传任何东西，游戏下次启动自己重建。

**要先关游戏吗？**
需要先关闭游戏，否则可能会出现游戏内问题

本项目与 Roblox Corporation 无任何关联，未获其认可或支持。「Roblox」是 Roblox Corporation 的商标。

出问题了？Aflyres@outlook.com

---

Copyright © 2026. All rights reserved.
Binary redistribution is permitted. Re-uploading this build as your own work is not.
