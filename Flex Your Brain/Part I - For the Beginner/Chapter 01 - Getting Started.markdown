# Chapter 01 - Getting Started

1.  Computer hardware is a bare machine with no intelligence of its own. An operating system like UNIX is a special software which provides it with basic intelligence. This intelligence is used to provide services for both the programs and users.

    Services for programs include:

    -   Scheduling CPU time.

    -   Allocating main memory.

    -   Accessing hardware devices such as hard-drive, printers etc.

    Services for users include:

    -   File management (copying and deleting files, creating directories).

    -   Determining other users currently logged-in on system or local network.

    -   Sending e-mail messages, backing up files etc.

---

2.  A program can't read a file by itself. Instead, it places a request to access the file to the operating system. The operating system in turn reads the file and makes the file data available to the program.

---

3.  The program is called user's login shell. Some of the popular shell programs available on a UNIX system are:

    -   **sh**: Bourne shell

    -   **csh**: C shell

    -   **ksh**: KornShell

    -   **bash**: Bourne Again Shell

---

4.  The output produced by executing `ls` command is saved in a file named _list_ in the current directory.

    The shell sees the redirection operator (`>`) when interpreting the command line. It opens a named file following the redirection operator (here, _list_). Next, the command `ls` is run, which reads the directory contents. The shell has manipulated things such that the output of the `ls` command doesn't go to the terminal, but is written to the file opened by the shell.

---

5.  The shell programming syntax requires that there be no spaces on either side of the `=` operator.

    When entering `x =10`, `x` is treated as a command by the shell. As (in the default installation) there's no command named `x`, the shell shows an error message stating that the command couldn't be found.

    A similar error occurs in case `x= 10` is entered, where `10` is treated as a command. The shell tries to locate and execute it but fails to do so. The `x=` part is seen as a variable assignment valid only for the scope of `10` command.

---

6.  Two empty files named _README_ and _readme_ are created in the current directory.

    If either of the two files exists already, it is replaced by an empty file.

    When running the commands on a case-insensitive file-system (which is the case with default installation of macOS), only one file named _README_ is created.

---

7.  (i). `who`: Lists all the users currently logged in. It produces a multi-columnar output showing a user's login name, terminal name, date & time of the last login, and hostname (only in Linux) if not local.

    `tty`: Prints the file name of the terminal connected to the standard input.

    (ii). `ps`: Lists the running processes associated with the logged-in user. The output differs slightly between macOS and Linux.

    In macOS, `ps` command displays a header line, followed by lines containing information about all of user processes that have controlling terminals.

    In Linux, `ps` command displays information about a selection of the active processes.

    (Above information is extracted from the man pages available on the respective operating system)

    `echo $$`: Prints the integer **PID** (Process ID) associated with the running shell process.

---

8.  `Control + d` key sequence, `logout` and `exit`. `exit` command is guaranteed to always work.

---

9.  A user's user-id is used to uniquely identify her in the operating system.

    It is associating with any file or process created by the user.

---

10. Directories, devices, terminals and printers are all represented as files in the UNIX file-system.

---

11. Some of the duties of a systems administrator are:

    -   Backing up files.

    -   Restoring the system to a usable state in case of a crash.

    -   Startup, shutdown and maintenance of the system.

    -   Creating and administering user accounts.

    -   Updating system date.

---

12. AT&T and University of California, Berkeley (UCB).

---
