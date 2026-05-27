# Notion Launcher — Install Guide

Adds a Notion icon to your VS Code activity bar. One click opens Notion in VS Code's Simple Browser. Log in once, stays logged in.

## Install (1 minute)

### Option A — Drag & drop (easiest)

1. Open VS Code
2. `Cmd+Shift+X` (Extensions panel)
3. Drag `notion-launcher-0.0.1.vsix` onto the Extensions panel
4. Reload window when prompted

### Option B — Command Palette

1. `Cmd+Shift+P` → "**Extensions: Install from VSIX...**"
2. Select `notion-launcher-0.0.1.vsix`
3. Reload window

### Option C — Terminal

```bash
code --install-extension /path/to/notion-launcher-0.0.1.vsix
```

## Use it

1. Click the **N** icon in the left activity bar
2. First time only: log in to Notion inside the Simple Browser tab that opens
3. Done — next time, one click opens Notion already logged in

## Pin a specific page as default (optional)

If you want a specific Notion page to open by default (e.g. your team wiki):

- Click the Notion icon → side panel shows **"Set default URL..."** button
- Or `Cmd+Shift+P` → "**Notion: Set Default URL**"
- Paste the URL of the Notion page you want as default

## Recommended: bind to a keyboard shortcut

For one-tap access without opening the side panel:

1. `Cmd+Shift+P` → "**Preferences: Open Keyboard Shortcuts (JSON)**"
2. Add:

```json
{
  "key": "cmd+shift+n",
  "command": "notionLauncher.open"
}
```

Now `Cmd+Shift+N` opens Notion in any VS Code window.

## Troubleshooting

**Icon doesn't show up after install:**
- Fully quit VS Code (`Cmd+Q`) and reopen
- If still missing, check `Cmd+Shift+P` → "**Developer: Show Running Extensions**" and look for "Notion Launcher"

**Login keeps asking every time:**
- Simple Browser cookies sometimes reset on VS Code updates
- Just log in once more; it'll persist again

**Want to change the default URL back:**
- Run `Notion: Set Default URL` and paste `https://www.notion.so/`
