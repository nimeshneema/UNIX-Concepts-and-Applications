# Chapter 1 - Getting Started

1.  Operating systems like UNIX provide services for both programs and users.

    For **programs**, the operating system offers essential services that involve the use of machine resources, such as using the CPU, allocating memory, and accessing devices like the hard disk for reading and writing files.

    For **users**, the operating system provides services for common tasks like copying or deleting a file, creating a directory, finding out who is working on the network, and sending a mail message. As a system administrator, it also handles tasks like backing up files.

2.  When a program needs to access the hardware, such as reading a file on disk, it makes a **call to the operating system** instead of attempting to do the job itself. The operating system then directs the disk controller to open the file and make the data available to the program.

3.  The program that starts executing at your terminal when you log in is known as the **shell**. Four types of this program available on a UNIX system are:

    -   Bourne shell (**sh**)

    -   C shell (**csh**)

    -   Korn shell (**ksh**)

    -   Bash shell (**bash**)

4.  The output produced by executing `ls` command is saved in a file named _list_ in the current directory.

    When you enter the sequence **ls > list**, the shell sees the `>` metacharacter and acts on it first. It opens a file named `list` and then executes the `ls` command. The shell has manipulated things so that the output of `ls`, which is normally displayed on the terminal, is redirected to the file it opened on behalf of the command. No output is shown on the screen, and the prompt returns after the command is completed.

5.  The variable assignment `x=10` with spaces on either side of the `=` does not work because shell programming syntax requires there to be "No spaces on either side of =". When spaces are present, the shell does not interpret it as a variable assignment but instead attempts to run `x` as a command.

6.  Two empty files named _README_ and _readme_ are created in the current directory.

    If either of the two files exists already, it is replaced by an empty file.

    When running the commands on a case-insensitive file-system, only one file named _README_ is created.

7.  1.  Running the **who** command displays the user-ids, terminal names, and login times of all users currently logged into the system.

        Running the **tty** command, shows the name of the specific terminal you are working on.

    2.  The **ps** command shows the processes you are responsible for creating, including the running shell.

        The **echo $$** command would print the process-id (PID) of the current shell.

        While **ps** shows all your processes, running **echo $$** specifically gives you the PID of your shell process.

8.  The three sequences you would try to log yourself out of the system are the **exit** command, the **logout** command, and the key sequence **[Ctrl-d]**. The **exit** command will always work.

9.  Your user-id is significant because it is the name the system uses to address you and to uniquely identify you. It is used to associate you as the owner of any files or processes you create, and as the sender of any mail messages you send to other users.

10. The one thing that is common to directories, devices, terminals, and printers is that they are all represented as **files** in the system.

11. Some of the duties of a system administrator encountered so far are granting users the authority to use the system, opening user accounts, giving them a secret password, and having the privilege to change the system date and time. If you are the sole user of a desktop, you are also responsible for the machine's startup, shutdown, maintenance, and backing up files.

12. The two schools of UNIX that initially guided its development were the AT&T Bell Laboratories team of Ken Thompson and Dennis Ritchie, and the contributions from the University of California, Berkeley (UCB), which led to BSD UNIX.
