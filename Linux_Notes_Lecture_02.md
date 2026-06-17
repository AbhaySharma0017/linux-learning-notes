# 🐧 Linux Notes — Lecture 02: Command Structure & How the Shell Works

---

## 📌 What are Commands?

Commands are **not magic words** — they are simply **small programs** installed somewhere on your computer.

- `date` → a program
- `cal` → a program
- `echo` → a program

> Every time you type a command, you are telling the shell to **find and run that program**.

---

## 🧱 The Linux Command Structure

All Linux commands follow this structure:

```
command  [options]  [inputs/operands]
```

| Part | Description | Example |
|---|---|---|
| `command` | Name of the program to run | `cal`, `date`, `echo` |
| `options` | Customize the behavior (start with `-`) | `-y`, `-u`, `--universal` |
| `inputs` | Data the command operates on (also called **operands**) | `2024`, `hello`, `12 2024` |

---

## 🔍 How the Shell Finds Commands — The PATH

When you type a command, the shell doesn't magically know where it is. It searches through a list of folders called the **PATH**.

### View your PATH:

```bash
echo $PATH
# Output: /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/bin:/snap/bin
```

Each folder is separated by a colon `:`. The shell searches **left to right** — it uses the **first match** it finds.

### How it works:

```
/usr/local/sbin → /usr/local/bin → /usr/sbin → /usr/bin → /bin → /snap/bin
       ↑
   Starts here, moves right until found
```

- If the command is found → it runs
- If not found in any folder → `command not found` error

> **Important:** If the same command exists in two folders, the **leftmost one wins**.

---

### `which` — Find where a command lives

```bash
which cal
# Output: /usr/bin/cal

which echo
# Output: /bin/echo

which which
# Output: /usr/bin/which
```

> Use `which` to confirm a command is installed and see exactly which version will run.

---

## 📥 Inputs (Operands)

- Not all commands require inputs — some are optional
- Inputs go **after** the command name (and after options)
- Multiple inputs are separated by a **space**

### Examples:

```bash
cal              # No input — shows current month
cal 2024         # One input — shows full year 2024
cal 12 2024      # Two inputs — shows December 2024
echo hello       # Input: hello
```

---

## ⚙️ Options

Options **customize** a command's behavior. They are usually letters preceded by a **dash `-`**.

### Short-form options (single letter, one dash):

```bash
date -u          # Show date in UTC/Universal Time
cal -y           # Show current year calendar
```

### Chaining short-form options together:

```bash
date -a -b -c    # Three separate options
date -abc        # Same thing — chained together (order doesn't matter)
date -cba        # Also the same result
```

### Long-form options (full word, two dashes `--`):

```bash
date -u           # Short form
date --universal  # Long form — same result, easier to read
```

> Long-form options **cannot** be chained together. They must each have their own `--`.

```bash
# Correct:
date --universal --option-two --option-three

# Short form can be chained:
date -abc
```

---

## ⚙️ Options with Their Own Inputs

Some options themselves need an additional input (value).

### Example with `cal`:

```bash
cal -A 1 12 2024
# -A = show months "After"
# 1  = how many months after (input to -A)
# 12 2024 = inputs to the cal command (December 2024)
# Result: Shows December 2024 + January 2025

cal -B 1 12 2024
# -B = show months "Before"
# Result: Shows November 2024 + December 2024

cal -A 1 -B 1 12 2024
# Result: November 2024 + December 2024 + January 2025
```

### Using `=` to link options with their inputs (where supported):

```bash
# Long form with = sign (cleaner to read)
command --after=1 --before=1

# Not all commands support this — check the man page
```

---

## 🔤 Case Sensitivity — Very Important!

**Everything in Linux is case-sensitive** — commands, options, and inputs.

```bash
date        # ✅ Valid
Date        # ❌ Invalid — capital D
DATE        # ❌ Invalid

date -u     # ✅ Valid — lowercase u = universal time
date -U     # ❌ Invalid — capital U is not the same option
```

> Always double-check the case of your commands and options.

---

## 📋 Full Command Structure Summary

```
command  -short_options  --long-options  option_input  command_input
```

### Real-world example:

```bash
cal -A 1 -B 1 12 2024
 │   │       │  └─── command inputs (month=12, year=2024)
 │   │       └────── input to -B option (1 month before)
 │   └────────────── -A option input (1 month after)  
 └────────────────── command name
```

---

## ⚡ Quick Reference Cheat Sheet

| Command / Concept | Description |
|---|---|
| `echo $PATH` | View the shell's search path |
| `which <command>` | Find which folder a command is in |
| `command input` | Pass input to a command |
| `command -o` | Short-form option |
| `command --option` | Long-form option |
| `command -abc` | Chain multiple short options |
| `command -A 1` | Option with its own input |
| `command --option=value` | Long-form option with value (where supported) |

---

## 💡 Key Takeaways from This Lecture

1. Commands are **programs** stored in folders on your system.
2. The shell searches the **PATH** left to right to find commands.
3. Use `which <command>` to see exactly where a command is stored.
4. Command structure is always: `command [options] [inputs]`
5. **Short options** use one dash (`-u`); **long options** use two dashes (`--universal`).
6. Short options can be **chained** (`-abc`); long options cannot.
7. Some options have their **own inputs** (e.g., `-A 1`).
8. Linux is **fully case-sensitive** — `date` ≠ `Date`.
9. **Next up:** Man pages — how to look up what any command can do.

---

*Notes based on Lecture 02 — Linux Command Structure & The Shell PATH*
