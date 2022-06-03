##  Chapter 06 - Basic File Attributes

01. Executing the command line:

    `ls -lR / > listing`

    saves the listing of all the files and directories in the whole system in a file named _listing_ in the current directory.

    However, it is worth noting that executing the above command line as a non root user may cause the directories without read permission to be skipped and the error message displayed on the console.

##

02. The significance of the first four fields in `ls -l` output is as described below:

    -   **First column**: File type and the associated permissions for the file owner, group owner and others.

    -   **Second column**: The number of links associated with the file.

    -   **Third column**: The username of the file owner.

    -   **Fourth column**: The name of the group that owns the file.

    These attributes can be changed by the owner of the file as well as the system administrator. (Depending on the release of UNIX i.e. AT&T or BSD. See answer 12 below).

    Only the system administrator can change the group ownership of a file to a group to which the owner doesn't belong.

##

03. (i). This command shows the attributes of the current directory in a long listing format.

    (ii). This command lists the contents of the parent directory in a long listing format.

##

04. (i). If _bar_ is an ordinary file, both the commands display _bar_ as the output.

    (ii). If _bar_ is a directory that contains only a single file or directory also named _bar_, than both the commands display _bar_ as the output.

##

05. No. The group owner of a file can be changed to a group to which the file owner is not a member of by the system administrator.

##

06. (i). By executing the command line:

    `chmod u+rwx,o-rwx foo`

    (ii). By executing the command line:

    `chmod 740 foo`

    In case of absolute assignment, we need to know the default permissions for the file _foo_ to preserve the group permissions.

##

07. The read permission may not be available for the source file. To copy the file, the appropriate read permission is required which can be set either by the file owner or the superuser.

##

08. (i). No one, including the owner of the file, can do anything with the file. The file is technically inaccessible.

    (ii). Anyone can read, write or execute the file. The file is publicly accessible.

##

09. _kumar_ is the group owner of the file _foo_.

    (i). _kumar_ can edit the file as the group owners have the write permission available.

    (ii). Whether or not _kumar_ can delete the file _foo_ would depend on the group ownership and permission set for the directory housing the file _foo_. _kumar_ will be able to delete the file _foo_ if the parent directory belongs to group _kumar_, and has the write permission available for the group.

    (iii). _kumar_ cannot change the permissions of the file _foo_ as the user is not the owner of the file.

    (iv). _kumar_ cannot change the ownership of the file _foo_ as she is not the owner of the file.

##

10. Assume that the file is named _foo_.

    Using relative assignment:

    (i). `chmod a+rwx foo`

    (ii). `chmod a-wx,o-r foo`

    (iii). `chmod a-wx,u-r foo`

    (iv). `chmod a-rwx foo`

    Using absolute assignment:

    (i). `chmod 777 foo`

    (ii). `chmod 440 foo`

    (iii). `chmod 044 foo`

    (iv). `chmod 000 foo`

##

11. No, it could not be done. No file can be created or deleted as the write permission has been revoked for everyone, owner included.

    No, the latter command revokes write permission for everyone on the file/directory named _foo_.

##

12. On an AT&T system, the owner can change the owner and the group of a file. On a BSD system, the owner of a file can be changed only by the system administrator and the user can change the group of a file only to a group to which she already belongs.

##
