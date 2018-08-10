### Flex Your Brain

---

01. A directory is technically a file that contains the name and the inode number of the files and sub-directories it houses. The entries in a directory are updated by the kernel on the user's behalf when new files and sub-directories are added or removed.

    The size of a directory is usually small as it doesn't actually store the files and sub-directories it houses, just their name and inode number.

##

02. `cat foo` : Displays the contents of the file **foo** on standard output.

    `cat > foo` : Returns secondary prompt and let the user type any text. Upon encountering end-of-file `[Ctrl-d]` character, the entered text is saved in a file named **foo** in the current directory.

    Use of `[Ctrl-d]` character is required when entering the text from standard input to let the shell know that the text entry is over.

##

03. (i). Yes. The file **foo** will be copied into the directory **bar**.

    (ii). No. An error message is displayed stating **foo** is a directory and is not copied.

##

04. The command:

    `rm -rf bar`

    will delete directory **bar** along with all the files and sub-directories recursively, disregarding the write protection status of any file or sub-directory and non-emptiness of any sub-directory.

    The command:

    `rmdir bar`

    will work only when the directory containing **bar** (current directory here) is not write-protected and is the directory **bar** is completely empty.

##

05. (i). `mv $HOME/include .` : The file or directory named **include** present in the logged in users home directory is moved to the current working directory. The command fails if the user is currently in the home directory.

    (ii). `cp -r bar1 bar2` : Recursively copy the contents of **bar1** to **bar2**. If **bar2** exists, recursively copy contents of **bar1** into **bar2**, thus making the copy of **bar1** a sub-directory of **bar2**.

    (iii). `mv * ../bin` : Moves all the files and directories in the current directory into a directory named **bin** in the parent directory. The command fails if the directory **bin** doesn't exist.

##

06. The three possible reasons could be:

    (i). Read permission is not available for the file **hosts**.

    (ii). Write permission is not available for the file **hosts.bak**.

    (iii). Execute permission not available for the directory **backup**.

##

07. Assuming that the statement "first `a` is empty" means that the directory **a** doesn't contain any files (even hidden), just the sub-directory **a**.

    To accomplish the said task, execute the following command-line:

    `cd ; mv a temp ; mv temp/a . ; rmdir temp`

    Individual commands in the above command-line are described as below:

    -   `cd` : Make home directory as the current working directory.

    -   `mv a temp` : Rename the directory **a** under home directory to something other than **a**, say **temp**.

    -   `mv temp/a .` : Move the directory hierarchy **a** under **temp** directory to the current directory i.e. the home directory.

    -   `rmdir temp` : Remove the **temp** directory normally as it is empty.

##

08. Using repeat factor, an internal command can be repeated **n** number of times.

    Type `/include` to locate the first occurrence of the pattern. Continue pressing the key `n` to repeat the search for further occurrences.

    Using repeat factor, a command can be executed for a fixed number of times. The dot command on the other hand simply repeats the last command once.

##

09. We can ensure that the file is indeed a Postscript file by executing `file` command with the filename as argument and checking for the type information.

    Postscript files are properly formatted for input to Postscript printers.

##

10. (i). We can count the number of filenames by executing:

    `wc -l <foo`

    This command outputs the total number of lines in the file foo.

    (ii). By displaying the octal dump of the files contents by executing:

    `od -bc foo`

    and verifying the presence of a space character (ASCII value of space character is `040` in octal).

##

11. DOS and UNIX text files differ by using different line ending characters. DOS uses the combination of **carriage return** and **line feed** characters (`\r\n`), whereas, UNIX uses **line feed** (`\n`) as the line ending character.

    `dos2unix` command converts a text file from DOS format to UNIX format by removing the extra carriage return characters from the places where the line ending character combination occurs. `unix2dos` command reverses the process by appending the carriage return character before every occurrence of the line feed character.

##

12. The required list can be created by executing the command-line:

    `comm -13 foo1 foo2`,

    which will list entires unique to file **foo2**. The command will not work properly when the files are unsorted or the files contains more than one name per line.

##

13. To add the two files to an archive and compress it, execute the command-line:

    `tar -cvf archive.tar foo.html bar.html ; gzip archive.tar`.

    The compressed archive will be saved as **archive.tar.gz**. To delete the original files execute:

    `rm foo.html bar.html`.

    To reverse the process, uncompress and unarchive the files by executing the command-line:

    `tar -xvf archive.tar.gz`.

    This can be followed by deleting the compressed archive by running the command:

    `rm archive.tar.gz`,

    to completely reverse the process.

##

14. The three advantages of using `zip` over `gzip` are:

    -   zip files can he handled easily both in Windows and UNIX.

    -   `zip` combines archiving and compressing under a single command.

    -   `zip` command provides facility to add/append files to an existing compressed archive.

    To compress and archive a directory hierarchy to send via email execute:

    `zip -r archive.zip direcotry_path`.

    The recipient can easily recreate the directory structure by executing:

    `unzip archive.zip`.

##

15. A command behaves recursively when it can descent a directory hierarchy and execute over all the files, sub-directories and files thereof.

    Examples of commands which support recursive operation are:

    -   `cp -R` : recursively copies a directory hierarchy.

    -   `ls -R` : recursively list files in a directory hierarchy.

    -   `rm -r` : recursively deletes files in a directory hierarchy.

    -   `zip -r` : recursively compress and archives a directory hierarchy.

##
