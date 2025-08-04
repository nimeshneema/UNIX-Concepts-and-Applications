# Chapter 9 - The Process

1.  Both of them are special environment variables available in the shell.

    -   `$$`: This shell variable stores the PID of the user's login shell.

    -   `$!`: This shell variable stores the PID of the last background job.

2.  (i). Both processes and files have certain attributes.

    (ii). Attributes for both are stored in a special structure maintained by the operating system (called process table for processes and inode for files).

    (iii). Both constitute a parent-child relationship.

3.  The two options available to a parent after spawning a child process are:

    (i). Wait for the child process to die before spawning another process.

    (ii). Do not wait for the child process to die and continue to spawn other child processes.

    The shell can be made to behave in both the aforementioned modes as discussed:

    (i). The shell can be made to behave in waiting mode simply by waiting for the completion of the child process before presenting the prompt again.

    (ii). The shell can be made to behave in non-waiting mode by executing the command in the background by using `&` operator or the `nohup` command.

4.  Daemons are special system processes that keep running all the time. The standard input and standard output of these process are not connected to the terminal, i.e. they have no controlling terminal. They are called without a specific request from the user. Many of these daemons are sleeping and wake up only when they receive input.

    A few examples of daemons and the tasks that they perform are:

    -   **lpsched**: Control all the printing activity.

    -   **sendmail**: Handle incoming and outgoing email.

    -   **cron**: Look for its control file once a minute and performs the mentioned jobs.

    Demons can be identified in the `ps -e` output by the `?` under the **TTY** column. A `?` indicates that the process has no controlling terminal.

5.  A process is created via three distinct phases using three system calls, in order, as discussed below:

    01. **fork**: The `fork` system call causes a copy of the invoking process to be made. The newly created child process has identical value for its process parameters except for the value of PID and PPID.

    02. **exec**: Using the `exec` system call, the forked child overwrites its image with the code and data of the new program.

    03. **wait**: The parent process executes the `wait` system call to wait for the child process to complete.

    The fork-exec mechanism as discussed above is responsible for the multiplication of processes in the system.

6.  The five important process attributes inherited by a child process from its parent process are:

    (i). Real UID and GID.

    (ii). Effective UID and GID.

    (iii). The current directory from where the process was run.

    (iv). The descriptors for all the open files.

    (v). Environment variables.

7.  `cd` is the change directory command. Directory change can't be made in a separate process. If invoking `cd` command was to spawn a child process (as in case `cd` was made available as an external command), after the command has completed execution, control will return to the parent process, and the original directory would be restored. Hence the command is built into the shell.

8.  Once the system is up, **init** forks and execs a **getty** for every active communication port. **getty** prints login prompts on their respective terminals. When an attempt is made to login, **getty** fork-execs the login program. Upon successful login, **login** fork-execs the process for the applicable login shell. With repeated overlaying, **init** becomes the immediate ancestor of the shell.

    When the user logs out, the shell process is killed and the death of the process is intimated to **init** which spawns another **getty** for the communication port.

9.  Zombie is a process state which is acquired by a process upon its death. A dead process remains in this state until its parent process picks up its exit status from the process table. Once that is done, the kernel frees the process table entry thereby killing the zombie process.

10. Both `&` and `nohup` are employed for running a process in the background. `nohup` allows the user to log out while the background job is running, but the shell `&` operator provides no such guarantee.

11. A signal is a mechanism using which the UNIX system communicates the occurrence of an event to a process.

    Pressing `Control + z` key combination on the keyboard sends **SIGTSTP** signal to the foreground process. It causes the process to suspend execution.

    Using `kill` command with signal names ensures portability, as the signal numbers are not portable across various UNIX operating systems.

12. (i). **False**. There are two signals namely **SIGKILL** and **SIGSTOP** that a process can't ignore or run user-defined code to handle.

    (ii). **False**. The parent process may not always wait for the child process to complete its run and return. The parent may also die leaving the child process as an orphan. A child process may continue executing without returning.

    (iii). **True**. A single program (a single file of the disk) can be executed by same or different user to give rise to multiple processes. A single user can log in from multiple terminals to give rise to more than one shell process (using the same shell program).

13. `jobs` is a shell built-in command in Bash and doesn't throw up this error message.

    A discussion on the question can be found on a Unix & Linux Stack Exchange thread [here](https://unix.stackexchange.com/q/111349/280308).

14. A single disk program or external command when executed creates a process. A job is a collection of more than one process.

    (i). A foreground job can be suspended by sending it the **SIGTSTP** signal generated by pressing `Control + z` on keyboard.

    (ii). A suspended job can be moved to the background by executing the `bg` command.

    (iii). A suspended job can be brought back to the foreground by executing the `fg` command.

15. (i). This is a valid **crontab** entry. It cause **cron** to execute the shell script _dial.sh_, every minute.

    (ii). This is an invalid **crontab** entry and will not work. In the first column, **00-60** is not a valid range (valid range for minute of hour is **00-59**). **30th** day of month never occurs in **February** (2nd month of year), as mentioned in the third and the fourth column.

16. `00,30 8-18 * * 1,3,5 connect.sh`
