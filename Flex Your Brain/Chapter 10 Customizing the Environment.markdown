01. An interactive shell presents a prompt and waits for input from user. A non-interactive shell on the other hand only executes shell scripts.

    Job control and history features have no significance in a non-interactive shell.

##

02. Applications are not designed to run from a specific shell. The environment variables are not dependent on shell. As they are independent of shell in use, they are represented in a fixed format.

##

03. **$HOME** and **$SHELL** representing users users home directory and login shell respectively are set by reading _/etc/passwd_ file.

##

04. The location of users mailbox is stored in **MAIL** variable. The value of **MAILCHECK** variable on the other hand determines the interval of time in minutes after which the shell checks the mailbox for the arrival of new mail.

    The arrival of new mail is intimated to the user by shell by printing a message on terminal.

##

05. (i). Set **$PS1** variable by executing: `PS1="[\H-\u \w]"`.

    (ii). By restarting the login session, thereby reverting to the original value for **PS1** environment variable.

##

06. The alias can be created by executing the following command-line:

    `alias rm='rm -R'`.

    Original `rm` command can be executed without unaliasing by appending the command with a `\` character as follows:

    `\rm`.

##

07. The accidental file overwriting can be prevented by setting **noclobber** option in Korn and Bash by executing the following:

    `set -o noclobber`.

    To override this protection feature, `|` symbol needs to be appended to `>` symbol as shown:

    `ls -l >| list.txt`.

##

08. (i). `!50`: Executes command-line corresponding to event number **50** as indicated by output of `history` shell built-in command.

    (ii). `!-2:p`: Display the command-line prior to the previously executed command.

    (iii). `!!`: Execute the last command.

    (iv). `^doc^bak`: In the previously executed command replace **doc** with **bak**.

    The Korn shell equivalent are listed below:

    (i). `r 50`.

    (ii). `fc -l -2`.

    (iii). `r`.

    (iv). `r doc=bak`.

##

09. (iii).

##

10. (i). `cp *.c c_progs ; cd $_`.

    (ii). `cmp foo foo.bak ; ^bak^doc`.

##

11. (i). `r`.

    (ii). `!!`.

##

12. In Korn enter:

    `r tar`.

    In Bash enter:

    `!tar`.

##

13. (i). Change the current working directory to home directory of user **henry**.

    (ii). Change the current working directory to the directory named _henry_ in logged in user's home directory.

    (iii). Change the current working directory to the immediate previous working directory.

    (iv). Same as (iii).

##

14. A profile file is executed once in a session. On the other hand the contents of a rc file are executed every time a sub-shell is invoked.

    Commands to initialize environment variables, set aliases, and shell options are set in these files.

##

15. By executing the `~/.alias` file within rc file by placing the following line in it:

    `. ~/.alias` or `source ~/.alias`.

    Yes.

##

16. (i). Restarting the login session, thereby automatically executing the updated _.profile_ file.

    (ii). Executing the _.profile_ file in the current shell by running:

    `. .profile` or `source .profile`.

##
