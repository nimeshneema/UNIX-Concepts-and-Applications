# Chapter 7 - The vi Editor

1.  The three modes of **vi** editor are:

    -   **Command Mode**

    -   **Input Mode**

    -   **ex Mode** (also called **Last Line Mode**)

    The editor starts in **Command Mode** by default. To switch to the **Input Mode**, enter one of the following keys:

    -   `i`: Insert text towards the left side of the cursor.

    -   `I`: Insert text towards the beginning of the line.

    -   `a`: Append text towards the right side of the cursor.

    -   `A`: Append text towards the end of the line.

    -   `r`: Replace the character under the cursor.

    -   `R`: Replace all the text starting from the cursor to the end of the line.

    -   `s`: Substitute text under the cursor.

    -   `S`: Substitute the entire line.

    -   `o`: Open a new line below the current line.

    -   `O`: Open a new line above the current line.

    To switch back to **Command Mode**, press the `Esc` key. Repeated/un-needed pressing of the `Esc` key sounds a beep.

    To enter **ex Mode**, switch to the **Command Mode** and press the `:` key, followed by the **ex Mode** command. An **ex Mode** command is executed upon pressing the `Enter` key, which upon completion switches the editor back to the **Command Mode**.

2.  First, navigate to the desired line using appropriate navigation keys. Press `I` to insert text at the beginning of the line. Enter `/*` and press `Esc` key to switch back to the **Command Mode**. Now press `A` key to append text at the end of the line. Enter `*/` and press the `Esc` key to switch back to the **Command Mode**.

3.  Since the cursor is still placed at the last character of the line, press the `x` key twice to delete two characters at the end of the line. Now press the `0` key to move to the beginning of the line. Again press the `x` key twice to delete the two characters at the beginning of the line.

4.  To move to line number 100, enter `:100` followed by pressing the `Enter` key.

    To write the lines to a file named _newfile_, execute the **ex Mode** command: `:.,$w newfile`

5.  This can happen when there are unsaved changes in the buffer. To discard the unsaved changes, and exit anyways, execute the **ex Mode** command: `:q!`.

6.  1.  This command saves the lines from the current line to 10th line below in a file named _foo_.

    2.  This command saves the last line in a file named _foo_.

    Both the above commands are executed in the **ex Mode**. If the file _foo_ already exists, a warning message is shown by the vi editor upon executing the `:w` **ex Mode** command. The warning message can be overridden by appending the `!` character to the `:w` command.

    So the second command overwrite the file _foo_ if it already exists in the current directory.

7.  Enter the character sequence as shown below:

    1.  `e`, `a`, ` -n`, `Esc`, `w`, `r"`, `3e`, `2x`, `r"`

    The step-by-step explanation is as follows:

    -   `e`: Move forward to the end of the word.

    -   `a`: Enter **Input Mode** to append text to the right of the cursor.

    -   ` -n`: Enter the three characters, **space**, **hyphen** and alphabet **n**.

    -   `Esc`: Press the escape key to switch back to the **Command Mode**.

    -   `w`: Move forward to the beginning of the word.

    -   `r"`: Replace **single quote** character with **double quote**.

    -   `3e`: Move forward to the end of the word, repeated thrice.

    -   `2x`: Delete the two characters `\c`.

    -   `r"`: Replace **single quote** character with **double quote**.

    2.  `I`, `f`, `Esc`, `w`, `a`, `stderr, `, `Esc`, `6e`, `a`, `"`, `Esc`

    The step-by-step explanation is as follows:

    -   `I`: Enter **Input Mode** to insert text at the beginning of the line.

    -   `f`: Insert the alphabet `f`.

    -   `Esc`: Switch to the **Command Mode**.

    -   `w`: Move forward to the beginning of the word.

    -   `a`: Enter **Input Mode** to append text to right of the cursor.

    -   `stderr, `: Enter the string **stderr**, followed by a **comma**, and a **space** character.

    -   `Esc`: Switch to the **Command Mode**.

    -   `6e`: Move forward to the end of the word, repeated six times.

    -   `a`: Enter the **Input Mode** to append text to right of the cursor.

    -   `"`: Insert a double quote character.

    -   `Esc`: Switch to the **Command Mode**.

8.  By running the `who` command by executing the **ex Mode** command `:!who`.

    Switch to the shell without quitting the editor by executing the **ex Mode** command `:sh`. Quitting the shell resumes the editor session.

9.  Make sure you are in the **Command Mode**. Enter the character sequence as shown below:

    `:/#include`, `Enter`, `4dd`, `:1`, `Enter`, `P`

    The step-by-step explanation is as follows:

    -   `:/#include`: The **ex Mode** command to search for the occurrence of the string **#include**.

    -   `Enter`: Pressing the enter key executes the above **ex Mode** command, and positions the cursor on the first match of the **#include** string.

    -   `4dd`: Delete 4 lines, starting from the current line.

    -   `:1`: The **ex Mode** command to move to the first line of the file buffer.

    -   `Enter`: Execute the above **ex Mode** command.

    -   `P`: Paste the deleted content of the four lines before the first line.

10. The desired command sequence to replace the occurrences of the text in the current line is:

    `:.s/printf(/fprintf(stderr,/g`

    The above is an **ex Mode** substitute command sequence.

    To achieve the desired substitution with global effect, execute:

    `:1,$s/printf(/fprintf(stderr,/g`

11. In the default configuration, `u` undoes the most recent, single editing change. Subsequent pressing of the key will further undo previous changes.

    When several editing changes have been made to a single line, and the user has not navigated away from the line, pressing `U` will discard all the changes made since the cursor was moved to the line.

12. The desired command sequences are as shown below:

    1.  `:1,10s/cnt/count/g`

    2.  `:.s/cnt/count/g`

    3.  `:1,$s/cnt/count/g`

    To repeat the exercise interactively, change the flag from **g** to **gc**. The corresponding command sequences are as shown below:

    1.  `:1,10s/cnt/count/gc`

    2.  `:.s/cnt/count/gc`

    3.  `:1,$s/cnt/count/gc`

13. A temporary swap file created by the vi editor can persist on disk. In such a case, upon restarting, and resuming the work subsequently, the editor will complain when an attempt is made to open the file.

    To salvage, use the `:recover` **ex Mode** command to recover as much of the file data as possible.

14. Save the file under a different name by executing the **ex Mode** command:

    `:w filename`

    Make sure that a file named _filename_ doesn't already exist on disk.

15. Copy the _/etc/passwd_ file in the home directory by running the following command line:

    `cd ; cp /etc/passwd .`

    Start the vi editor by executing:

    `vi passwd`

    Now, execute the following **ex Mode** commands one by one:

    -   `:1,10w passwd1`

    -   `:11,20w passwd2`

    -   `:21,$w passwd3`

16. Use the key-sequence as mentioned below (along with explanation):

    -   `:1`: Move to the first line in the text.

    -   `0`: Move the cursor to the first column.

    -   `O`: Open a line above and enter **Input Mode**.

    -   `#include <stdio.h>`: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `j`: Move a line below.

    -   `2|`: Move to the second column.

    -   `x`: Delete the space character just before include.

    -   `e`: Move to end of the word.

    -   `a`: Enter the **Input Mode** to append text.

    -   ` `: Enter a single space character just after include.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `j`: Move a line below.

    -   `$`: Move the cursor to the end of the line.

    -   `h`: Move the cursor one character to the left.

    -   `a`: Enter the **Input Mode** to append text.

    -   `, int exit_status`: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `J`: Join the current and the next line.

    -   `j`: Move a line below.

    -   `b`: Repeatedly press this key till the cursor is at the beginning of the word **printf**.

    -   `i`: Enter the **Input Mode** to insert text.

    -   `/* `: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `A`: Enter the **Input Mode** to append text to the end of the line.

    -   ` */`: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `o`: Open a line below and enter the **Input Mode**.

    -   `    `: Enter four space characters.

    -   `fpritnf(stderr, "Error number %d, quitting program\n", errno);`: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `j`: Move a line below.

    -   `2dd`: Delete the current and the next line.

    -   Navigate to the parameter `1` of the `exit` function.

    -   `s`: Enter the **Input Mode** to substitute text.

    -   `exit_status`: Enter this string verbatim.

    -   `Esc`: Switch back to the **Command Mode**.

    -   `:w` or `:w somefile`: Optionally save the updated buffer contents to a disk file.
