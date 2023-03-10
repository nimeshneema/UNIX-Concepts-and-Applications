##  Chapter 11 - More File Attributes

01. True.

    In a UNIX system, each available file system directory structure is headed by a root directory. Among all the available file systems, one of them is designated as the root file system. At the time of booting, all the secondary file systems attach themselves to the root file system, thereby creating an illusion of a single file system.

---

02. The three time stamps maintained in the inode for every file are:

    01. Time of creation.

    02. Time of last modification.

    03. Time of last access.

    To display them for the file _foo_ execute the following command line:

    -   `ls -l foo`: Display the time of last modification.

    -   `ls -lu foo`: Display the time of last access.

---

03. When a file is linked (hard link), the link count of the file in incremented by one in the inode.

    When the link is removed, the link count is decremented by one in the inode.

    In the case of soft link, no changes are made in the inode.

---

04. (i). A file named _bar_ in created anew.

    (ii). The `ln` command throws an error message stating that the file _bar_ exits.

    (iii). A file named _foo_ is created inside the directory _bar_.

---

05. Two application areas of hard links are:

    (i). Protect against accidental deletion by creating a backup link.

    (ii). Freedom from maintaining separate disk files for programs with little difference.

    Two main disadvantages of using hard links are:

    (i). A hard link for a file cannot be created on a separate file system.

    (ii). It is not possible to create a hard link for a directory.

---

06. Fast symbolic link is a feature available in Linux, where the pathname is stored in the inode itself.

    When the original file pointed to by a symbolic link is deleted, the link itself becomes useless and is called a dangling symbolic link.

---

07. By creating a symbolic link to the new location with the old path by executing the following:

    `ln -s $HOME/internet/progs $HOME/progs`

---

08. The command can fail if the execute permission is not available for the directory _bar_.

---

09. Whether the file can be deleted or not depends upon the write permission available for the containing directory. The file can be deleted with write permission set on directory otherwise not.

    The presence or absence of execute permission of either file or directory has no role to play here.

---

10. (i). Any newly created directory will have open permissions for all users. Anyone can read it, create/delete files in it, or change to it, thereby compromising on privacy. Any newly created files will be writable by anyone.

    In simpler terms, anyone in the system can read or write any file without restriction.

    (ii). Any newly created directory can be read by, or changed to by anyone, there compromising on privacy. Any newly created files can be read by anyone which may not be desirable.

    In simpler terms, anyone in the system can read any file without restriction.

---

11. (i). The former command line displays a list of files and directories in the current directory in a long listing format, sorted in an ASCII collating sequence by name.

    The latter command line displays a similar output, only the order of listing is by modification time instead of name.

    (ii). The former command line sorts the listing by the time of last access.

    The latter command line sorts the listing by the time of last access followed by the time of modification.

---

12. The desired `find` command line are:

    (i). `find ~ \( -name "*.html" -o -name "*.HTML") -print`

    (ii). `find ~ -inum 9076 -print`

    (iii). `find ~ -type d -perm 666 -print`

    (iv). `find ~ -mtime 1 -print`

    None of the above commands would fail.

---

13. The desired `find` command line are:

    (i). `find . -mtime -1 -exec mv ../posix {} \;`

    (ii). `find ~ \( -name a.out -o -name core\) -exec rm -fi {} \;` or `find ~ \( -name a.out -o -name core\) -ok rm -fi {} \;`

    (iii). `find /oracle -name login.sql -exec cp {} . \;`

    (iv). `find ~ -type d -exec chmod 755 {} \; ; find ~ -type f -exec chmod 644 {} \;`

---
