# Linux Terminal Learning Notes

## Current Topic
- Bash shell
- Bash keyboard shortcuts
- Terminal navigation
- Command history and reverse search

---

# Bash Shell Basics

## What is Bash?
- Bash stands for **Bourne Again Shell**.
- It is a command-line shell commonly used on Linux systems.
- Bash allows users to interact with the operating system using commands.

---

# Terminal Auto-Completion

## Using `Tab`
- Pressing `Tab` attempts to auto-complete commands, filenames, or directories.
- Example:
  ```bash
  cd Doc


Pressing `Tab` may complete it to:

```bash
cd Documents/
```

## Using `Tab` Twice

* Pressing `Tab` twice shows all possible matches.
* Example:

  ```bash
  Desktop/  Documents/  Downloads/
  ```

## Benefits

* Faster typing
* Fewer spelling mistakes
* Helps discover files and commands

---

# Clearing the Terminal

## Using `clear`

```bash
clear
```

* Clears the terminal screen.

## Using `Ctrl + L`

* Keyboard shortcut for clearing the screen.
* Similar to the `clear` command.

## Important Note

* Clearing the screen does not erase command history.

---

# Bash Keyboard Shortcuts

## `Ctrl + A`

* Moves the cursor to the **beginning** of the command line.

## `Ctrl + E`

* Moves the cursor to the **end** of the command line.

## `Ctrl + R`

* Starts **reverse search** through command history.
* Useful for finding previously used commands.

## `Ctrl + G`

* Exits or cancels reverse search mode.

---

# Command History

## Arrow Keys

* `Up Arrow` shows previous commands.
* `Down Arrow` moves forward through command history.

## Reverse Search

* Activated with:

  ```bash
  Ctrl + R
  ```
* Searches command history as you type.

Example:

```bash
(reverse-i-search)`apt': sudo apt update
```

---

# Emacs Shortcuts in Bash

## Default Bash Keybindings

* Bash commonly uses **Emacs-style shortcuts** by default.

Examples:

* `Ctrl + A` → beginning of line
* `Ctrl + E` → end of line
* `Ctrl + R` → reverse search

---

# Vi and Vim Modes

## Vi/Vim Editing Mode

* Bash can also use **Vi-style keybindings** instead of Emacs shortcuts.
* Inspired by the `vi` and `vim` text editors.

## Difference

* Emacs mode uses shortcuts like `Ctrl + A`.
* Vi mode uses command and insert modes similar to Vim.

## Common Editors

* `vi` → older Unix text editor
* `vim` → improved version of vi

---

```
```
