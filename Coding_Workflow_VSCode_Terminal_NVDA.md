# Coding Workflow: VS Code + Terminal + NVDA

This workflow is based on current course folder structure: a course folder with subfolders organized by week, used to manage assignments and synced to GitHub. This is how the workflow is defined for this course, which we can try as a pilot.
Feel free to adapt it to whatever structure feels most natural to you going forward.

The goal of this workflow is to reduce the number of times to switch between panels. Wherever possible, tasks are done from the terminal instead of navigating the VS Code interface.

Tools: Windows / Terminal - GitBash/ VS Code

---

## 1. Open VS Code 

- Lauch VS Code
- `Ctrl+` `  - open the integrate terminal inside VS Code

## 2. Confirm and navigate to the correct working directory

- `pwd` — confirms the current directory; NVDA reads the full path aloud
- `cd` into this week's folder, for example: `cd ~/laras/CLMT5045/week3`
- `ls`  — lists the files already in this week's folder

## 3. Identify which panel is active

- `Fn+Alt+F1` — Accessibility Help, announces your current location and available actions
- `Fn+F6` / `Shift+F6` — move focus between panels (editor, terminal, sidebar) if needed

## 4. Create or open a file — prefer the terminal over VS Code navigation

- Create a new file directly from the terminal: `touch filename.py` (Git Bash)
- Open a file directly into the editor from the terminal: `code filename.py`
- Alternative — from within the editor: `Ctrl+P`, type the filename, `Enter` / `Ctrl+N` — Create a new file

## 5. Working with open files in the editor

- `Ctrl+S` — save
- `Ctrl+W` — close the current tab
- `Ctrl+PageDown` / `Ctrl+PageUp` — switch between open file tabs (right / left)

## 6. Write code

- Use autocomplete suggestions: after typing part of a command, press `Ctrl+Up` / `Ctrl+Down` to browse suggestions instead of typing the full syntax from memory
- `Ctrl+F` — search for a specific word, variable name, or character within the current file
- `Ctrl+G` — jump to a specific line number; NVDA announces the new position

## 7. Run the script

- In the terminal: `python filename.py`
- `Fn+Alt+F2` — open accessible view to read the output
- `Caps Lock+Up` / `Caps Lock+Down` — move between output lines
- `Escape` — close accessible view

## 8. Check for errors

- `F8` — jump to the next error or warning; NVDA announces it
- `Shift+F8` — jump to the previous error or warning
- `Ctrl+F` — alternatively, search for a known error keyword in the file
- Note the line number mentioned in the error
- `Ctrl+G` — jump back to that line in the editor

## 9. Edit, save, re-run (the core loop)

- Make the fix in the editor
- `Ctrl+S` — save
- Return to the terminal and re-run: `python filename.py`
- Repeat steps 7–9 until the output is correct

## 10. Save output as files, not just terminal display

- For text or data results, write the output to a file instead of relying only on what shows up in the terminal:
  ```python
  with open("output_week3.txt", "w") as f:
      f.write(str(result))
  ```
- For charts, save the figure instead of just displaying it:
  ```python
  plt.savefig("chart_week3.png")
  ```

## 11. Package your work for submission — README.md

- Create a short `README.md` file in the week's folder listing the files and a one-line description of each. You don't need to copy file contents into it — just reference them and add a short description:
  ```markdown
  # Week 3

  - script.py — analysis script
  - output_week3.txt — printed results
  - chart_week3.png — CO2 trend chart (see description below)

  Chart description: CO2 levels show a steady upward trend from 1958 to 2020, with a seasonal oscillation pattern overlaid on the long-term increase.
  ```

## 12. Sync to GitHub

- `git add .`
- `git commit -m "description of changes"`
- `git push`
