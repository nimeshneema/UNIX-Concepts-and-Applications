### Flex Your Brain

---

01. The three modes of **vi** are: **Command Mode**, **Input Mode** and **ex Mode** (or Last Line Mode).

    The editor starts in Command mode by default. To switch to Input mode, enter one of the `i`, `I`, `a`, `A`, `r`, `R`, `s`, `S`, `o`, or `O` key. To switch back to Command mode, press the `[Esc]` key. To enter ex mode, switch to Command mode and press the `:` key followed by ex mode command. ex mode command is executed by pressing the `[Enter]` key, which on completion switches the editor back to Command mode.

##

02. First navigate to the desired line using appropriate navigation keys. Press `I` to insert text at the beginning of the line. Enter `/*` and press `[Esc]` key to switch back to Command mode. Now press `A` key to append text at the end of the line. Enter `*/` and press the `[Esc]` key to switch back to the Command mode.

##

03. Since the cursor is still placed at the last character of the line, press `x` twice to delete two characters at the end of the line. Now press `0` to move to the beginning of the line. Again press `x` twice to delete the two characters at the beginning of the line.

##

04. To move to line number 100, enter `:100` followed by pressing the `[Enter]` key.

    To write the lines to a file named **newfile**, execute the ex mode command:

    `:.,$w newfile`.

##

05. This can happen when there are unsaved changes in the buffer. To discard the unsaved changes and exit anyways, execute the ex mode command: `:q!`.

##

06. (i). `:.,10w foo`: Saves the lines from the current line to 10th line below in a file named **foo**.

    (ii). `:$w! foo`: Saves the last line in a file named **foo**. Overwrite the file **foo** if it already exist.

    Both the above commands are executed in ex mode. If the file **foo** already exists, a warning message is shown by vi editor upon executing `:w` ex mode command. The warning can be overridden by appending `!` to `:w` command.

##

07. Enter the character sequence as shown below:

    (i). `e`, `a`, ` -n`, `[Esc]`, `w`, `r"`, `3e`, `2x`, `r"`.

    The step-by-step explanation is as follows:

    `e`: Move forward to end of word.

    `a`: Enter input mode to append text to right of cursor.

    ` -n`: Enter the three character **space**, **hyphen** and alphabet **n**.

    `[Esc]`: Press escape key to switch back to command mode.

    `w`: Move forward to beginning of word.

    `r"`: Replace **single quote** character with **double quote**.

    `3e`: Move forward to end of word, repeated thrice.

    `2x`: Delete the 2 characters `\c`.

    `r"`: Replace **single quote** character with **double quote**.

    <br/>

    (ii). `I`, `f`, `[Esc]`, `w`, `a`, `stderr, `, `[Esc]`, `6e`, `a`, `"`, `[Esc]`.

    The step-by-step explanation is as follows:

    `I`: Enter input mode to insert text at beginning of line.

    `f`: Insert the alphabet `f`.

    `[Esc]`: Switch to command mode.

    `w`: Move forward to beginning of word.

    `a`: Enter input mode to append text to right of cursor.

    `stderr, `: Enter the string **stderr** followed by command and space character.

    `[Esc]`: Switch to command mode.

    `6e`: Move forward to end of word, repeated six times.

    `a`: Enter input mode to append text to right of cursor.

    `f`: Insert double quote character.

    `[Esc]`: Switch to command mode.

##

08. By running the `who` command by executing ex mode command `:!who`.

    Switch to shell without quitting the editor by executing ex mode command `:sh`. Quitting the shell will returns to the editor session.

##

09. Make sure you are in command mode. Enter the character sequence as shown below:

    `:/#include`, `[Enter]`, `4dd`, `:1`, `[Enter]`, `P`.

    The step-by-step explanation is as follows:

    `:/#include`: ex mode command to search for the occurrence of string **#include**.

    `[Enter]`: Pressing the enter key executes the above ex mode command and positions the cursor on the first match of the **#include** string.

    `4dd`: Deletes 4 lines, starting from the current line.

    `:1`: ex mode command to move to the first line of the file buffer.

    `[Enter]`: Execute the above ex mode command.

    `P`: Paste the deleted content of the four lines here.

##

10. To achieve the desired substitution with global effect, execute the following ex mode substitute command sequence:

    `:1,$s/printf(/fprintf(stderr,/g`

##

11. In default configuration, `u` undoes the most recent, single editing change. Subsequent pressing of the key will redo the change.

    When a number of editing changes have been made to a single line and the user has not navigated away from the line, pressing `U` will discard all the changes made since the cursor was moved to the line.

##

12. The desired ex mode command sequences are as shown below:

    (i). `:1,10s/cnt/count/g`

    (ii). `:.s/cnt/count/g`

    (iii). `:1,$s/cnt/count/g`

    To repeat the exercise in an interactive manner, change the flag from `g` to `gc`. The updated ex mode command sequences are as shown below:

    (i). `:1,10s/cnt/count/gc`

    (ii). `:.s/cnt/count/gc`

    (iii). `:1,$s/cnt/count/gc`

##

13. The swap file can remain on disk and the editor will complain when an attempt is made to open the file.

    It is advised to use `:recover` ex mode command to recover as much of the file as possible.

##

14. Save the file under a different name by executing the ex mode command:

    `:w filename`.

    Make sure that a file named **filename** doesn't already exist on disk.

##

15. Copy the **/etc/passwd** file in the home directory by running the following command-line:

    `cd ; cp /etc/passwd .`

    Start the vi editor by executing:

    `vi passwd`

    Now, execute the following ex mode commands one by one:

    `:1,10w passwd1`

    `:11,20w passwd2`

    `:21,$w passwd3`.

##

16.Enter the character sequence as shown below:

    `:1`, `O`, enter the characters: `#include <stdio.h>`, `[Esc]`, `j`, `0`, `l`, `x`, `6e`, `a`, enter the characters: `, int exit_status`, `A`, enter the characters: ` {`, `[Esc]`, `j`, `dd`, `0`, `w`, `i`, enter the characters: `/* `, `[Esc]`, `A`, enter the characters: ` */`, `[Esc]`, `j`, `0`, `w`, `i`, enter the character: `f`, `[Esc]`, `w`, `a`, enter the characters: `stderr, `, `[Esc]`, `2w`, `rE`, `5w`, `i`, enter the characters: `quitting program\n`, `[Esc]`, `j`, `dd`, `0`, `3w`, `s`, enter the characters: `exit_status`, `[Esc]`.

##
