### Flex Your Brain

---

01. By executing the command-line:

    `ls -lR / > listing.txt`

    Administrative privilege may be required to run the command-line as many system directories do not have read and execute permissions for non-administrative users, and hence are inaccessible. The same could be achieved by executing the command-line as mentioned below:

    `sudo ls -lR / > listing.txt`.

##

02. The significance of the first four fields in `ls -l` output is described below:

    -   **First column**: Shows the file type and the associated permissions for file owner, group owners and others.

    -   **Second column**: Shows the number of links associated with the file.

    -   **Third column**: Shows the username of the file owner.

    -   **Fourth column**: Names the group that owns the file (by default this is the primary group of the file owner).

    These attributes can be changed by the owner of the file as well as the system administrator. (Depending on the release of UNIX i.e. AT&T or BSD. See answer 12 below).

    Only system administrator can change the group ownership of a file to a group to which the owner doesn't belong.

##

03. (i). `ls -ld .`: Shows the attributes of the current directory in long listing format.

    (ii). `ls -l ..`: Lists the contents of the parent directory in long listing format.

##

04. If **bar** is an ordinary file, both the commands display **bar** as the output.

    If **bar** is a directory that contains only a single file or directory also named **bar**, than both the commands display **bar** as the output.

##

05. Yes. But the group many not be the user's primary group.

##

06. (i). `chmod u+rwx,o-rwx foo`.

    (ii). `chmod 740 foo`.

    In case of absolute assignment, we need to know the default permissions for the file foo to preserve the group permissions.

##

07. The read permission may not be available for the source file. To copy the file, the appropriate read permission is required which can be set either by the file owner or the superuser.

##

08. (i). No one, including the owner of the file can do anything with the file. The file is technically unusable.

    (ii). Anyone can read, write or execute the file. The file is publicly accessible.

##

09. kumar is the group owner of the file foo.

    (i). kumar can edit the file as the group owners have write permission available.

    (ii). Whether or not kumar can delete the file will depend on the group ownership and permission set for the directory housing the file foo. kumar will be able to delete the file foo if the parent directory belongs to group kumar and has write permission available for the group.

    (iii). kumar cannot change the permissions of the file foo as she is not the owner of the file.

    (iv). kumar cannot change the ownership of the file foo as she is not the owner of the file.

##

10. Assume that the file is named **foo**.

    Using relative assignment:

    (i). `chmod a+rwx foo`.

    (ii). `chmod a-wx,o-r foo`.

    (iii). `chmod a-wx,u-r foo`.

    (iv). `chmod a-rwx foo`.

    Using absolute assignment:

    (i). `chmod 777 foo`.

    (ii). `chmod 440 foo`.

    (iii). `chmod 044 foo`.

    (iv). `chmod 000 foo`.

##

11. No.

    No.

##

12. On an AT&T system, owner can change the owner and the group of a file. On a BSD system, owner of a file can be changed only by the superuser and the user can change the group of a file only to a group to which she already belong.

##
