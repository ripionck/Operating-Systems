## Command Line Interface (CLI) Overview

A **Command Line Interface (CLI)** is a text-based interface that allows users to interact with a computer system by typing commands. It is a fundamental way to communicate with computers, especially in environments where graphical interfaces are not available or are less efficient.

### Components of a CLI

1. **Prompt**: This is the text displayed by the system to indicate where the user can input commands. It often includes information like the current user, hostname, and directory path.

   **Example**: `ubuntu@chopin:~$`

2. **Command**: The user inputs a command, which can be either an internal (built-in) command or an external command that runs an executable file.

3. **Parameters**: These are additional inputs provided to the command, such as arguments or options, which modify how the command operates.

4. **Input/Output Streams**:
   - **STDIN (Standard Input)**: Typically associated with keyboard input.
   - **STDOUT (Standard Output)** and **STDERR (Standard Error)**: Used for displaying output and error messages, respectively.

### How CLI Works

1. **User Interaction**: Users type commands into the terminal or command prompt.
2. **Command Execution**: The CLI interprets the command and executes it, either by running a built-in function or launching an external program.
3. **Output Display**: The results of the command are displayed on the screen.

### CLI Representation

Here's a simple representation of how a CLI works:

```
[User]@[Hostname]:[Current Directory]$ command param1 param2
```

- **[User]**: The current user logged in.
- **[Hostname]**: The name of the computer.
- **[Current Directory]**: The path of the directory where the command is being executed.
- **$**: The prompt symbol indicating where the user can input commands.
- **command**: The command to be executed.
- **param1, param2**: Parameters or options for the command.

### Example

If you want to list all files in the current directory, you would use the `ls` command:

```
ubuntu@chopin:~$ ls
```

This command will display a list of files and directories in your home directory.

### CLI vs. GUI

While **Graphical User Interfaces (GUIs)** provide a visual interface with icons and menus, CLIs rely solely on text-based input and output. CLIs are often preferred for tasks requiring efficiency, automation, or when working remotely, as they can be more precise and faster for experienced users.
