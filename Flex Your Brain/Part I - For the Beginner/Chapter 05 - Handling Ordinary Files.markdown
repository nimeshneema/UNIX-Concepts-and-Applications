##  Chapter 05 - Handling Ordinary Files

01. A directory is technically a file containing the name and the inode number of files and sub-directories that it contains. The entries are updated by the kernel on the user's behalf when files and sub-directories are added, renamed or deleted.

    The size of a directory file is usually small as it doesn't store the files and subdirectories it contains, just their name and inode numbers.

---

02. The former command displays the contents of the file named _foo_ present in the current directory.

    The latter command returns a secondary prompt and lets the user type any text. Upon encountering the end-of-file (`Control + d`) character, the entered text is saved in a file named _foo_ in the current directory.

    Use of `Control + d` is required when entering the text from standard input to let the shell know that the text entry is over.

---

03. (i). Yes, the command would work. The file _foo_ would be copied into the directory named _bar_.

    (ii). No, the command won't work. An error message is displayed stating that _foo_ is a directory and is not copied.

---

04. The first command will delete the directory _bar_ along with all the files and sub-directories recursively, disregarding the write protection status of any files or sub-directory and non-emptiness of any sub-directory.

    The second command will work only when the directory _bar_ is empty and its parent directory (current directory here) is not write-protected.

---

05. (i). The file or directory named _include_ present in the logged-in user's home directory is moved to the current working directory.

    (ii). The command recursively copies the contents of _bar1_ to _bar2_. If _bar2_ exists and is a directory, recursively copy contents of _bar1_ into _bar2_, thus making a copy of _bar1_ a sub-directory of _bar2_.

    (iii). The command moves all the files and directories in the current directory into a directory named _bin_ in the parent directory.

---

06. The three possible reasons can be:

    (i). Read permission is not available for the file _hosts_.

    (ii). Write permission is not available for the file _backup/hosts.bak_.

    (iii). Execute permission is not available for the directory _backup_.

---

07. By executing the following command line:

    `cd ; mv a temp ; mv temp/a . ; rmdir temp`

    Individual commands in the above command line are described below:

    -   `cd`: Changes the working directory to the user's home directory.

    -   `mv a temp`: Rename the directory _a_ under home directory to _temp_.

    -   `mv temp/a .`: Move the directory hierarchy _a_ under _temp_ directory to the home directory.

    -   `rmdir temp`: Remove the directory named _temp_.

---

08. Using the repeat factor, an internal command within `more` command can be made to run multiple times.

    Type `/include` to locate the first occurrence of the pattern. Continue pressing the key `n` to repeat the search for further occurrences.

    Using the repeat factor a command can be executed for a set number of times. The dot command on the other hand simply repeats the last command once.

---

09. We can ensure that the file is indeed a Postscript file by executing `file` command with the filename as an argument and checking for the file type information.

    Postscript files are properly formatted for input to a Postscript printer.

---

10. (i). We can count the number of filenames by executing the command line:

    `wc -l < foo`

    which outputs the total number of lines in the file _foo_.

    (ii). By displaying the octal dump of the files contents by executing:

    `od -bc foo`

    and checking for the presence of space character in the output.

---

11. DOS and UNIX text files differ by using different line ending characters. DOS uses a combination of **carriage return** and **line feed** characters (**\r\n**), whereas, UNIX uses **line feed** (**\n**) as the line ending character.

    `dos2unix` command converts a text file from DOS format to UNIX format by removing the extra carriage return characters from the places where the line ending character combination occurs.

    `unix2dos` command reverses the process by appending the carriage return character before every occurrence of the line feed character.

---

12. The desired list can be created by executing the command line:

    `comm -13 foo1 foo2`

    which will list the entries unique to the file _foo2_. The command will not work properly when the files are unsorted, or the files contains more than one name per line.

---

13. To add the two files to an archive and compress it, execute the command line:

    `tar -cvf archive.tar foo.html bar.html ; gzip archive.tar`

    The compressed archive will be saved as _archive.tar.gz_. To delete the original files execute:

    `rm foo.html bar.html`

    To reverse the process, uncompress and unarchive the files by executing the command line:

    `tar -xvf archive.tar.gz`

    This can be followed by deleting the compressed archive by running the command:

    `rm archive.tar.gz`

    to completely reverse the process.

---

14. The three advantages of using **zip** over **gzip** are:

    -   zip files can be handled easily both in Windows and UNIX.

    -   zip combines archiving and compressing under a single command.

    -   zip command provides facility to add/append files to an existing compressed archive.

    To compress and archive a directory hierarchy to send via email execute:

    `zip -r archive.zip direcotry_path`

    The recipient can easily recreate the directory structure by executing:

    `unzip archive.zip`

---

15. A command behaves recursively when it can descent a directory hierarchy and execute over all the files, sub-directories and files thereof.

    Examples of commands which support recursive operation are:

    -   `cp -R`: Recursively copies a directory hierarchy.

    -   `ls -R`: Recursively lists files in a directory hierarchy.

    -   `rm -r`: Recursively deletes files in a directory hierarchy.

    -   `zip -r`: Recursively compress and archives a directory hierarchy.

---
