<div align="center">

# 🎙️ WakeVoice Portable

**A no-install, no-Python Chinese voice assistant for Windows.**

Download → unzip → double-click `WakeVoiceDesktop.exe` → talk to your computer and it does things for you. Wake word, speech recognition and basic replies all run **on your PC** — works offline, your voice never leaves the machine.

> 💬 Wake word → spoken command → done. No Python · No install · No cloud.

[![Release](https://img.shields.io/github/v/release/jsxxwhai/wakevoice-portable?color=blue&label=Download%20Portable)](https://github.com/jsxxwhai/wakevoice-portable/releases)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)
[![Stars](https://img.shields.io/github/stars/jsxxwhai/wakevoice-portable?style=social&label=Star)](https://github.com/jsxxwhai/wakevoice-portable)

</div>

> [!NOTE]
> 本仓库是**便携分发包**：`WakeVoiceDesktop.exe` + 完整运行库，无需安装 Python。完整源码、构建脚本与开发文档请看主仓库 [wakevoice](https://github.com/jsxxwhai/wakevoice)。本项目为原创独立开发，不包含、不模仿任何第三方品牌或受版权保护的内容，MIT 协议开源。

<img src="assets/og-card.png" alt="WakeVoice Portable social card" width="100%"/>

![WakeVoice Portable demo (animated)](assets/demo.gif)

## Quick Start

1. Download the latest `WakeVoiceDesktop-portable-vX.zip` from [Releases](https://github.com/jsxxwhai/wakevoice-portable/releases).
2. Unzip and double-click `WakeVoiceDesktop.exe`.
   - On first launch it automatically downloads a ~42 MB Chinese speech model (progress shown), then works fully offline.
   - Say the wake word **“你好伙伴”** (nǐ hǎo huǒbàn) → it replies **“我在”** → speak your command → it runs it automatically after a ~1.5 s pause.
3. Press `Esc` at any time to interrupt or stop the current task.

> Full Chinese guide is inside the zip: `使用说明.txt`.

## What you can say

- “打开记事本 / 打开计算器 / 打开 example.com” — open apps & websites
- “现在几点 / 今天星期几” — date & time
- “读一下屏幕” — read the screen (OCR)
- “拜拜” — end the conversation

## Features

- 🎙️ **Hands-free** — wake word + spoken command, then it acts after a short pause; no keyboard needed
- 🔒 **Private by default** — wake word, STT and basic replies run locally; no cloud account, no subscription
- 🧠 **Optional LLM** — point `config/config.yaml → llm` at any Chat Completions-compatible endpoint (or set the matching env var) for smarter answers; skip it and everything still works locally
- 🧩 **Extensible** — drop a `.py` skill into `skills/` to add a capability
- ⚡ **Portable** — no Python install, no admin rights needed to run

## System requirements

- Windows 10 / 11 (64-bit)
- A microphone
- Internet only on first run (to download the speech model); offline afterwards

## Configuration & FAQ

- **Custom wake word**: open `config/config.yaml` next to the EXE in a text editor and change `wake.word`.
- **Smarter replies**: in `config/config.yaml` → `llm`, set `base_url` / `api_key` for any Chat Completions-compatible service, or set the matching environment variables. Without it, all local skills still work.
- “Windows protected your PC” prompt → click “More info” → “Run anyway” (normal for unsigned apps).
- The complete Chinese manual lives inside the zip as `使用说明.txt`.

## Build it yourself

The portable bundle is produced from the main repository with one command:

```bash
python scripts/build_dist.py --clean --portable --zip
```

## License

[MIT](LICENSE) © WakeVoice Contributors

<details>
<summary><b>中文版 · 快速开始</b></summary>

## 快速开始（两步）

1. 下载最新 [Release](https://github.com/jsxxwhai/wakevoice-portable/releases) 里的 `WakeVoiceDesktop-portable-vX.zip`。
2. 解压后双击 `WakeVoiceDesktop.exe`：
   - 首次运行会自动下载约 42MB 中文语音模型（显示进度，之后可离线使用）；
   - 完成后自动进入监听，说 **“你好伙伴”** → 它答“我在” → 说出指令 → 停顿 1.5 秒自动执行。

> 想停止当前任务，随时按 `Esc`。

## 系统要求

- Windows 10 / 11（64 位）
- 麦克风
- 首次运行需联网（下载语音模型），之后可离线

## 常用指令

- “打开记事本 / 打开计算器 / 打开 example.com”
- “现在几点 / 今天星期几”
- “读一下屏幕”（可选 OCR）
- “拜拜” 结束对话

## 配置与常见问题

- **自定义唤醒词**：用记事本打开程序目录 `config/config.yaml`，修改 `wake.word`。
- **接入大模型让回答更聪明**：在 `config/config.yaml` 的 `llm` 段配置 `base_url` / `api_key`（任意兼容 Chat Completions 的服务端点）或设置对应环境变量；不配置也能正常使用本地技能。
- 提示“Windows 已保护你的电脑” → 点“更多信息”→“仍要运行”（未签名程序的正常提示）。
- 完整中文说明书在压缩包内 `使用说明.txt`。

## 如何自己打包

便携版由主仓库一条命令产出：

```bash
python scripts/build_dist.py --clean --portable --zip
```

</details>
