*This project has been created as part of the 42 curriculum by juliosouza09.*

# Minishell

![minishell](https://github.com/user-attachments/assets/74b13aee-8453-473e-9a1e-b40d30cf2f85)

## Description

**Minishell** is a Unix shell implemented in **C**, developed as part of the **42 Common Core** curriculum.

The goal of this project is to recreate the core behavior of **Bash**, focusing on:
- Process creation and control
- File descriptor management
- Signal handling
- Command parsing and execution
- Interaction with the UNIX operating system

This project demonstrates a strong understanding of **systems programming**, **process lifecycle management**, and **low-level UNIX APIs**, while enforcing strict constraints on allowed functions and global state.

---

## Features

### Shell Behavior
- Interactive prompt display
- Command history using `readline`
- Executable resolution via `PATH`, relative paths, or absolute paths
- Correct exit status propagation (`$?`)

### Parsing & Expansion
- Environment variable expansion (`$VAR`)
- Exit status expansion (`$?`)
- Single quotes (`'`) to prevent all expansions
- Double quotes (`"`) allowing `$` expansion only
- Graceful handling of unsupported or unclosed syntax

### Redirections
- `<` input redirection
- `>` output redirection
- `>>` output append redirection
- `<<` heredoc with delimiter (without history update)

### Pipes
- Full pipeline support using `|`
- Correct stdin/stdout chaining across commands

### Built-in Commands
- `echo` (with `-n`)
- `cd` (relative or absolute path)
- `pwd`
- `export`
- `unset`
- `env`
- `exit`

### Signal Handling
- `ctrl-C` → interrupts command and shows new prompt
- `ctrl-D` → exits the shell
- `ctrl-\` → ignored (bash-like behavior)

Signal handling is implemented using **at most one global variable**, storing **only the received signal number**, ensuring safe separation between signal handlers and program state.

---

## Technical Constraints

- Written entirely in **C**
- Uses only authorized system calls and library functions
- No access to internal data structures from signal handlers
- No memory leaks in user-written code
- Uses **libft** where authorized

---

## Instructions

### Compilation

```bash
make
````

### Run

```bash
./minishell
```

### Clean build files

```bash
make clean
make fclean
```

### Recompile

```bash
make re
```

---

## What This Project Demonstrates

* Deep understanding of **UNIX process management**
* Safe and correct **signal handling**
* Robust **file descriptor control**
* Modular C design under strict constraints
* Ability to recreate complex system behavior from specifications

This project closely mirrors real-world shell behavior and provides strong foundations for **backend**, **systems**, and **infrastructure engineering roles**.

---

## Resources

### Technical References

* Advanced Programming in the UNIX Environment — W. Richard Stevens
* Bash Reference Manual
* Linux `man` pages (`fork`, `execve`, `pipe`, `dup2`, `wait`, `signal`)
* GNU Readline Documentation

### AI Usage Disclosure

AI tools were used **only as a learning assistant**, specifically for:

* Clarifying UNIX concepts (signals, pipes, process flow)
* Reviewing documentation references
* Improving code readability and documentation wording

All **architecture decisions, implementation, debugging, and final code** were written and validated manually.

---

## Notes

This project intentionally follows **only the required specifications**.
When behavior was ambiguous, **Bash** was used as the reference implementation.

---

## Author

**Júlio César**
42 Porto — Software Development
- GitHub: [https://github.com/juliosouza09](https://github.com/juliosouza09)
- LinkedIn: [https://linkedin.com/in/juliosouzadev](https://linkedin.com/in/juliosouzadev)

