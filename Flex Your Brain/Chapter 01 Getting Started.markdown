### Flex Your Brain

---

01. A computer hardware is a bare machine with no intelligence of its own. An operating system like UNIX is a special system software which provides the computer with basic intelligence in the form of services.

    A few examples of services for programs include scheduling CPU time, allocating memory, accessing hardware devices like disks for reading and writing files etc.

    A few examples of services for users include file management (copying and deleting files, creating directories), determining other users currently logged-in into the system, sending mail messages etc.

##

02. The program makes a call to the operating system using a specially designed interface (known as **system call**), which in turn performs the job and makes the data available to the program.

##

03. The program is known as the user's login shell. Some of the popular shell programs available on a UNIX system are:

    - **sh**: The primitive Bourne Shell.
    - **csh**: C Shell.
    - **ksh**: Korn shell.
    - **bash**: An enhanced version of the original Bourne shell.

##

04. The output obtained on running `ls` command is saved in a file named _list_ in the current directory.

    The shell sees the redirection operator when interpreting the command-line. It opens the file following the `>` operator (here, _list_). Next the command `ls` is run which reads the directory file corresponding to the current directory. The shell has manipulated things so that the output of the `ls` command doesn't go to the standard output but is written to the file opened by the shell on its behalf.

    **Note**: The file is created anew if it doesn't already exist, or is overwritten with the command output if it does. An error occurs if either the named file exists and is not writable by the current user, or the named file doesn't exist and the directory is not writable by the user.

##

05. The shell programming syntax requires that there should be no spaces on either side of the `=` operator.

    When entering `x =10`, `x` is treated as a command by the shell. Since there is no system command (internal or external) named `x`, the shell shows an appropriate error message stating that the command couldn't be found.

    Similar error occurs in case `x= 10` is entered where `10` is treated as a command. The shell tries to locate and execute it, but fails to do so. The `x=` part is seen as a variable assignment valid only for the scope of `10` command.

##

06. Two empty files named _README_ and _readme_ are created in the current directory.

    **Note**: When running on a case-insensitive file-system (the default configuration on macOS), only one file named _README_ is created. If either of the two files already exists, its content is overwritten with an empty file.

##

07. (i). `who` command outputs a list of all the users currently logged in, showing for each user her login name, terminal name, date and time of login and host-name if not local.

    `tty` command outputs the absolute path of the device file corresponding to the terminal attached to the standard output.

    (ii). `ps` command outputs a list of all the currently running processes corresponding to the logged in user.

    `echo $$` outputs the integer **PID** (Process ID) corresponding to the running shell process.

##

08. `[Ctrl-d]`, `logout` and `exit`. `exit` command is guaranteed to always work.

##

09. The user-id is used to uniquely identify a user in the operating system. It is associated with any file or process created by the user.

    The name is used to identify the user with other users and for display in command output.

##

10. They are all represented as files in the UNIX file-system.

##

11. Some of the duties of a systems administrator are:

    - Backing up files.

    - Restoring the system to a usable state in case of a crash.

    - Startup, shutdown and maintenance of the system.

    - Administering the system.

    - Creating and administering user accounts.

    - Updating system date.

##

12. AT&T and University of California, Berkeley (UCB).

##
