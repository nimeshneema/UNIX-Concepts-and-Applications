# Chapter 2 - The UNIX Architecture and Command Usage

1.  The UNIX architecture is based on a division of labor between two key agencies:

    -   **Kernel**

    -   **Shell**

    The kernel is the core of the operating system, a collection of routines that is loaded at boot time and communicates directly with the hardware. It manages system memory, schedules processes, and handles programs' requests to access hardware through system calls.

    The shell, on the other hand, is the command interpreter and acts as the interface between the user and the kernel. It takes user input from the keyboard, processes it, and then passes the commands to the kernel for execution. While there is only one kernel, there can be multiple shells running, one for each logged-in user.

2.  The two basic entities supporting the UNIX system are the file and the process.

    A **file** is simply an array of bytes, and the system considers everything, including directories, devices, terminals, and printers, as files.

    A **process** is the name given to a file when it is executed as a program. The process is a "time image" of an executable file, and like files, processes are part of a hierarchical tree structure.

    UNIX systems predominantly use text files because their behavior is mainly controlled by them. The system provides a vast array of text manipulation tools to edit these files without a full-fledged editor.

    Text files are also easier to read, understand and edit. UNIX started as an operating system targeted towards engineering community, and engineers often tinkered with configuration files and shared it with their peers. Using a text file format makes it easy to do so as well as analyse and debug them if need be.

3.  **Multiprogramming** means that UNIX can run multiple programs at once, competing for the CPU's attention. This can happen whether multiple users are running jobs or a single user is running multiple jobs.

    **Multiuser** means that the system's resources, such as the CPU, memory, and hard disk, are shared between multiple users, each of whom can be working on the system concurrently.

    **Multitasking** means that a single user can run multiple jobs at the same time, with one job running in the foreground and others running in the background.

4.  **System calls** are a handful of functions, written in C and built into the kernel, that user programs use to communicate with the kernel and access hardware. The power of UNIX lies in the fact that all flavors use the same system calls, which makes it easier to port software from one UNIX machine to another.

    In contrast to a Windows system, where C programmers must use standard library functions, the C programmer in the UNIX environment has complete access to both the system call library and standard library functions, making it a more powerful environment.

5.  Many UNIX commands are designed to perform simple rather than complex tasks as part of the "small is beautiful" philosophy adopted by its designers.

    This modular, building-block approach allows simple commands to be connected using pipes (`|`) to perform complex tasks. This makes it more flexible and versatile, as the number of combinations of usage is very large. If a command performed multiple functions and produced excessive output or was interactive, it would be difficult to use its output as input for another command.

6.  The statement is not entirely true.

    While the **wc** command is designed to count lines, words, and characters, it is designed to work with _any_ input, not just files.

    The pipe (`|`) symbol can connect two commands, feeding the output of one as input to another. For example, the command **ls | wc** uses the output of **ls** (the list of filenames) as input to **wc**, which then counts the number of files by counting the number of lines. In this case, **wc** is not working on a file but on the output from another command.

7.  Three major differences between UNIX commands and Windows programs are:

    -   **Command Naming and Case Sensitivity:** UNIX commands are typically short, single, lowercase words, and the system is case-sensitive (e.g., **ls** is a valid command but **LS** is not). Windows is generally not case-sensitive.

    -   **Command Architecture and Tools:** UNIX uses a building-block approach with hundreds of small, simple commands that can be combined using tools like pipes (`|`). Many Windows programs are more monolithic and are not designed to be easily chained together.

    -   **Command Documentation:** UNIX provides extensive online documentation through the **man** command and other tools (**apropos**, **whatis**). While Windows has help systems, the structure and availability of command-line documentation differ.

8.  A program file named `foo` might exist in the current directory, but when you try to execute it, the shell searches for the command in the directories specified by its `PATH` variable. The message `foo: command not found` appears because the current directory is not included in the `PATH` variable, or it is not listed in a location where the shell found and executed the command. To run the command, you would either need to add the current directory to the `PATH` or specify the full pathname, `./foo`.

9.  **Whitespace** refers to a contiguous string of spaces and tabs. The shell compresses multiple consecutive spaces or tabs to a single space.

10. To display the man pages for each of these, you would need to specify the section number in which the keyword is located. The `man` command searches in order, so specifying the section number is necessary to get the correct documentation when a keyword appears in multiple sections.

    The options used to specify section number differ between macOS and Linux. Form the usage forms are depicted below:

    -   **macOS**

        -   `man -s1 command`

        -   `man -s5 filename`

        -   `man -s2 system_call`

    -   **Linux**

        -   `man -s 1 command`

        -   `man -s 5 filename`

        -   `man -s 2 system_call`

    In Linux, the option `-s` is followed by a whitespace and the section number, while in macOS, the section number is appended to `-s` option.

11. In the `SYNOPSIS` section of a man page:

    -   The `|` character indicates that only one of the options on either side can be used. For `/usr/xpg4/bin/tail [ -f | -r]`, you can use either the `-f` option or the `-r` option, but not both.

    -   The three dots `...` (ellipsis) indicate that there can be more instances of the preceding word. For `ls [ file ... ]`, it means the `ls` command can be used with one or more filenames as arguments.

12. The **interrupt character** is used to stop a running program and bring back the prompt. This is often associated with the **[Ctrl-c]** or **[Delete]** keys.

    The **eof character** (end-of-file) is used to terminate input for commands that are expecting user input from the terminal. This is associated with the **[Ctrl-d]** key sequence.

13. To direct **man** to use a specific pager, such as `less`, you must set the `PAGER` shell variable and then export it. The commands to do this would be:

    ```
    PAGER=less ; export PAGER
    ```

    This setting is only valid for the current session.
