# Chapter 4 - The File System

1.  The two types of ordinary files are:

    -   **Text files**

    -   **Binary files**

    A **text file** contains only printable characters and is often human-readable. Each line in a text file is terminated by a newline character. Examples include C and Java source code, shell scripts, and plain text documents.

    A **binary file** contains both printable and unprintable characters, covering the entire ASCII range. These files are typically not human-readable and can disturb a terminal's settings if you try to display them directly. Examples include UNIX commands, compiled executables, and picture or video files.

2.  A **device file** helps in accessing a device by acting as a symbolic representation of it within the file system. The device file itself contains no data. Instead, its attributes, which are stored elsewhere, identify the physical device to the kernel. When a user or program performs a read or write operation on a device file, the kernel uses these attributes to interact with and operate the corresponding device.

3.  1.  `mkdir a/b/c`: This command will **not work** because it attempts to create a directory `b` inside `a`, and then `c` inside `b`, but `a` and `a/b` do not exist yet. The parent directories must be created before their subdirectories.

    2.  `mkdir a a/b`: This command **will work**. It first creates the directory `a` and then, because `a` now exists, it successfully creates the subdirectory `a/b`. The order of arguments is crucial here.

    3.  `rmdir a/b/c`: This command will **not work**, as the directory `a/b/c` does not exist yet.

    4.  `rmdir a a/b`: This command **will not work** as written. The `rmdir` command works on the lowest-level directory first. It will attempt to remove `a`, but `a` is not empty because it contains `b`. The command to correctly remove this structure would be `rmdir a/b a`.

    5.  `mkdir /bin/foo`: This command **will likely not work**. The `/bin` directory is a system-level directory owned by the root user. A non-privileged user would receive a "Permission denied" error when trying to create a directory there.

4.  If the `mkdir test` command fails, the possible reasons are:

    -   A directory named `test` **already exists** in the current directory.

    -   The user does **not have the correct permissions** to create files or directories in the current directory.

5.  The only one of these that can be created is `...` or `....`.

    -   `.` (a single dot) is used to refer to the current directory.

    -   `..` (two dots) is used to refer to the parent directory of the current directory.

    -   `...` and `....` are **not special characters** to the shell and are treated as normal filenames. Therefore, you can successfully create files or directories with these names using a command like `mkdir ...` and `mkdir ....`.

6.  The `rmdir bar` command failed because `rmdir` can only remove **empty** directories. The `ls bar` command may have shown no files because it does not show hidden files—those that begin with a dot (`.`).

7.  To develop a script that refers to a file in `charlie`'s home directory and works even if the home directory changes, you should use the tilde (`~`) symbol followed by the username. The shell will automatically expand this to the correct home directory path.

    You can specify the location of the file in your script like this: `~charlie/filename`.

8.  -   `cd ~charlie` will attempt to change the current directory to **charlie's home directory**. The shell expands `~charlie` to the absolute pathname of charlie's home directory (e.g., `/home/charlie`).

    -   `cd ~/charlie` will attempt to change the current directory to a subdirectory named `charlie` located inside **your own home directory**. The shell expands `~` to your home directory, and then looks for a `charlie` subdirectory within it.

    It is possible for both commands to work. This would happen if a subdirectory named `charlie` exists within your home directory, and the user `charlie` also has their own home directory on the system. However, they refer to two completely different locations.

9.  You sometimes run a command with the prefix `./` because `.` represents the **current directory**.

    The command `update.sh` fails because the shell searches for executable files only in the directories specified by the `PATH` variable. The current directory (`.`) is often not included in `PATH` for security reasons.

    The command `./update.sh` explicitly tells the shell to look in the current directory for the file `update.sh` and execute it, bypassing the `PATH` search.

10. The sort order prescribed by the ASCII collating sequence gives priority in this order:

    1.  **Numbers** (0-9)

    2.  **Uppercase** letters (A-Z)

    3.  **Lowercase** letters (a-z)

11. 1.  `cd ../..`: This command is presumed to change the current directory two levels up in the hierarchy. Starting from `/home/kumar`, the first `..` would move you to `/home`, and the second `..` would move you to `/`. This command **will work**.

    2.  `mkdir ../bin`: This command is presumed to create a directory named `bin` inside the parent directory of `/home/kumar`, which is `/home`. This command **will work**, if you have the permissions to create a directory in `/home`, otherwise not.

    3.  `rmdir ..`: This command is presumed to remove the parent directory, `/home`. This command **will not work** because `/home` is not empty (it contains the directory `kumar`), and `rmdir` can only remove empty directories. Also, you do not have permission to delete the home directory.

    4.  `ls ..`: This command is presumed to list the contents of the parent directory, `/home`. It will display the files and subdirectories found there, such as `kumar`. This command **will work**.
