# 1. Keyboard Shortcuts for VS Code (Working in progress)

### Initial setup

Before using accessibility shortcuts, enable Screen Reader Mode so VS Code optimizes its output for NVDA. You only need to do this once:

1. Press `Ctrl+Shift+P` to open the command palette
2. Type: Open User Settings JSON
3. Press `Enter`
4. Add this line inside the curly braces: `"editor.accessibilitySupport": "on"`
5. Press `Ctrl+S` to save

After this, VS Code will show "Screen Reader Optimized" in the status bar every time it opens.

### Accessbility & Help

- `Ctrl+` ` — Open a terminal
- `Fn+Alt+F1` — Accessibility help 
- `Alt+F2` — Read the full python scripts in accessible view, with code check results
- `Ctrl+Shift+O` — Move between commands inside the accessible view (pending)
- `Escape` — Close the accessible help/view

### Reading terminal output

- `Ctrl+Up` — Open accessible view of terminal
- `Caps Lock+Up` or `Caps Lock+Down` — Move up or down between lines in accessible view
- `Ctrl+Down` — Close the accessible view of terminal

### Navigation between panels

- `Ctrl+Shift+P` — Command palette: run any VS Code command by name
- `Fn+F6` — Move focus to the next panel (for example, editor, terminal, sidebar)
- `Fn+Shift+F6` — Move focus to the previous panel
- `Ctrl+1` — Return focus to the editor

### Working with files

- `Ctrl+N` — Create a new file
- `Ctrl+P` — Quick open: search and open a file by name
- `Ctrl+S` — Save the current file
- `Ctrl+W` — Close the current editor tab

### Markdown files

To switch a Markdown file from preview mode to edit mode:
1. Press `Ctrl+Shift+P` to open the command palette
2. Type: Reopen Editor with Text Editor
3. Press `Enter`

### Errors and code suggestions (pending)

- `Fn+F8` — Go to the next error or warning 
- `Shift+F8` — Go to the previous error or warning

### Setting Caps Lock as the NVDA modifier key

By default the NVDA modifier key is `Insert`. To also use `Caps Lock`:

1. While NVDA is running, press `Insert+N` to open the NVDA menu
2. Select Preferences, then select Settings
3. In the left panel, select Keyboard
4. Under NVDA Modifier Keys, check the box next to Caps Lock
5. Select OK to save

After this change, both `Insert` and `Caps Lock` work as the NVDA modifier key, whcih can be used for reading the Terminal in the accessible view.
