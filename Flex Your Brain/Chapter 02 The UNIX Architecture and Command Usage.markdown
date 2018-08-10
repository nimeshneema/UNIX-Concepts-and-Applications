### Flex Your Brain

---

01. The UNIX system divides the labor between two agencies - the kernel and the shell. Kernel interacts with the machine's hardware and the shell interacts with the user. Kernel is responsible for all sorts of system management activities. Shell performs the job of command interpretation and gets a command-line executed with the help of the kernel.

##

02. Everything is represented in UNIX by a file which is just an array of bytes. A file when executed as a program is called a process. A file is stored on disk and a process exists in main memory.

    UNIX systems predominantly use text file as they are easy to edit. UNIX started out as an operating system targeted towards engineering community. Engineers tend to tinker with configuration files and share it with their peers. Using text file format makes it easy. UNIX also provide a large collection of text manipulation tools to enable editing configuration files without using an editor.

##

03. **Multiprogramming**: Ability to keep multiple programs in the system memory at the same time.

    **Multiuser**: Ability to support multiple users at the same time and allowing them to use a single installation of an operating system simultaneously.

    **Multitasking**: Ability to execute multiple tasks concurrently and even switch between them.

##

04. System calls are special routines written in C language and built into the kernel. They act as an interface to the kernel for user programs. System calls are standardized across UNIX and any UNIX operating system by definition offers the same set of system calls.

    C programming is different and powerful in the UNIX environment as it was created and implemented first on UNIX and then the entire UNIX operating system, including all the utilities were written in C. Thus, C language and its standard library is deeply integrated into UNIX operating system. UNIX system calls are implemented in C and are offered as C function interfaces. Windows doesn't share the same system calls as UNIX, neither does it include the standard library in its default installation.

##

05. The creators of the UNIX followed the **small is beautiful** philosophy and never attempted to pack many features into a single tool.

    Simple tools that perform well defined tasks can be combined using shell operators to perform complicated tasks and filter data.

##

06. `wc` command can be used with not just files but with input coming from standard input or from output of some other command. This is illustrated with the following examples:

    Execute `wc` command without any argument. The command prompt won't return. Enter some text and terminate the input by entering a newline and immediately following it by end-of-file character using `[Ctrl-d]`. The output will represent count of the characters in the entered text.

    Pipe the output of a command such as `ls` to `wc -l` to count the number of non-hidden files and directories in the current directory. Enter the command-line as:

    `ls | wc -l`.

##

07. Three major differences between UNIX commands and Windows programs are:

    -   Unlike Windows, commands in UNIX are case sensitive.

    -   Windows commands work irrespective of the presence of whitespace between the command and its options unlike UNIX where whitespace is mandatory.

    -   UNIX commands makes use of POSIX systems calls whereas Windows commands doesn't.

##

08. This can happen when **foo** doesn't exist as a shell built-in command and neither is any executable named **foo** present in any of the directories listed in the **PATH** environment variable. The executable named **foo** present in the current directory is not executed if the current directory (represented by `.`) is not listed in the PATH environment variable.

##

09. Any contiguous sequence of space, tab and newline characters is called a whitespace. If multiple contiguous whitespace is present between the command and its arguments, the shell automatically compresses it to a single space character.

##

10. By specifying the section number as an argument to the `man` command. as follows:

    `man -s1 command`, `man -s5 filename` and `man -s2 system_call`.

##

11. Either one of `-f` or `-r` can be used as an argument when executing the command `/usr/xpg4/bin/tail`.

    The `file` argument can be repeated any number of times when executing the command `/usr/bin/ls`.

##

12. **Interrupt character** represented by `[Ctrl-c]` is used to interrupt a long running or an unresponsive program.

    **eof character** represented by `[Ctrl-d]` can be used to terminate user input or to log out from the current session.

##

13. Update the **PAGER** environment variable to use the desired pager say `less` by running `PAGER=less` on shell prompt.

##
