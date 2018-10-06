01. Two types of ordinary files are:

    - **text** file

    - **binary** file

    A text file contains only printable characters from the ASCII character set, whereas a binary file can contain characters from the entire spectrum of the ASCII character set.

    C or Jave program source code, Perl or shell script and ASCII text readme file are examples of text file.

    Executable program, PNG or JPEG image and WAV audio file are examples of binary file.

##

02. A device file helps in accessing the device by setting appropriate file attributes.

##

03. (i). `mkdir a/b/c`: Won't work. Directory _a_ and _a/b_ need to exist before attempting to create directory _a/b/c_.

    (ii). `mkdir a a/b`: Will work. Directory _a_ will be created first followed by directory _a/b_.

    (iii). `rmdir a/b/c`: Won't work. Directory _a/b/c_ does not exist yet.

    (iv). `rmdir a a/b`: Will work partially. Directory _a_ won't be removed as it's non-empty. Directory _a/b_ will be removed as it's empty.

    (v). `mkdir /bin/foo`: Won't work for ordinary user. _/bin_ is writable only by the root user.

##

04. Either _test_ already exists as a file or directory in the current directory, or the user doesn't have write permission in the current directory.

##

05. Only **...** and **....** can be created either as a file or a directory. **.** and **..** are special names reserved for use by the operating system to refer to the current and the parent directory.

##

06. The directory _bar_ contains hidden files or directories which are not displayed when running `ls bar`.

##

07. By referring to charlie's home directory as **~charlie**.

##

08. `cd ~charlie` changes the current working directory to user charlie's home directory. `cd ~/charlie` changes the current working directory to a directory named _charlie_ in current user's home directory.

    The former command will fail if there is no user named **charlie**. The latter command will fail if no directory named _charlie_ exists in current user's home directory.

##

09. To refer to _update.sh_ file present in the current directory and not some other file with the same name existing in a directory listed in **PATH** variable. This measure is also required if the current working directory (represented by **.**) is not listed in the **PATH** variable.

##

10. Numbers, followed by uppercase alphabets, followed by lowercase alphabets.

##

11. (i). `cd ../..`: Changes the current directory to the root directory _/_. It will work successfully if the user has execute permission available for the root directory.

    (ii). `mkdir ../bin`: Create a directory named _bin_ under _/home_ directory. The command will fail if either the user doesn't have write permission available for _/home_ or _/home/bin_ already exists as a directory or file.

    (iii). `rmdir ..`: Won't work. This command attempts to remove the parent directory i.e. _/home_ while being placed in the child directory _/home/kumar_, which the shell won't permit.

    (iv). `ls ..`: This command will attempt to list the contents of the parent directory i.e. _/home_. Will succeed only if the user has read permission available for _/home_ directory.

##
