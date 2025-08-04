# Chapter 4 - The File System

1.  Two types of ordinary files are:

    -   **Text** file

    -   **Binary** file

    A text file contains only the commonly identifiable printable characters. On the other hand, a binary file can contain characters from the entire spectrum of the ASCII character set which can include non-printable characters too.

    C program source code, Perl script and ASCII text files are some examples of a text file.

    Executable program, PNG image and WAV audio files are some examples of a binary file.

2.  A device file helps in accessing the device by setting appropriate file attributes on the file representing the device.

3.  (i). This command won't work. Directory _a_ and _a/b_ need to exist before attempting to create the directory _a/b/c_.

    (ii). This command will work. Directory _a_ will be created first followed by the directory _a/b_.

    (iii). This command won't work. The directory _a/b/c_ does not exist yet.

    (iv). This command will work partially. Directory _a_ won't be removed as it's non-empty. Directory _a/b_ will be removed as it's empty.

    (v). This command won't work for ordinary users. _/bin_ is writable only by the root user.

4.  Either _test_ already exists as a file or directory in the current directory, or the user doesn't have write permission in the current directory.

5.  Only **...** and **....** can be created either as a file or a directory. **.** and **..** are special names reserved for use by the operating system to refer to the current and the parent directory.

6.  The directory _bar_ contains hidden files or directories which are not displayed when running `ls bar`.

7.  By referring to charlie's home directory as `~charlie`. (Assuming that charlie's username remains the same.)

8.  `cd ~charlie` changes the current working directory to user charlie's home directory. `cd ~/charlie` changes the current working directory to a directory named _charlie_ in the current user's home directory.

    The former command will fail if there is no user named **charlie**. The latter command will fail if no directory named _charlie_ exists in the current user's home directory.

9.  To refer to _update.sh_ file present in the current directory and not some other file with the same name existing in one of the directories listed in **PATH** variable. This measure is also required if the current working directory (represented by **.**) is not listed in the **PATH** variable.

10. Numbers, followed by uppercase alphabets, followed by lowercase alphabets.

11. (i). Changes the current directory to the root directory _/_. It will work successfully if the user has execute permission available for the root directory.

    (ii). Creates a directory named _bin_ under _/home_ directory. The command will fail if either the user doesn't have write permission available for _/home_ or _/home/bin_ already exists as a directory or file.

    (iii). This command won't work. It attempts to remove the parent directory i.e. _/home_ while being placed in the child directory _/home/kumar_, which the shell won't permit.

    (iv). This command will attempt to list the contents of the parent directory i.e. _/home_. It will succeed only if the user has read permission available for _/home_ directory.
