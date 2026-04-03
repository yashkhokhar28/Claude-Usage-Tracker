![Windows](https://img.shields.io/badge/platform-Windows-blue)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

# Claude Usage Tracker

A lightweight Windows taskbar widget that shows your Claude Code usage at a glance.

It sits in your taskbar with smooth, Claude-branded progress bars showing how much of your usage window remains — no need to open the terminal or the Claude site.

## Features

- **5h bar** — your current 5-hour Claude usage window
- **7d bar** — your current 7-day window
- Live countdown until each limit resets
- Smooth, color-coded progress bars (terracotta → amber → red as usage increases)
- Native taskbar widget + system tray icon with percentage badge
- **One-click login** — right-click → "Login via Claude Code" if not authenticated
- Falls back to browser login if Claude Code CLI is not installed
- Dark and light mode support
- Multi-language support (English, Spanish, French, German, Japanese)
- Auto-update via GitHub Releases or WinGet

## Requirements

- Windows 10 or Windows 11
- A Claude account (Pro, Max, Teams, Enterprise, or Console)
- Claude Code CLI recommended but not required for initial login

## Install

### WinGet

```powershell
winget install YashKhokhar.ClaudeUsageTracker
```

### Manual

Download `claude-usage-tracker.exe` from the [Releases](https://github.com/yashkhokhar28/Claude-Usage-Tracker/releases) page and run it directly.

### Build from source

```powershell
# Install Rust if you don't have it
winget install Rustlang.Rustup

# Build
git clone https://github.com/yashkhokhar28/Claude-Usage-Tracker.git
cd Claude-Usage-Tracker
cargo build --release

# Run
.\target\release\claude-usage-tracker.exe
```

## Usage

Once running, the widget appears in your taskbar and as a tray icon.

- **Not logged in?** Right-click → **Login via Claude Code** (opens browser if CLI is not installed)
- **Drag** the left divider to reposition the widget
- **Right-click** for refresh, update frequency, settings, language, and exit
- **Left-click** the tray icon to toggle widget visibility
- Enable **Start with Windows** from the right-click menu for auto-launch

## Diagnostics

```powershell
claude-usage-tracker --diagnose
```

Log file: `%TEMP%\claude-usage-tracker.log`
Settings: `%APPDATA%\ClaudeUsageTracker\settings.json`

## Privacy

- Reads your local Claude credentials from `~/.claude/.credentials.json`
- Sends requests only to Anthropic's API (usage data) and GitHub (update checks)
- No analytics, no telemetry, no backend server
- Fully open source — inspect every line

## Author

Built by [Yash Khokhar](https://github.com/yashkhokhar28).

## License

MIT
