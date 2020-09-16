## Chapter 02 - The UNIX Architecture and Command Usage

01.	The UNIX system divides the labor between two agencies:

	-	**Kernel**

	and

	-	**Shell**

	The kernel interacts with the machine's hardware. It is responsible for all sorts of system management activities. It also provides services to the user programs in the form of system calls.

	The shell interacts with the user. It provides the user interface to the computer. It performs the job of command interpretation and gets a command line executed with the help of the kernel.

##

02.	A file is simply an array of bytes stored on disk and can practically contain anything. A file getting executed as a program is called a process.

	UNIX systems predominantly use text files as they are easy to edit. UNIX started as an operating system targeted towards engineering community, and engineers often used to tinker with configuration files and share it with their peers. Using a text file format makes it easy to do so.

##

03.	-	**Multiprogramming**: Ability to keep multiple programs in the system memory at the same time.

	-	**Multiuser**: Ability to support multiple users at the same time and allowing them to use a single installation of operating system simultaneously.

	-	**Multitasking**: Ability to execute multiple tasks concurrently by a user and even switch between them.

##

04.	System calls are special routines written in C programming language and built into the operating system kernel. They act as an interface to the kernel for user programs. System calls are standardized across UNIX, and any UNIX operating system, by definition, offers the same set of system calls.

	C programming is different and powerful in the UNIX environment as it was created and implemented first on UNIX, and then the entire UNIX operating system, including all the utilities were written in C. Thus, C language, and its Standard Library is deeply integrated into the UNIX operating system. UNIX system calls are implemented in C and are offered as C function interfaces.

	Windows don't share the same system calls as UNIX. Neither does it include the C Standard Library in its default installation.

##

05.	The creators of the UNIX followed the **small is beautiful** philosophy. They attempted not to cram many features into a single tool.

	They believed that using simple tools that perform well-defined tasks can be combined with shell operators to perform complicated tasks and filter data.

##

06.	The statement is not precisely true. `wc` command can be used, not just with files, but also with input coming from standard input or the output of some other command. This is illustrated with the following examples:

	Execute `wc` command without any argument. The command prompt won't return. Enter some text and terminate the input by entering a newline, and immediately following it by the end-of-file character using `[Control-d]`. The output will represent the count of the characters in the entered text.

	Pipe the output of a command such as `ls` to `wc -l` to count the number of non-hidden files and directories in the current directory. Enter the command line as:

	`ls | wc -l`

##

07.	Three major differences between UNIX commands and Windows programs are:

	-	Unlike Windows, commands in UNIX are case-sensitive.

	-	Windows commands work irrespective of the presence of whitespace between the command and its options, unlike UNIX where whitespace is mandatory.

	-	UNIX commands make use of POSIX systems calls whereas Windows commands don't.

##

08.	The program file named _foo_ present in the current directory is not executed if the current directory (represented by **.**) is not listed in the **PATH** environment variable.

##

09.	Any contiguous sequence of one or more **space**, **tab** and **newline** characters are called whitespace.

	If multiple contiguous whitespaces are present between the command and its arguments, the shell automatically compresses it to a single space character.

##

10.	By specifying the section number as an argument to the `man` command (as depicted):

	-	`man -s1 command`

	-	`man -s5 filename`

	-	`man -s2 system_call`

##

11.	Either one of `-f` or `-r` can be used as an argument when executing the command `/usr/xpg4/bin/tail`.

	The `file` argument can be repeated any number of times when executing the command `/usr/bin/ls`.

##

12.	-	**Interrupt character** represented by `[Control-c]` is used to interrupt a long-running or an unresponsive program.

	-	**eof character** represented by `[Control-d]` can be used to terminate user input or to log out from the current session.

##

13.	By updating the **PAGER** environment variable to use the desired pager say `less` by running `PAGER=less` on the shell prompt.

##
