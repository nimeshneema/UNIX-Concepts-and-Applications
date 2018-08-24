### Flex Your Brain

---

01. The shell performs all the actions represented by the metacharacters before executing the command-line.

    After completing the pre-processing step consisting of wild-card expansion, variable evaluation, command substitution, opening appropriate files, connecting streams, the shell submits the command-line to the kernel for final execution.

##

02. (i). `{foo[12],Foo5}`.

    (ii). `quit.[coh]`.

    (iii). `{watch.{htm,HTML},Watch.html}`.

    (iv). `.*.swp`.

##

03. (i). `[0-9]?*[!A-Za-z]`.

    (ii). `[!.]??*`.

    (iii). `?*2004*?`.

##

04. (i). A filename comprising of at least 5 characters, where the first character is an alphabet or one of the `[`, `\`, `]`, `^`, `_` or `` ` `` characters.

    (ii). A filename comprising of at least one numeric character.

    (iii). A filename which doesn't end with a numeric character.

    (iv). A non-hidden filename with two character extension where first character is not `s`, second character is not `h` and the extension is not `.sh`.

##

05. `cp chap{0[1-9],1[0-9],2[0-6]} ../`.

    Yes.

##

06. `ls .*`: Lists all the hidden files in the current directory. If there are any hidden sub-directories, their contents are listed.

    `ls *.`: Lists all the non-hidden files in the current directory whose name end with a dot. If there are any non-hidden sub-directories, their contents are listed.

##

07. By executing the command-line:

    `rm -rf "*" "My Documents"`.

##

08. Single and double quoting suppresses the special meaning of metacharacters and treats them literally. Double quoting is preferred when shell variable evaluation or command substitution is desired within the quoted string.

##

line words and bytes

09. `wc foo`: The `wc` command opens the file **foo** and displays the count of lines, words and bytes in the file foo on the standard output.

    `wc < foo`: The `wc` command reads the stream input coming from the file **foo** and displays the count of lines, words and bytes in the file foo on the standard output.

    The command `wc` opens the file in the former case and the shell opens the file in the latter.

##

10. By executing the command-line:

    `cat foo1 - foo2`

    The contents of file **foo1** will be displayed on the terminal and the shell will wait for user input from keyboard. Once the input from the keyboard is made and the same is terminated with end-of-file character, the contents of the file **foo2** will be displayed on the terminal and the prompt returned subsequently.

##

11. (i). The contents of the file **foo** are overwritten by the text entered via standard input.

    (ii). file **foo** is created anew and the output of command `who` is appended to it.

    (iii). The file **foo** is blanked out.

    (iv). The contents of the file **foo** is replaced by a single newline `\n` character.

##

12. The file **newlist** is present in the list of files along-with other files listed as an output of `ls` command. **newlist** finds its way into the list as the shell opens the file before `ls` command comes into action.

##

13. File descriptor is a unique integer number assigned to an open file by the UNIX kernel.

    `2>` is used as redirection symbol for standard error because **2** is the default file descriptor for the Standard Error stream.

##

14. The error message is thrown not by `cat` command but by the shell. Any error thrown by `cat` command will be redirected to the file **bar**. Here the command doesn't get to act as the shell fails to locate the file **foo**, hence the error.

##

15. Three conditions needs to be satisfied here:

    -   `prog1` should be able to write to Standard Output.

    -   `prog2` should be able to read from Standard Input and write to Standard Output.

    -   `prog3` should be able to read from Standard Input.

##

16. By executing the following command-line:

    `who | wc -l`.

##

17. (i). `echo "$(cal)"`.

    (ii). `echo "$(cat list)"`.

##

18. (i). Total size of all C source files (in bytes) can be stored in the variable named **count** by executing the following command-line:

    `count=$(cat *.c | wc -c)`.

    (ii). Assuming that the file is named foo.c, the total number of lines can be stored in the variable named **count** by executing the following command-line:

    `count=$(cat foo.c | wc -l)`.

##

19. By executing the command-line:

    `count="$(cat `cat foo` | wc -m)"`

    First of all `cat foo` is expanded which lists all the file names. Further invocation of `cat` write to Standard Output the contents of all the files listed from the last step. The Standard Output from this step is piped to `wc` command which counts the total number of characters using `-m` option and the resulting value is assigned to the `count` variable.

##
