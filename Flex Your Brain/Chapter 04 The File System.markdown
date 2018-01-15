### Flex Your Brain

---

01. Ordinary files can be classified into two types: **text** and **binary**. A text file generally contains only printable characters from the ASCII character set, whereas a binary file contain characters from the entire spectrum of the ASCII character set.

    C program source code, perl script file and ASCII text readme files are examples of text files.

    Compiled C executable, a PNG image file and a wav audio file are examples of binary files.

##

02. A device file helps in accessing a device by making itself available for reading and writing via system calls and by setting appropriate file attributes.

##

03. (i). `mkdir a/b/c` : Won't work. Directory `a` and `a/b` needs to exist before attempting to create directory `a/b/c`.

    (ii). `mkdir a a/b` : Will work. Directory `a` will be created first followed by directory `a/b`.

    (iii). `rmdir a/b/c` : Won't work. Directory `a/b/c` does not exist yet.

    (iv). `rmdir a a/b` : Will work partially. Directory `a` won't be removed as it's non-empty. Directory `a/b` will be removed as it's empty.

    (v). `mkdir /bin/foo` : Won't work. `/bin` is writable only by the root user. To create a file or directory in `/bin`, either login as root user or use `sudo` command.

##

04. Either `test` already exists as a file or directory in the current directory, or the user doesn't have write permission for the current directory.

##

05. Only `...` and `....` can be created either as a file or a directory. `.` and `..` are special names reserved for use by the operating system to refer to the current and the parent directory.

##

06. The directory `bar` may contain hidden files and hence may not actually be empty. Alternatively, the user may not have write permission for the current directory (which contains the directory `bar`).

##

07. By referring to charlie's home directory as `~charlie`.

##

08. `cd ~charlie` changes the current working directory to charlie's home directory. `cd ~/charlie` attempts to change the current working directory to a directory named `charlie` inside charlie's home directory. The latter command may fail if no such directory exists.

##

09. To refer to the `update.sh` file present in the current directory and not some other file with the same name existing in a directory listed in the user's **PATH**. This measure will be required if the current working directory (represented by `.`) is not listed in the **PATH** variable.

##

10. Numbers, followed by uppercase alphabets, followed by lowercase alphabets.

##

11. (i). `cd ../..` : Changes the current directory to the root directory `/`. It will work successfully if the user has execute permission available for the root directory.

    (ii). `mkdir ../bin` : Create a directory named `bin` under `/home` directory. The command will fail if either the user doesn't have write permission available for `/home` or `/home/bin` already exists as a directory or file.

    (iii). `rmdir ..` : Won't work. This command attempts to remove the parent directory i.e. `/home` while being placed in the child directory `/home/kumar`, which the shell doesn't permit.

    (iv). `ls ..` : This command will attempt to list the contents of the parent directory i.e. `/home`. Will succeed only if the user has read permission available for `/home`.

##
