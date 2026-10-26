# Roblox Cache Cleaner Pro

> Frees the disk space Roblox never cleans up after itself.

**English** · [中文](#中文)

---

## English

Roblox keeps every asset it ever downloaded. After a few updates that folder can
grow to several GB, and the game starts to stutter. This tool finds that cache,
shows you how much it is, and deletes it in one click.

Windows 10 / 11 · 64-bit · No installation, no runtime, no admin rights

### Download

**[⬇ Download the latest release](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

Unzip it anywhere and run `Roblox Cache Cleaner Pro.exe`.

<!-- VIRUSTOTAL: replace the line below with your scan link, e.g.
[VirusTotal report](https://www.virustotal.com/gui/file/<sha256>) · SHA-256: `<hash>`
-->

> The executable is not code-signed. See [Antivirus](#antivirus) below.

### Screenshot

![Main window](docs/img/main.png)

### What it does

1. **Checks whether Roblox is running** — using `CreateToolhelp32Snapshot` /
   `Process32FirstW` / `Process32NextW`, the standard read-only process
   enumeration API. It reads the list of process names and nothing else. The
   game process is never opened.
2. **Deletes files inside five cache folders**, all under `%LOCALAPPDATA%\Roblox\`:

   ```
   rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
   ```

   The folders themselves are kept — only their contents are removed.

### What it does NOT do

The complete import list of the core module is five entries:

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

No `socket`, no `urllib`, no `requests`, no `subprocess`, no `winreg`.

It cannot reach the network, edit the registry, launch other programs, or read
or write game memory — **that code does not exist**.

It does not touch game files, saves, settings, or account data.

### Antivirus

The executable is **not code-signed**, and it is packed as a single file that
unpacks native modules at runtime. Both of those look suspicious to heuristic
scanners, so Windows Defender, Huorong, 360 and similar tools may flag it.

This is a false positive caused by the packaging method, not by anything the
program does. To allow it:

- **Windows Defender** — Windows Security → Virus & threat protection →
  Manage settings → Exclusions → Add an exclusion → File
- **Huorong** — tray icon → Trust Zone → Add file
- **360 / PC Manager** — click "Add to trust" in the popup, or restore it from
  the quarantine list

If you would rather not trust it: deleting the contents of
`%LOCALAPPDATA%\Roblox\rbx-storage\` by hand does exactly the same thing.

### FAQ

**Does it affect my account?**
No. It deletes local cache files. Nothing is uploaded, and Roblox rebuilds the
cache on its next launch.

**Do I need to close Roblox first?**
Yes — the Clean button is disabled while the game is running, so the tool will
not fight a live process.

**Can I undo it?**
Not directly, but the cache is not data you own — it is re-downloaded
automatically. The only cost is a slightly longer next load.

### Disclaimer

Not affiliated with, endorsed by, or supported by Roblox Corporation.
"Roblox" is a trademark of Roblox Corporation. This is an unofficial third-party
tool.

Contact: Aflyers@outlook.com

---

## 中文

Roblox 会把下载过的资源全部留着，几次更新之后缓存能堆到几个 GB，游戏也开始卡。
这个工具找出这些缓存、告诉你占了多少、一键删掉。

Windows 10 / 11 · 64 位 · 免安装 · 无需运行环境 · 无需管理员权限

### 下载

**[⬇ 下载最新版本](https://github.com/Lwithlll/roblox-cache-cleaner/releases/latest)**

解压到任意目录，双击 `Roblox Cache Cleaner Pro.exe`。

### 截图

![主界面](docs/img/main.png)

### 它做什么

1. **判断 Roblox 是否在运行** —— 用 `CreateToolhelp32Snapshot` /
   `Process32FirstW` / `Process32NextW`，Windows 标准的只读进程枚举接口。
   只读取进程名列表，从不打开游戏进程。
2. **删除 5 个缓存目录里的文件**，全部位于 `%LOCALAPPDATA%\Roblox\`：

   ```
   rbx-storage/    logs/    Downloads/    OTAPatchBackups/    tmp-capture-storage/
   ```

   目录本身保留，只清空里面的内容。

### 它不做什么

核心模块的全部 import 只有五个：

```python
import ctypes, os, re, shutil
from ctypes import wintypes
```

没有 `socket`、没有 `urllib`、没有 `requests`、没有 `subprocess`、没有 `winreg`。

它**没有能力**联网、改注册表、调用外部程序、读写游戏内存——这些代码根本不存在。

不修改游戏文件、存档、设置，也不碰账号数据。

### 杀毒软件

程序**未做代码签名**，且是单文件自解压结构，两者都会让启发式引擎警觉，
Windows Defender、火绒、360 等可能报毒。

这是打包方式导致的误报，不是程序行为有问题。加白方法：

- **Windows Defender** —— Windows 安全中心 → 病毒和威胁防护 → 管理设置 →
  排除项 → 添加或删除排除项 → 文件
- **火绒** —— 托盘图标 → 信任区 → 添加文件
- **360 / 电脑管家** —— 弹窗点「添加信任」，或从隔离区恢复

如果不放心：手动删除 `%LOCALAPPDATA%\Roblox\rbx-storage\` 里的内容，效果完全一样。

### 常见问题

**会影响账号吗？**
不会。删的是本地缓存，不上传任何数据，Roblox 下次启动会自动重建。

**需要先关掉 Roblox 吗？**
需要。游戏运行时「开始清理」按钮会自动禁用，避免和正在运行的游戏抢文件。

**能撤销吗？**
不能，但缓存不是你的数据，会自动重新下载，代价只是下次加载稍慢。

### 免责声明

本项目与 Roblox Corporation 无任何关联，未获其认可或支持。
「Roblox」是 Roblox Corporation 的商标。这是一个非官方第三方工具。

联系邮箱：Aflyers@outlook.com

---

Copyright © 2026. All rights reserved.
Binary redistribution is permitted. Re-uploading this build as your own work is not.
