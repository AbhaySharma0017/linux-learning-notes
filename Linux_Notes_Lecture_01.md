# 🐧 Linux Notes — Lecture 01: First Steps with the Terminal

---

## 📌 What is the Terminal?

The **terminal** is a powerful tool that lets you issue **commands** directly to your computer. The computer reads these commands and executes them. It is one of the most important tools in Linux.

> Think of it as talking directly to your OS — no clicking, just typing.

---

## 🖥️ Opening the Terminal

| Method | How |
|---|---|
| Graphical | Right-click desktop → Open Terminal (varies by distro) |
| Keyboard Shortcut ⚡ | `Ctrl + Alt + T` |

---

## 🧱 How Linux Commands Work (The Pattern)

All Linux commands follow a **similar structure**:

```
command  [options]  [input/arguments]
```

- **command** → the action you want to perform (e.g., `cal`, `date`)
- **options** → customize the behavior, usually start with a dash `-`
- **input/arguments** → the data or value you pass to the command

> Understanding this structure is the foundation of mastering Linux. You don't memorize commands — you understand the pattern.

---

## 📋 Basic Commands Covered

### 1. `echo` — Print text to the screen

```bash
echo hello
# Output: hello

echo echoooooooo
# Output: echoooooooo
```

> **Use case:** Quickly print text, test variables, or debug scripts.

---

### 2. `cal` — Display a calendar

```bash
cal
# Shows current month with today's date highlighted

cal 2017
# Shows full calendar for the year 2017

cal -y
# Also shows the full calendar for the current year (using an option)
```

> **Key concept:** You can pass **arguments** (like `2017`) or **options** (like `-y`) to change command behavior.

---

### 3. `date` — Show current date and time

```bash
date
# Output: Day Month Date HH:MM:SS Timezone Year
# Example: Wed Oct 04 10:35:22 IST 2017
```

> **Use case:** Check system date/time; also heavily used in shell scripting.

---

### 4. `clear` — Clear the terminal screen

```bash
clear
```

**Keyboard shortcut (faster):** `Ctrl + L`

> The screen looks clean again — previous commands are not deleted, just scrolled out of view.

---

## 🕹️ Navigating Command History

### Using the Up/Down Arrow Keys

- Press `↑` (Up Arrow) → go back to the previous command
- Press `↓` (Down Arrow) → go forward in history
- Keeps cycling through all commands you've run in the session

---

### `history` — View all past commands

```bash
history
# Shows a numbered list of all commands run
```

**Example output:**
```
1  echo hello
2  cal
3  date
4  clear
```

---

### Re-running a Command from History

```bash
!1
# Runs command number 1 from history (e.g., echo hello)

!8
# Runs command number 8

!!
# Runs the most recent command again
```

---

### Clearing the History

```bash
history -c ; history -w
```

- `-c` → clears the in-memory history
- `-w` → writes the change permanently to the history file

> After this, only the `history` command itself will remain.

---

## 🚪 Closing the Terminal

| Method | How |
|---|---|
| GUI | Click the ✕ button |
| Command | `exit` |
| Keyboard Shortcut | `Ctrl + D` |

> `Ctrl + D` is the pro way — keeps your hands on the keyboard throughout.

---

## ⚡ Quick Reference Cheat Sheet

| Command | What it Does |
|---|---|
| `echo <text>` | Prints text to the screen |
| `cal` | Shows current month calendar |
| `cal <year>` | Shows full year calendar |
| `cal -y` | Shows current year calendar |
| `date` | Shows current date & time |
| `clear` | Clears the terminal screen |
| `history` | Lists all past commands |
| `!<number>` | Re-runs a command by history number |
| `!!` | Re-runs the last command |
| `history -c ; history -w` | Clears command history permanently |
| `exit` | Closes the terminal |

---

## 💡 Key Takeaways from This Lecture

1. Commands are typed in the terminal and executed by pressing **Enter**.
2. Commands can be **customized** using options (`-y`) and arguments (`2017`).
3. All commands follow the same pattern: `command [options] [input]`
4. Use **keyboard shortcuts** (`Ctrl+L`, `Ctrl+D`, `↑ arrow`) to work faster.
5. `history` and `!number` save time when re-running previous commands.
6. Understanding the **structure** of commands matters more than memorizing them.

---

*Notes based on Lecture 01 — Introduction to Linux Terminal & Basic Commands*
