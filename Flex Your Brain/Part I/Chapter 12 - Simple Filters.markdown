## Chapter 12 - Simple Filters

01.	Assume that the file is named _foo_. Execute the following command line to print it in reverse:

	`pr -n -t foo | sort -nr | cut -f 2 -`

##

02.	Executing the alias `lastedit` as shown below will bring up the last modified file from among all the files present in the current directory hierarchy and open it with the vi editor. It works with both Korn and Bash shell.

	`alias lastedit="vi $(ls -t | head -n 1)"`

##

03.	Assume that the file in question is named _foo_. Execute the following command lines:

	(i). `head -n 10 foo | tail -n -6`

	(ii). `tail -n 2 foo | head -n 1`

##

04.	By executing the following command line:

	`date | tr -s '\040' | tr '\040' '\012'`

	To join the fields to get back the original output, execute:

	`date | tr '\040' '\012' | tr '\012' '\040'`

##

05.	By executing the following command line:

	`ps -A | tr -s "\040" | sort -t"\040" -k 4`

##

06.	Assume that the file is named _foo_. Execute the following command line:

	`tr -cd '?' < foo | wc -m`

##

07.	`cut -d ":" -f1 /etc/passwd | tail -n +11`

##

08.	`echo $PATH | tr ":" "\012"`

##

09.	`sort -t ":" -n -k 3 -k 4 /etc/passwd`

##

10.	`ls -S | head -5`

##

11.	Executing the following command line sets the variable named **length** to the length of line **xxx** of the file _emp.lst_:

	`length=$(head -n xxx emp.lst | tail -n 1 | wc -m)`

##

12.	First of all, we need to get rid of the extra information present in both the files, except username, sort the resulting list, and then save them in different files. The same can be accomplished by executing the following:

	`cut -d ":" -f1 foo1 | sort -u > foo11`

	`cut -d ":" -f1 foo2 | sort -u > foo22`

	The resulting output for files _foo1_ and _foo2_ are saved in files _foo11_ and _foo22_ respectively.

	Now, executing the following command line achieves the desired results:

	(i). `comm -23 foo11 foo22`

	(ii). `comm -13 foo11 foo22`

	(iii). `comm -12 foo11 foo22`

##

13.	(i). Execute the following command:

	`who | cut -d " " -f1 | sort | uniq -c | sort -n | grep -v "1 " | cut -c 6-`

	Each logged-in user is listed with a count of their number of logins. Users who have logged in more than once can be easily identified from this list.

	(ii). `mailx -s "Logged in Users" root < $(who | cut -d " " -f1 | sort | uniq)`

##

14.	Both `sort -u` and `uniq` removes repeated lines from a file. While `sort -u` both sorts a file and displays unique lines, `uniq` expects a sorted file as input.

##

15.	By executing the following command line:

	`tr -s " " < foo | cut -d " " -f 2,3,6 | sort | uniq -c | sort -n`

##
