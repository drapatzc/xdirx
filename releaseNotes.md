# Release Notes — XCode Developer Directory

## Version 01.00.00

### Initial Release

**Core Features:**
- Interactive terminal directory browser with keyboard navigation
- Automatic clipboard copy of the current path on launch
- Hotkey system: 9 persistent slots — save with 1–9, action menu with Shift+1–9
- Hotkey action overlay: open in Terminal, Finder, navigate, or copy to clipboard
- Quick keys: Space (current directory), z (selection), a/e (first/last entry)
- Root navigation with r (return to start directory)
- Open files with Return / → (macOS `open`)
- Open Finder with f, open Terminal with t
- Localization: German and English (toggle with l)
- Help screen with all key bindings (press h)
- Scrollbar for large directories (fixed 20-line content area)
- Path truncation from the left for long directory paths
- .xcodeproj / .xcworkspace displayed in bold italic

**Technical:**
- Self-contained binary — no external dependencies at runtime
- Localizable.xcstrings embedded directly in the binary (Base64)
- Swift 6, macOS 13+
- Flicker-free rendering via single atomic Darwin.write call
- Alt-screen buffer with full screen clear on launch
