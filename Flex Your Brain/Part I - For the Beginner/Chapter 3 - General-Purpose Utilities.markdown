# Chapter 3 - General-Purpose Utilities

1.  You display both the date and time in the specified format using the **date** command with a format specifier string. The format string combines the desired date and time elements, each preceded by a `%`.

    ```
    date +"%d-%m-%y/%H:%M:%S"
    ```

2.  An escape sequence is a two-character string, typically beginning with a backslash (`\`), that the **echo** command interprets as a directive rather than a literal character.

    Here are three escape sequences used by `echo`:

    -   `\c`: This sequence suppresses the newline character that **echo** normally adds at the end of its output. This keeps the cursor and the next prompt on the same line as the output.

    -   `\t`: This represents a tab character, which inserts horizontal space, pushing the following text to the right by eight character positions.

    -   `\n`: This represents a newline character, which creates the effect of a line break.

3.  The original command **echo "Filename: \c"** didn't place the cursor at the end of the line because `echo`'s behavior with escape sequences can vary between different shells.

    -   **Bash**: For the command to behave correctly in Bash, you must use the `-e` option, which enables the interpretation of escape sequences.

        ```
        echo -e "Filename: \c"
        ```

    -   **Any other shell (System V-based)**: In other shells like those based on System V, escape sequences are often interpreted by default. The command as written should work, but if it doesn't, you can try using the `-n` option, which is an alternative to `\c` in BSD-based systems.

        ```
        echo -n "Filename: "
        ```

4.  The command **printf "Filename: %s\n", fname** fails to run as intended because it uses C language syntax, which is incorrect for the UNIX **printf** command. In the shell environment, arguments for **printf** should not be separated by a comma. The variable `fname` would also need a `$` prefix to be evaluated.

    The correct syntax for the shell `printf` would be:

    ```
    printf "Filename: %s\n" "$fname"
    ```

    This syntax correctly passes the format string and the argument to the command.

5.  -   **Using `bc`**:

        To convert the decimal number **192** to octal, you set the `obase` (output base) to 8, then enter the number. For hexadecimal, you set `obase` to 16.

        ```
        bc
        obase=8
        192
        300
        obase=16
        192
        C0
        ```

        You would use `ibase=10` to ensure the input is treated as decimal, but this is the default.

    -   **Using `printf`**:

        You can use the `%o` and `%x` format specifiers to display the number in octal and hexadecimal, respectively.

        ```
        printf "192 in octal is %o, in hexadecimal is %x\n" 192 192
        ```

        This would output: `192 in octal is 300, in hexadecimal is c0`

    **Binary**: To display the number in binary, you must use **bc**. You would set `obase` to 2. The `printf` command does not have a format specifier for binary output.

    ```
    bc
    obase=2
    192
    11000000
    ```

6.  When you run `ps` first, it shows the processes currently running in your shell, which includes your login shell.

    After running the `script` command, a new shell process is started.

    When you run `ps` again from within this new shell, you will notice that the output now includes two shell processes: the original login shell and the new shell that was created by **script**. This demonstrates that **script** starts a new shell as a "child" of the login shell.

7.  The **mailx** command is considered superior to a GUI program like Netscape or Mozilla because of its non-interactive nature. It can be used from shell scripts, allowing for the automation of mail-related tasks. Its ability to work with command-line options, redirection, and pipes makes it a versatile tool for generating mail headers and message bodies on the fly without user intervention or mouse clicks.

8.  In the UNIX mailing system, the **mailbox** is the primary file where all new incoming messages are deposited. The `mailbox` is typically located in a system directory like `/var/mail` and is named after the user's ID.

    The **mbox**, on the other hand, is a secondary storage file (usually named `mbox` in the user's home directory). Once a message from the `mailbox` is viewed, it is moved to the `mbox` file, where it remains until it is explicitly deleted.

9.  To prevent keyboard input from being displayed on the screen, you would use the `stty` command with the `-echo` keyword.

    To accept the input:

    ```
    stty -echo
    ```

    After the input is received, you revert to the normal setting by running:

    ```
    stty echo
    ```

    This restores the normal behavior of echoing characters to the screen.

10. To confirm whether you are logged on to a remote machine, you can use the **who am i** command. It will display information about your current session, including the machine name from which you logged in. If you are logged in remotely, the output will show the remote machine's hostname or domain name in parentheses.

    ```
    # If logged in from a local terminal
    $ who am i
    kumar    console    Aug 1 07:56     (:0)

    # If logged in from a remote machine
    $ who am i
    kumar    pts/10     Aug 1 07:56     (pc123.heavens.com)
    ```

    You could also use the **uname -n** or **hostname** commands, which would display the name of the machine you are currently logged into. You can then compare this to your local machine's name.

11. You can determine the erase, kill, and eof characters on your system by using the **stty -a** command. This command displays all the current terminal settings.

    The output will show a list of keywords and their assigned values. The erase character is shown by `erase = ^?`, the kill character by `kill = ^u`, and the end-of-file (eof) character by `eof = ^d`. The `^` symbol represents the **Ctrl** key.

12. To ensure that **[Ctrl-c]** interrupts any program, you need to use the **stty** command to set the interrupt character.

    ```
    stty intr \^c
    ```

    This command tells the system that the interrupt key sequence is **[Ctrl-c]**.

    This setting will only be in effect for the current session. The next time you log in, the terminal will revert to its default settings. To make the setting permanent, you would need to add this command to a shell configuration file (like `.profile`), which will be covered in a later chapter.
