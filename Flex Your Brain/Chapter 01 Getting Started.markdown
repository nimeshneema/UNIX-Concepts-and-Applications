01. A computer hardware is a bare machine with no intelligence of its own. An operating system like UNIX is a special software which provides a computer with basic intelligence. This intelligence is used to provide services for both program running under it and for the users of computer.

    Services for programs include scheduling CPU time, allocating memory, accessing hardware devices like hard drive for reading and writing files etc.

    Services for users include file management (copying and deleting files, creating directories), determining other users currently logged-in into the system or network, sending mail messages, backing up files etc.

##

02. A program generally can't read files by itself. Instead it places a request to access the file to the operating system. The operating system in turn performs the job and makes the file data available to the program.

##

03. The program called user's login shell starts executing at the terminal as soon as she logs in. Some of the popular shell programs available on a UNIX system are:

    - **sh**: Bourne shell.
    - **csh**: C shell.
    - **ksh**: KornShell.
    - **bash**: Bourne Again SHell.

##

04. The output of `ls` command is saved in a file named _list_ in the current directory.

    The shell sees the redirection operator (**>**) when interpreting the command-line. It opens the named file following the redirection operator (here, _list_). Next the command `ls` is run which reads the directory contents. The shell has manipulated things so that the output of the `ls` command doesn't go to the terminal, but is written to the file opened by the shell on its behalf.

##

05. The shell programming syntax requires that there should be no spaces on either side of **=** operator.

    When entering `x =10`, `x` is treated as a command by the shell. There is no command (internal or external) named `x`, the shell shows an error message stating that the command couldn't be found.

    Similar error occurs in case `x= 10` is entered, where `10` is treated as a command. The shell tries to locate and execute it, but fails to do so. The `x=` part is seen as a variable assignment valid only for the scope of `10` command.

##

06. Two empty files named _README_ and _readme_ are created in the current directory.

    **Note**: When running on a case-insensitive file-system (the default configuration in macOS), only one file named _README_ is created. If either of the two files exists already, it is replaced by an empty file.

##

07. (i). `who`: Lists all the users currently logged in. It produces a four column output showing users login name, terminal name, date and time of login and hostname if not local.

    `tty`: Prints the file name of the terminal connected to the standard input.

    (ii). `ps`: Lists all the currently running processes corresponding to the logged in user.

    `echo $$`: Prints the integer **PID** (Process ID) corresponding to the running shell process.

##

08. `[Control-d]`, `logout` and `exit`. `exit` command is guaranteed to always work.

##

09. The user-id is used to uniquely identify the user in the operating system.

    It is used throughout the system by associating it with any file or process created by the user.

##

10. Directories, devices, terminals and printers are all represented as files in the UNIX file-system.

##

11. Some of the duties of a systems administrator are:

    - Backing up files.

    - Restoring the system to a usable state in case of a crash.

    - Startup, shutdown and maintenance of the system.

    - Creating and administering user accounts.

    - Updating system date.

##

12. AT&T and University of California, Berkeley (UCB).

##
