# VS Code: open `.md` files in a WYSIWYG editor by default

**What it does:** reading and editing markdown files in VS Code's default text editor is mildly painful for product people. This prompt configures VS Code so `.md` and `.markdown` files open in a Notion/Typora-style WYSIWYG editor (via the `cweijan.vscode-office` extension) and save back to clean markdown.

**Platform:** macOS, VS Code (or any fork that uses the same user settings path, e.g. Cursor — adjust the settings path if needed).

**How to use:** paste the prompt below into Claude Code. It will install the extension, update your user settings, and tell you to reload the window.

## Prompt

```
VS Code'da .md dosyalarının default olarak WYSIWYG markdown editörle (preview gibi
görünen ama üzerinde direkt yazabildiğim) açılmasını istiyorum. macOS kullanıyorum.

Aşağıdaki adımları sırayla yap:

1. VS Code CLI üzerinden "cweijan.vscode-office" eklentisini kur:
   "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" --install-extension cweijan.vscode-office

2. Kullanıcı settings.json dosyasını şu yola yaz (varsa içeriği bozma, sadece
   workbench.editorAssociations alanını ekle/güncelle):
   ~/Library/Application Support/Code/User/settings.json

   Eklenecek/güncellenecek alan:
   {
     "workbench.editorAssociations": {
       "*.md": "cweijan.markdownViewer",
       "*.markdown": "cweijan.markdownViewer"
     }
   }

3. Bana VS Code'da "Cmd+Shift+P → Developer: Reload Window" yapmamı söyle.
   Ayrıca workspace trust dialog'u gelirse "Yes, I trust the authors" demem
   gerektiğini hatırlat (custom editor o olmadan yüklenmez).

Bittiğinde .md dosyalarına tıkladığımda WYSIWYG editör açılacak — Notion/Typora
benzeri, üzerinde direkt yazabildiğim, kaydedince saf markdown'a dönen.
```

## English summary of the prompt

The prompt instructs Claude Code to:

1. Install the `cweijan.vscode-office` extension via the VS Code CLI.
2. Update `~/Library/Application Support/Code/User/settings.json` to associate `*.md` and `*.markdown` files with `cweijan.markdownViewer` — without clobbering existing settings.
3. Remind you to run `Cmd+Shift+P → Developer: Reload Window` and to accept the workspace trust dialog (the custom editor won't load without it).

After that, clicking any `.md` file opens it in a Notion/Typora-like editor; saving writes plain markdown back to disk.

## Notes

- For **Cursor** or other forks, swap the CLI path and the settings path:
  - Cursor CLI: `/Applications/Cursor.app/Contents/Resources/app/bin/cursor`
  - Cursor settings: `~/Library/Application Support/Cursor/User/settings.json`
- On Linux/Windows the settings path differs; adjust the prompt accordingly.

## Credit

Originally shared internally on Slack by the Insider Dispatcher community.
