# Chapter 5 - Handling Ordinary Files

1.  A directory does not contain files themselves, but rather their **names** and a unique number associated with each name, called the **inode number**. When a file is created or removed, the kernel updates the corresponding directory by adding or removing this entry. A directory is essentially a list of filenames and their inode numbers.

    The size of a directory is typically small because it only stores this list of entries, not the actual file data. The data for the files is stored separately on the disk, and the directory entry simply points to it via the inode number. This design allows the directory itself to remain compact, regardless of the size of the files it contains.

2.  The former command displays the contents of the file named `foo` present in the current directory.

    The latter command returns a secondary prompt and lets the user type any text. Upon encountering the end-of-file character [Ctrl-d], the entered text is saved in a file named `foo` in the current directory. If a file named `foo` already exists in the current directory, it is overwritten.

    Use of end-of-file character is required when entering the text from standard input to let the shell know that the text entry is over. At this point the file is saved and the prompt returns.

    Running the command `cat foo` does not require [Ctrl-d] because it reads from a file, not the keyboard, and it terminates automatically once it reaches the end of that file.

3.  1.  Yes, the command would work. The file `foo` would be copied into the directory named `bar`.

    2.  No, the command won't work. An error message is displayed stating that `foo` is a directory and is not copied.

4.  The command `rm -rf bar` will delete the directory `bar` along with all the files and sub-directories recursively, disregarding the write protection status of any files or sub-directory and non-emptiness of any sub-directory.

    The command `rmdir bar` will work only when the directory `bar` is empty and its parent directory (current directory here) is not write-protected.

5.  1.  The file or directory named `include` present in the logged-in user's home directory is moved to the current working directory.

    2.  The command recursively copies the contents of the directory `bar1` to `bar2`. If `bar2` exists and is a directory, recursively copy contents of the directory `bar1` into `bar2`, thus making a copy of `bar1` a sub-directory of `bar2`.

    3.  The command moves all the files and directories in the current directory into a directory named `bin` in the parent directory.

6.  The three possible reasons can be:

    1.  Read permission is not available for the file `hosts`.

    2.  Write permission is not available for the file `backup/hosts.bak`.

    3.  Execute permission is not available for the directory `backup`.

7.  By executing the command-line: `cd ; mv a temp ; mv temp/a . ; rmdir temp`

    Individual commands in the above command line are described below:

    -   `cd`: Changes the working directory to the user's home directory.

    -   `mv a temp`: Rename the directory `a` under home directory to `temp`.

    -   `mv temp/a .`: Move the directory hierarchy `a` under `temp` directory to the home directory.

    -   `rmdir temp`: Remove the directory named `temp`.

8.  Using the repeat factor, an internal command within **more** command can be made to run multiple times.

    Type `/include` to locate the first occurrence of the pattern. Continue pressing the key `n` to repeat the search for further occurrences.

    Using the repeat factor a command can be executed for a set number of times. The dot command on the other hand simply repeats the last command once.

9.  We can ensure that the file is indeed a Postscript file by executing **file** command with the filename as an argument and checking for the file type information.

    Postscript files are properly formatted for input to a Postscript printer.

10. 1.  We can count the number of filenames by executing the command-line, `wc -l < foo`, which outputs the total number of lines in the file `foo`.

    2.  By displaying the octal dump of the files contents by executing the command-line, `od -bc foo` and checking for the presence of space character in the output.

11. DOS and UNIX text files differ by using different line ending characters. DOS uses a combination of **carriage return** and **line feed** characters (`\r\n`), whereas, UNIX uses **line feed** (`\n`) as the line ending character.

    **dos2unix** command converts a text file from DOS format to UNIX format by removing the extra carriage return characters from the places where the line ending character combination occurs.

    **unix2dos** command reverses the process by appending the carriage return character before every occurrence of the line feed character.

12. The desired list can be created by executing the command-line `comm -13 foo1 foo2` which will list the entries unique to the file `foo2`. The command will not work properly when the files are unsorted, or the files contains more than one name per line.

13. To add the two files to an archive and compress it, execute the command-line:

    ```
    tar -cvf archive.tar foo.html bar.html ; gzip archive.tar
    ```

    The compressed archive will be saved as `archive.tar.gz`. To delete the original files execute the command-line:

    ```
    rm foo.html bar.html
    ```

    To reverse the process, uncompress and unarchive the files by executing the command-line:

    ```
    tar -xvf archive.tar.gz
    ```

    This can be followed by deleting the compressed archive by running the command-line:

    ```
    rm archive.tar.gz
    ```

    to completely reverse the process.

14. The three advantages of using **zip** over **gzip** are:

    -   zip files can be handled easily both in Windows and UNIX.

    -   zip combines archiving and compressing under a single command.

    -   zip command provides facility to add/append files to an existing compressed archive.

    To compress and archive a directory hierarchy to send via email execute the command-line:

    ```
    zip -r archive.zip direcotry_path
    ```

    The recipient can easily recreate the directory structure by executing the command-line:

    ```
    unzip archive.zip
    ```

15. A command behaves recursively when it can descent a directory hierarchy and execute over all the files, sub-directories and files thereof.

    Examples of commands which support recursive operation along with relevant option are:

    -   `cp -R source_directory target_directory`: Recursively copies a directory hierarchy.

    -   `ls -R directory_path`: Recursively lists files in a directory hierarchy.

    -   `rm -r directory_path`: Recursively deletes files in a directory hierarchy.

    -   `zip -r directory_path`: Recursively compress and archives a directory hierarchy.
