# Command-Line Tool xdirx

A keyboard-driven directory browser for the macOS terminal.  
Not affiliated with Apple or Xcode.  
Available in **German** and **English**.

---

## Why This Tool?

As a developer — especially when working with Claude Code or other AI assistants — you constantly need directory paths. Copying a path to the clipboard normally means: open a terminal, navigate, type `pwd`, select the output, copy. That costs time and focus.

xdirx addresses exactly that: launch the browser, navigate with arrow keys, press `Space` — path is in the clipboard. Done. No window switching, no typing, no selecting.

Once you've tried it, you won't want to copy paths any other way.

---

## The Problem with Directory Paths in the Terminal

Anyone who regularly switches between projects, config files, and working directories knows the drill: type `pwd`, select the output, copy — dozens of times a day. Finder and Terminal are two separate worlds; opening a directory in Finder and using the same path in Terminal always takes multiple steps. Favorite folders are completely missing from the standard shell, and every session starts from scratch.

xdirx solves exactly that: one single full-screen interface for navigation, clipboard, Finder, Terminal, and saved favorites.

---

## What Makes This Tool Special

### Clipboard with a Single Keystroke

The current directory path lands in the clipboard with `Space` — ready to paste into Claude Code, a terminal command, or a config file. No selecting, no right-clicking.

### Hotkey Slots — Favorite Folders Always at Hand

The tool provides **9 persistent hotkey slots** for frequently used directories. Once saved with a number key, these paths are available at any time: open in Terminal, open in Finder, jump directly, or copy path — all from an overlay with one more keystroke.

### Open Finder and Terminal Directly

Press `f` to open the selected directory instantly in Finder, `t` for a new Terminal window. No drag & drop, no right-clicking, no manual typing.

### Xcode Project Detection

Folders ending in `.xcodeproj` or `.xcworkspace` are automatically recognized and opened directly in Xcode when you press `Return` — not entered as a regular directory.

---

## What Works Well

xdirx is a focused tool for navigation and path actions:

| Task | Tool |
|------|------|
| Copy directory path to clipboard | xdirx |
| Open favorite folder with a single keystroke | xdirx |
| Open directory in Finder | xdirx |
| New Terminal window for a directory | xdirx |
| Open Xcode project directly | xdirx |
| Provide path for Claude Code | xdirx |
| Copy, move, or delete files | Terminal / Finder |
| Search and filter files | Terminal (find, grep) |

---

## Honest Limitations

- **No file operations:** xdirx navigates and copies paths — copying, moving, or deleting files is not intended.
- **No search:** There is no search function or filter option within the directory list.
- **Clipboard overwritten on launch:** The current path is automatically copied to the clipboard on startup — any previous clipboard content is lost.
- **No file preview:** File contents cannot be displayed.
- **Local filesystems only:** Network drives appear in the list but are not treated specially.

---

## 10 Reasons Why It's Worth It

1. Path in Claude Code in seconds — navigate, press Space, paste
2. 9 hotkey slots — the most important folders always at hand
3. Open Finder directly — no right-click, no drag & drop
4. Open Terminal directly — for any directory with a single key
5. Open Xcode projects directly — auto-detected, no searching
6. Full-screen UI — clean view, no scrolling through terminal output
7. No installer, no package manager — one file, done
8. Two languages — German and English, switch at any time
9. Persistent hotkeys — settings saved across sessions
10. Free, no accounts, no cloud — ready to use immediately

---

## 10 Things to Know (Honestly)

1. macOS only — no Windows, no Linux
2. No file operations — navigation and path actions only
3. No search function — scrollable directory list only
4. Clipboard content is automatically overwritten on startup
5. Hotkeys are saved globally — independent of the start directory
6. No preview mode for file contents
7. Very large directories can briefly delay rendering
8. Xcode Command Line Tools must be installed
9. Network drives appear but are not treated specially
10. Only one instance makes sense at a time — no multi-window concept

---

## Requirements

### Required — Without This, Nothing Works

**1. Mac with macOS Ventura 13 or newer**  
The tool is macOS-only. No Windows, no Linux.

**2. Xcode Command Line Tools**  
Run once in Terminal:

```bash
xcode-select --install
```

### Effort — One-Time, Not Recurring

| Step | Time Required |
|------|---------------|
| Install Xcode Command Line Tools | 2–5 min |
| Clone repository | < 1 min |
| Set execution permissions | < 1 min |
| Set up alias | 1 min |
| **Total** | **~5 minutes, one-time** |

After that: tool launches in seconds.

---

## Installation

### 1. Download Repository

```bash
git clone https://github.com/drapatzc/xdirx.git ~/GIT-Home/xdirx
```

### 2. Set Execution Permissions

```bash
chmod +x ~/GIT-Home/xdirx/xdirx
```

### 3. Set Up Alias (zsh)

```bash
echo 'alias xdirx="$HOME/GIT-Home/xdirx/xdirx"' >> ~/.zshrc
source ~/.zshrc
```

### 4. Test

```bash
xdirx
```

---

## Updating

```bash
cd ~/GIT-Home/xdirx
git pull
```

---

## Starting

Run the tool in any directory:

```bash
xdirx
```

The tool starts in the current working directory. The current path is automatically copied to the clipboard on startup.

---

## Usage

The tool displays a full-screen view with directory list, shortcut bar, and hotkey bar.

### Navigation

| Key | Action |
|-----|--------|
| `↑` / `↓` | Select entry above / below |
| `→` / `Return` | Enter directory / open file |
| `←` | Go to parent directory |
| `r` | Jump to root (start) directory |
| `a` | Select first entry in the list |
| `e` | Select last entry in the list |

### Clipboard

| Key | Action |
|-----|--------|
| `Space` | Copy current directory to clipboard |
| `z` | Copy selected entry path to clipboard |

### System Actions

| Key | Action |
|-----|--------|
| `f` | Open selected directory in Finder |
| `t` | Open selected directory in Terminal |

### Hotkeys

| Key | Action |
|-----|--------|
| `1` – `9` | Save current entry to hotkey slot |
| `Shift+1` – `Shift+9` | Open hotkey action overlay |
| `D` | Delete all hotkeys (with confirmation) |

**Hotkey Action Overlay** (after `Shift+1-9`):

| Key | Action |
|-----|--------|
| `T` | Open saved path in Terminal |
| `F` | Open saved path in Finder |
| `D` | Navigate directly to saved directory |
| `C` | Copy saved path to clipboard |
| `X` | Cancel |

### General

| Key | Action |
|-----|--------|
| `l` | Toggle language (German ↔ English) |
| `h` | Show help overlay |
| `Q` | Quit |
| `Escape` / `Ctrl+C` | Quit |

Settings are stored in `~/.xcode-developer-directory-settings.json`.

---

## User Interface

After launching, the tool displays a full-screen view:

```
╔══════════════════════════════════════════════════╗
║  XCode Developer Directory  v01.00.00            ║
║  Christian Drapatz                               ║
║  Path:       /Users/name/Projects                ║
║  Clipboard:  /Users/name/Projects                ║
╠══════════════════════════════════════════════════╣
║  [..] (Parent Directory)                         ║
║  [MyProject]                                     ║ ◀  selected
║  [AnotherFolder]                                 ║
║  MyProject.xcodeproj                             ║
║  README.md                                       ║
╠══════════════════════════════════════════════════╣
║  F:Finder | T:Terminal | Z:Clipboard | 1..9:Save ║
╠══════════════════════════════════════════════════╣
║  [1] /Users/name/Projects/App                    ║
║  [3] /Users/name/Documents                       ║
╚══════════════════════════════════════════════════╝
```

- **Header:** Current path and current clipboard content
- **Directory list:** Scrollable list (20 entries visible) with scrollbar
- **Shortcut bar:** All key bindings at a glance
- **Hotkey bar:** All saved hotkey slots

**Color coding:**
- Directories: blue `[Name]`
- Files: dimmed `Name`
- Xcode projects: italic dimmed `Name`
- Selected entry: yellow background, black text

---

## Architecture & Source Code

The binary (`xdirx`) is publicly available on GitHub. The actual source code is private — only the executable version is provided.

### Technical Details

| Property | Details |
|----------|---------|
| **Language** | Swift 5.9 (Swift Package Manager) |
| **Platform** | macOS 13+ (Executable Target) |
| **UI** | Full-screen terminal UI with ANSI colors, atomic single-buffer rendering |
| **Persistence** | JSON files at `~/.xcode-developer-directory-*.json` |
| **Signal Handling** | `Ctrl+C` / `Escape` quits the tool safely |
| **Dependencies** | None external — Foundation only |
| **Input** | Raw mode, UTF-8, CJK character width awareness, full escape sequence support |

---

## Developer

I build software for the Apple ecosystem — native iOS and macOS apps, my own games, and developer tools.

### Portfolio

**[christiandrapatz.de](https://christiandrapatz.de)**

### AI Apps

**[betterlocale.com](https://betterlocale.com)**

- [BetterLocale Crash](https://betterlocale.com/en-crash/)
- [BetterLocale Code](https://betterlocale.com/en-code/)
- [BetterLocale Store](https://betterlocale.com/en-store/)
- [BetterLocale Doc](https://betterlocale.com/en-doc/)
- [BetterLocale MarkDown](https://betterlocale.com/en-markdown/)

### Games

**[atomiumgames.com](https://atomiumgames.com)**

- [crazy-monsters.com](https://crazy-monsters.com)
- [tower-arena.com](https://tower-arena.com)
- [strategy-war.com](https://strategy-war.com)
- [battle-alliance.com](https://battle-alliance.com)

### Apps

**[onetwoapps.de](https://www.onetwoapps.de)**

- [scanbox-app.de](https://scanbox-app.de)
- [meinhaushaltsbuch.app](https://meinhaushaltsbuch.app)

---

## Author

Christian Drapatz — [christiandrapatz.de](https://christiandrapatz.de) — 2026

## License

This project is not released under an open-source license.  
All rights reserved.
