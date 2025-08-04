# Chapter 10 - Customizing the Environment

1.  An interactive shell presents a prompt and waits for input from the user. A non-interactive shell on the other hand only executes shell scripts. There are certain shell features which are exclusive to the interactive shell.

    Job control, aliases and history features have significance only in an interactive shell.

---

2.  Applications are not designed to run from a specific shell. The environment variables are not dependent on the shell. As they are independent of shell in use, they are represented in a fixed format.

---

3.  **HOME** and **SHELL** representing user's home directory and login shell respectively are set by reading the _/etc/passwd_ file.

---

4.  The location of user's mailbox is stored in the **MAIL** variable. The value of the **MAILCHECK** variable, on the other hand, determines the interval of time in seconds after which the shell checks the mailbox for the arrival of a new mail.

    The arrival of a new mail is intimated to the user by the shell, by printing a message on the terminal.

---

5.  (i). The prompt string can be changed to look as desired by setting the **PS1** environment variable by executing the following command line:

    `PS1="[\H-\u \w]"`

    (ii). The prompt string can be reverted back to the original value by restarting the login session, thereby resetting the vale for the **PS1** environment variable.

---

6.  The alias can be created by executing the following command line:

    `alias rm='rm -R'`

    Original `rm` command can be executed without un-aliasing, by appending the command with a `\` character as follows:

    `\rm`

---

7.  The accidental file overwriting can be prevented by setting the **noclobber** option in Korn and Bash shell by executing the following command line:

    `set -o noclobber`

    To override this protection feature, `|` symbol needs to be appended to the `>` symbol as shown:

    `ls -l >| list.txt`

---

8.  (i). Execute the command line corresponding to event number **50** as indicated by the output of the `history` shell built-in command.

    (ii). Display the command line before the previously executed command.

    (iii). Execute the last command.

    (iv). In the previously executed command, replace **doc** with **bak**.

    The Korn shell equivalent are listed below:

    (i). `r 50`

    (ii). `fc -l -2`

    (iii). `r`

    (iv). `r doc=bak`

---

9.  (iii) the last command beginning with ca.

---

10. The condenced command sequences are as follows:

    (i). `cp *.c c_progs ; cd $_`

    (ii). `cmp foo foo.bak ; ^bak^doc`

---

11. By running the following command lines:

    (i). `r`

    (ii). `!!`

---

12. In the Korn shell, enter:

    `r tar`

    In the Bash shell, enter:

    `!tar`

---

13. (i). Change the current working directory to the home directory of the user _henry_.

    (ii). Change the current working directory to the directory named _henry_ in logged-in user's home directory.

    (iii). Change the current working directory to the previous working directory.

    (iv). Same as (iii).

---

14. A profile file is executed once in a session, upon login. On the other hand, the contents of a rc file are executed every time a sub-shell is invoked.

    Commands to initialize environment variables, set aliases and shell options are set in these files.

---

15. By executing the `~/.alias` file within rc file by placing the following line in it:

    `. ~/.alias` or `source ~/.alias`

    Yes, the aliases will be available in a shell script in both Korn and Bash shell.

---

16. The two ways of changing _.profile_ file are:

    (i). Restarting the login session, thereby automatically executing the updated _.profile_ file.

    (ii). Executing the _.profile_ file in the current shell by running:

    `. .profile` or `source .profile`

---
