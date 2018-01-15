### Flex Your Brain

---

01. By running the following command-line:


    `date +"%d-%m-%y/%H:%M:%S"`

##

02. An escape sequence is generally a two character-sequence beginning with a backslash (`\`) character.

    Three escape sequences used by echo command, with their significance are:

    -   `\n` : Prints a newline.
    -   `\b` : Prints a backspace character, i.e. removes the previous character.
    -   `\\` : Prints a literal backslash character.

##

03. (i). Supply `-e` option to echo command as: `echo -e "Filename: \c"`

    (ii). Supply `-n` option to echo command as: `echo -n "Filename: \c"`

##

04. The comma character is not required after the first argument. `fname` needs to be evaluated as a variable and should be preceded by `$` character. The correct command-line is:

    `printf "Filename: %s\n" $fname`

##

05. (i). Convert 192 to octal by executing the following internal commands:

    `obase=8`
    <br/>
    `192[Enter]`



    Convert 192 to hexadecimal by executing the following internal commands:
    
    `obase=16`
    <br/>
    `192[Enter]`

    (ii). Convert 192 to octal and hexadecimal by executing the following command-line:

    `printf "The value of 192 in octal is %o and hexadecimal is %x\n" 192 192`

    `bc` can be used to display the number in binary by setting `obase=2`.

##

06. Running `script` command spawns a new shell process.

##

07. **mailx** can obtain its arguments via shell variables or at runtime using piping and redirection. It can work non-interactively and can be automated.

##

08. When a new email message is received, it is stored in a file referred to as **mailbox**. Once the email message is read, it automatically moves to a file named **mbox** which is generally stored in the users home directory.

##

09. Executing:

    `stty -echo`

    will turn off the display of keyboard input. The above setting can be reversed by executing:

    `stty echo`.

##

10. Execute:

    `uname -n`

    and check the hostname.

##

11. By examining the output of:

    `stty -a`

    and reading values corresponding to **erase**, **kill** and **eof** keys.

##

12. By setting `[Ctrl-c]` corresponding to `kill` keyword using stty command as:

    `stty kill \^c`.

    No. The settings doesn't persist between login sessions.

##
