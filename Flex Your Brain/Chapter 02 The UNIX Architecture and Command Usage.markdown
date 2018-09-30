01. The UNIX system divides the labor between two agencies - **kernel** and **shell**. Kernel interacts with the machine's hardware, while the shell interacts with the user.

    Kernel is responsible for all sorts of system management activities. It also provides services to the user programs in the form of system calls.

    Shell provides the user interface to the computer. It performs the job of command interpretation and gets a command-line executed with the help of the kernel.

    The UNIX system is supported by two abstractions, files and processes. File is an array of bytes and used to store data. Process is a file in execution. Both file and process have hierarchy.

##

02. Everything is represented in UNIX as a file, which is simply an array of bytes. A file when executed as a program is called a process. A file is stored on disk and a process exists in main memory.

    UNIX systems predominantly use text file as they are easy to edit. UNIX started out as an operating system targeted towards engineering community. Engineers often require to tinker with configuration files and share it with their peers. Using text file format makes it easy to do so.

##

03. **Multiprogramming**: Ability to keep multiple programs in the system memory at the same time.

    **Multiuser**: Ability to support multiple users at the same time and allowing them to use a single installation of operating system simultaneously.

    **Multitasking**: Ability to execute multiple tasks concurrently by a user and even switch between them.

##

04. System calls are special routines written in C language and built into the kernel. They act as an interface to the kernel for user programs. System calls are standardized across UNIX and any UNIX operating system by definition offers the same set of system calls.

    C programming is different and powerful in the UNIX environment as it was created and implemented first on UNIX and then the entire UNIX operating system, including all the utilities were written in C. Thus, C language and its standard library is deeply integrated into the UNIX operating system. UNIX system calls are implemented in C and are offered as C function interfaces.

    Windows doesn't share the same system calls as UNIX, neither does it include the standard library in its default installation.

##

05. The creators of the UNIX followed the **small is beautiful** philosophy and never attempted to pack many features into a single tool.

    Simple tools that perform well defined tasks can be combined using shell operators to perform complicated tasks and filter data.

##

06. The statement is not true. `wc` command can be used not just with files, but also with input coming from standard input or from output of some other command. This is illustrated with the following examples:

    Execute `wc` command without any argument. The command prompt won't return. Enter some text and terminate the input by entering a newline and immediately following it by end-of-file character using `[Control-d]`. The output will represent count of the characters in the entered text.

    Pipe the output of a command such as `ls` to `wc -l` to count the number of non-hidden files and directories in the current directory. Enter the command-line as:

    `ls | wc -l`.

##

07. Three major differences between UNIX commands and Windows programs are:

    - Unlike Windows, commands in UNIX are case-sensitive.

    - Windows commands work irrespective of the presence of whitespace between the command and its options unlike UNIX where whitespace is mandatory.

    - UNIX commands makes use of POSIX systems calls whereas Windows commands doesn't.

##

08. The program file named _foo_ present in the current directory is not executed if the current directory (represented by `.`) is not listed in the **PATH** environment variable.

##

09. Any contiguous sequence of one or more **space**, **tab** and **newline** characters is called a whitespace. If multiple contiguous whitespace is present between the command and its arguments, the shell automatically compresses it to a single space character.

##

10. By specifying the section number as an argument to `man` command. as follows:

    - `man -s1 command`

    - `man -s5 filename`

    - `man -s2 system_call`

##

11. Either one of `-f` or `-r` can be used as an argument when executing the command `/usr/xpg4/bin/tail`.

    The `file` argument can be repeated any number of times when executing the command `/usr/bin/ls`.

##

12. **Interrupt character** represented by `[Control-c]` is used to interrupt a long running or an unresponsive program.

    **eof character** represented by `[Control-d]` can be used to terminate user input or to log out from the current session.

##

13. Update the **PAGER** environment variable to use the desired pager say `less` by running `PAGER=less` on shell prompt.

##
