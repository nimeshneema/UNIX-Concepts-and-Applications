# Chapter 6 - Basic File Attributes

1.  You can get a complete listing of all files and directories in the whole system by using the **ls** command with the `-R` (recursive) option and an absolute pathname to the root directory. To save this output to a file, you use the `>` redirection operator.

    ```
    ls -R / > all_files.txt
    ```

    However, it is worth noting that executing the above command line as a non root user may cause the directories without read permission to be skipped and an error message displayed on the console.

2.  The first four fields of the `ls -l` output are significant for understanding a file's basic properties and security.

    -   First column - File Type and Permissions: The first character indicates the file type (e.g., `-` for a regular file, `d` for a directory), followed by nine characters representing permissions (`r`, `w`, `x`) for the owner, group, and others.

    -   Second column - Links: The number in the second field shows how many links (names) the file has.

    -   Third column - Ownership: The third field is the user who owns the file, usually the one who created it.

    -   Fourth column - Group Ownership: The fourth field is the group that owns the file.

    The **owner** of a file can change all of its attributes. The **superuser** can also change all attributes for any file on the system.

    The file ownership attribute can be changed from one user to another using **chown** command only by the superuser.

3.  The significance of commands:

    1.  `ls -ld .`: This command displays the attributes of the current directory (`.`) itself, rather than its contents. The `-d` option tells **ls** command to treat the directory as a file.

    2.  `ls -l ..`: This command displays a long listing of the files and subdirectories found in the parent directory (`..`).

4.  The commands `ls bar` and `ls -d bar` will display the same output, the string `bar`, if `bar` is an ordinary file.

    The second way this could happen is if `bar` is a directory containing a file named `bar`. `ls bar` would display the file name `bar`, while `ls -d bar` would display the directory `bar` itself.

5.  No, the owner does not always belong to the same group as the group owner of a file. While by default, a file's group owner is the group to which the owner belongs, the owner can change the group owner of the file using the **chgrp** command.

6.  To assign all permissions to the owner and remove all permissions from others on a file named `foo`, you can use either relative or absolute assignment methods.

    1.  `Relative Assignment`: You would use two separate expressions with `chmod`, separated by a comma.

        ```
        chmod u+rwx,o-rwx foo
        ```

        This command adds all permissions to the user while explicitly removing all permissions from others. This approach doesn't require any assumptions about the file's default permissions.

    2.  `Absolute Assignment`: This method sets all nine permission bits at once, so it is necessary to consider the group's permissions as well. Assuming the group has read and execute permissions (`r-x` or `5`), the octal representation for the command would be `750`.

        ```
        chmod 750 foo
        ```

        This sets the user's permissions to `rwx` (7), the group's permissions to `r-x` (5), and others' permissions to `---` (0). This method requires an assumption about the group's desired permissions.

7.  The reason you received the error message "cannot create file foo" is that the source file in the other user's directory is likely not readable by you A copy command requires read permission on the source file to access its contents. While you have write permission in your own directory, you cannot read the other user's file.

    To copy the file, you would need to ask the other user to grant you read permission on the file, or ask them to copy the file to a location where you have read permission.

8.  From a security viewpoint, the consequences of a file having these permissions are as follows:

    1.  000: This file is useless for all categories of users because it cannot be read, written to, or executed. However, the file can still be deleted by the owner, as the ability to delete a file is controlled by the permissions of the directory it is in, not the file's own permissions.

    2.  777: This file is extremely dangerous because it is universally readable, writable, and executable. Any user on the system can read, modify, or delete its contents. You should never set permissions this way unless you have a specific and highly controlled reason, and even then, it is not recommended.

9.  The `ls -l` output shows that the owner of the file `foo` is sumit, while the current user is kumar. The permissions for `others` are not set (`---`), so the permissions for the kumar group apply. Kumar is also the group owner, as seen in the fourth field of the output. The permissions for the group are `rw-`.

    Based on this information, kumar can:

    1.   Edit: Yes, the group has `w` (write) permission.

    2.  Delete: Yes, if Kumar has write permission on the directory where the file `foo` resides. This is not shown in the `ls -l` output, but the directory has write permission.

    3.  Change permissions: No, only the owner (sumit) or the superuser can change the permissions of the file.

    4.  Change ownership: No, only the superuser can change the ownership of a file on a BSD-based system.

10. The file's current permissions are `rw-r-xr--`.

    1.  To change to `rwxrwxrwx`:

        -   Relative: `chmod u+x,g+wx,o+rwx filename` or `chmod ugo+rwx filename` or `chmod a+rwx filename`.

        -   Absolute: `chmod 777 filename`.

    2.  To change to `r--r-----`:

        -   Relative: `chmod u-w,g-wx,o-rw filename`

        -   Absolute: `chmod 440 filename`

    3.  To change to `--r--r--`:

        -   Relative: `chmod u-rwx,g-x,o-w filename`

        -   Absolute: `chmod 244 filename`

    4.  To change to `--------`:

        -   Relative: `chmod a-rwx filename`

        -   Absolute: `chmod 000 filename`

11. After running `chmod a-w .`, you cannot create or remove a file in the current directory because you have removed write permission from the directory itself. Directory write permission is required to create or remove files and subdirectories, regardless of a file's individual permissions.

    The command `chmod a-w foo` is different because it only removes write permissions from the file named `foo`, not the directory. You would still be able to create and remove other files and directories.

12. To determine whether your system uses the BSD or AT&T version of **chown** and **chgrp**, you can test their behavior.

    For **chown**, try to change the ownership of a file that you own to another user. If the command succeeds, your system likely uses the AT&T version where the owner can change ownership. If it fails and says "Permission denied", it's a BSD-based system, and only the superuser can perform this action.

    For **chgrp**, as the owner of a file, try to change the group ownership to a group you do not belong to. If the command succeeds, it's an AT&T-based system. If it fails, but then succeeds when you change the group to one you are a member of, it's a BSD-based system.
