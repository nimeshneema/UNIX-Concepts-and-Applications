### Flex Your Brain

---

01. `$$`: Stores the PID of the user's login shell.

    `$!`: Stores the PID of the last background job.

##

02. (i). Both have certain attributes.

    (ii). Attributes for both are stored in a special structure in memory maintained by the operating system kernel (called process table for processes and inode for files).

    (iii). Both constitute parent child relationship.

##

03. The two options available to a parent process after spawning a child are:

    (i). Wait for the child process to die so that it can spawn more process.

    (ii). Do not wait for the child process to die and continue to spawn other processes.

    <br/>

    The shell can be made be behave in both the aforementioned modes as discussed:

    (i). The shell can be made to behave in waiting mode by waiting for the completion of the child processes before presenting the prompt again.

    (ii). The shell can be made to behave in non-waiting mode by executing the command in the background by using `&` operator or `nohup` command.

##

04. Daemons are special system processes that keep running all the time. The standard input and standard output of these process are not connected to the terminal. They are called without a specific request from the user. Many of these daemons are actually sleeping and wake up only when they receive input.

    A few examples of daemons and the tasks that they perform are:

    -   **lpsched**: Controls all the printing activity.

    -   **sendmail**: Handles incoming and outgoing email.

    -   **cron**: Looks for its control file once a minute and performs the mentioned jobs.

    Demons can be identified in the `ps -e` output by the `?` in the **TTY** column. The `?` means that the process has no controlling terminal.

##

05. A process is created using three distinct phases using three system calls as discussed below:

    -   **fork**: The fork system call causes a copy of the invoking process to be made. The newly created child process has identical value for its process parameters except for PID and PPID.

    -   **exec**: Using exec system call, the forked child overwrites its image with the code and data of the new program.

    -   **wait** : The parent process executes the wait system call to wait for the child process to complete.

    The fork-exec mechanism as discussed above is responsible for the multiplication of processes in the system.

##

06. The important process attributes inherited by a child process from its parent are:

    (i). real UID and GID.

    (ii). effective UID and GID.

    (iii). The current directory from where the process was run.

    (iv). The descriptors for all open files.

    (v). Environment variables.

##

07. `cd` is the change directory command. Directory change can't be made in a separate process. If invoking `cd` command spawns a child process (in case `cd` was made available as an external command), after the command has completed execution, control will return to the parent process and the original directory would be restored. Hence the command is built into the shell.

##

08. Once the system is up, **init** forks and execs a **getty** for every active communication port. **getty** prints login prompt on their respective terminals. When an attempt is made to login, **getty** fork-execs the login program. Upon successful login, **login** fork-execs the process for the applicable login shell. With repeated overlaying **init** becomes the immediate ancestor of the shell.

    When the user logs out, the shell process is killed and the death of the process is intimated to **init** which spawns another **getty** for the communication port.

##

09. Zombie is a process state which is acquired by a process upon its death. A dead process remains in this state until its parent process picks up the exit status from the process table. Once that is done, the kernel frees the process table entry thereby killing the process.

##

10. Both `&` and `nohup` are employed for running a process in the background. `nohup` allows the user to log out while the background job is running but shell's `&` operator provides no such guarantee.

##

11. Signal is a mechanism using which the UNIX system communicates the occurrence of an event to a process.

    Pressing `[Ctrl-z]` key combination on the keyboard sends **SIGTSTP** signal to the foreground process. It causes the process to suspend execution.

    Using `kill` command with signal names ensures portability as the signal numbers may vary across operating systems.

##

12. (i). **False**. There are two signals namely **SIGKILL** and **SIGSTOP** that a process can't ignore or run user-defined code to handle it.

    (ii). **False**. The parent process may not always wait for the child process to complete its run and return. The parent may also die leaving the child process as orphan. A child process may continue executing without returning.

    (iii). **True**. A single program (a single file of disk) can be executed by same or different users to give rise to multiple processes. A single user can log in from multiple terminals to give rise to more than one shell process (using the same shell program).

##

13. There appears to be some typo in the question as the shell built-in command `jobs` doesn't throw up this error message. A detailed discussion on the question can be read [here](https://unix.stackexchange.com/a/111350).

##

14. A single disk program or external command when executed creates a process. A job is a collection of more than one process.

    (i). A foreground job can be suspended by sending it **SIGTSTP** signal generated by pressing `[Ctrl-z]` on keyboard.

    (ii). A suspended job can be moved to background by executing `bg` command.

    (iii). A suspended job can be brought back to foreground by executing `fg` command.

##

15. (i). This is a valid **crontab** entry. It cause **cron** to execute the shell script **dial.sh**, every minute.

    (ii). This is an invalid **crontab** entry and will not work. In first column, **00-60** is not a valid range (valid range for minute of hour is **00-59**). **30th** day of month never occurs in **February** (2nd month of year), as mentioned in third and fourth column.

##

16. `00,30 8-18 * * 1,3,5 connect.sh`.

##
