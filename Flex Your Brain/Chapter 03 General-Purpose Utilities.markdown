01. By running the following command-line:

    `date +"%d-%m-%y/%H:%M:%S"`.

##

02. An escape sequence is a sequence of characters that does not represent the characters themselves literally, but a different character that's not possible to be entered directly in the given context. It is generally a two character-sequence beginning with a backslash (**\\**) character.

    Three escape sequences used by `echo` command, with their significance are:

    -   `\n`: Represents newline character.
    -   `\b`: Represents backspace character.
    -   `\\`: Represents backslash character.

##

03. (i). Supply `-e` option to `echo` command. The modified command will be:

    `echo -e "Filename: \c"`.

    (ii). Supply `-n` option to `echo` command.  The modified command will be:

    `echo -n "Filename: \c"`.

##

04. There are a couple mistakes in the command-line:

    - As per the syntax of `printf` command, it is invalid to supply a comma character between arguments.

    - **fname** needs to be evaluated as a variable and should be preceded by `$` character.

    The corrected command-line is:

    `printf "Filename: %s\n" $fname`.

##

05. (i). Convert 192 to octal by executing the following `bc` internal commands:

    `obase=8[Enter]`
    <br/>
    `192[Enter]`

    Convert 192 to hexadecimal by executing the following `bc` internal commands:

    `obase=16[Enter]`
    <br/>
    `192[Enter]`

    (ii). Convert 192 to octal and hexadecimal by executing the following command-line:

    `printf "The value of 192 in octal is %o and hexadecimal is %x\n" 192 192`

    `bc` can be used to easily display the number in binary by setting `obase=2`.

##

06. Running `script` command spawns a new sub-shell process.

##

07. `mailx` command can obtain its arguments via shell variables or at runtime using piping and redirection. It can work non-interactively and can be automated.

##

08. When a new email message is received, it is stored in a file referred to as _mailbox_. Once the email message is read, it automatically moves to a file named _mbox_ which is generally stored in the users home directory.

##

09. To hide keybord input from getting displayed on the terminal, executing:

    `stty -echo`

    The above setting can be reversed by executing:

    `stty echo`.

##

10. A machine can be identified by checking its hostname by executing the following command:

    `uname -n`

##

11. By examining the output of:

    `stty -a`

    and reading values corresponding to **erase**, **kill** and **eof** keys.

##

12. By setting `[Control-c]` corresponding to **kill** keyword using `stty` command as:

    `stty kill \^c`

    No. The settings doesn't persist between login sessions.

##
