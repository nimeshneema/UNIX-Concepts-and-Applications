## Chapter 13 - Filters Using Regular Expressions - grep And sed

01.	Both wildcards and regular expressions are used to define a search pattern. However, wildcards are a feature of the shell, while regular expressions are not.

	Regular Expressions are a well-defined and systematic way of using a sequence of characters that define a search pattern. Regular expressions are used with commands that support its usage and it has nothing to do with the shell.

	Regular expressions use its own set of special characters called metacharacters, which overshadows the wildcard characters used by the shell. Quoting is used to ensure that the shell doesn't attempt to interpret the regular expression characters.

##

02.	The asterisk character is used thrice in the command line. Here's the meaning of each occurrence:

	-	The first asterisk is interpreted as a regular expression metacharacter. It matches the longest string starting with _botswana_ and ending with _birds_.

	-	The second and third asterisks are interpreted as shell wildcard characters. They match all the files which contain the string `.htm` in their filename.

	Thus, the command line searches for the lines matching the pattern starting with _botswana_ and ending with _birds_, in all the files in the current directory, which contain the string `.htm` in their filename.

##

03.	Use the following command line:

	`ls -l | grep "^-r-xr-xr-x"`
	
	This will give a `ls` long listing of all the ordinary files in the current directory which are not writable by any user.
	
	**P.S.**: The following command line can be used to get just the desired file names without the excessive verbiage thrown by `ls -l` command. It uses two additional commands `tr` and `cut` in the command line.
	
	`ls -l | tr -s " " | grep "^-r-xr-xr-x" | cut -d " " -f9`

	The explanation of the above command line is as follows:
	
	`tr` is translate characters command, and is used to compress all the occurrences of multiple consecutive space characters by a single space character.

	`cut` command is used to extract the last item from every line where the items are separated by each other with a single space character.

	The output of `ls -l` command is piped through the `tr` command to squeeze all the occurrences of multiple consecutive spaces by a single space so that the desired output can be easily extracted using the `cut` command.

	While the `cut` command has been discussed previously in the text, `tr` command is not. Refer to the `tr` command man page to learn more about it and the available options.

##

04.	The command line displays the same number of lines as present in the file named _foo_. The mentioned Basic Regular Expression is trying to match occurrences of zero or more characters, which is technically every line in the file.

	Removing the quotes would cause the `.*` pattern to be interpreted as wildcard by the shell instead. This wildcard expansion step (which is performed by the shell before the `grep` command is executed) would replace `.*` with all the file and directory names beginning with a `.` character. This would include, at the minimum, the current and the parent directory names which are represented with `.` and `..` respectively.
	
	So the expanded command line would look like this:
	
	`grep . .. <FILE/DIRECTORY 1> <FILE/DIRECTORY 2> ... <FILE/DIRECTORY N> foo`
	
	where each one of _<FILE/DIRECTORY 1>_ is a file or directory name beginning with a `.` character.
	
	Now the above command line, when executed, tries to match the occurrence of `.` (the second token in the command line just after `grep`) in every file or directory that follows in the remainder of the command line. Since `grep` doesn't work over directory names, an error message would be displayed on the standard output stating that an item is a directory. For any filenames, each of its lines are matched and outputted on the standard output with the filename prepended.

	Since the filename _foo_ occurres as the last argument, every one of its line would be displayed too in a similar manner, but after the contents of all the hidden files listed before it are displayed.

##

05.	The command line would print the string `foo` on standard output if the file _foo_ contains a tab character.

##

06.	Use the following command line:

    ```grep "`date +"%d/%m"`" emp.lst | cut -d "|" -f2```

##

07.	(i) The former expression matches a numric string containing the digits 0 to 9, with the string of length zero or more.

	The latter matches a numeric string while ensuring that the string contains at least one digit.

	So, the former expression can match zero length numeric strings while the latter matches the string consisting of at least one digit.

	(ii) The former matches a single character at the beginning of a line which could be anything but the caret (`^`) character.
		
	The latter matches the presence of the string `^^` at the beginning of a line.

##

08.	The first command line matches all the lines in the file foo, that has, as its first character, anything other than small case alphabet.

	The second command line matches all the lines in the file foo, that does not begin with a small case alphabet as its first character.

	Thus, the two commands are equivalent.

##

09.	(i) `jeff[er][er](ie|y)s?`

	(ii) `hitch(e|i)ng?`

	(iii) `[Hh](e|i)a?rd`

	(iv) `di(x|ck)s?(on)?`

	(v) `[Mm](c|a)gh?ee`

##

10.	Assuming that the name of the file is foo, the following command lines can be used to remove blank lines containing nothing or whitespace characters (i.e. one or more space, tab or newline character)

	(i)	`grep -v -e "^$" -E "^(\r\n|\n|\r)|[\t ]+)$" foo`
        
	(ii) `sed -n '/(^$|\t+|\n|\r\n|\r)/d' foo` or `sed -n '/^$/d' foo`

##

11.	Locate lines containing only printf but not fprintf using (i) grep (ii) sed? (printf can also occur at the beginning of a line.)

	(i)	`grep (^printf|[^f]printf) foo`

	(ii) `sed -n '/(^printf|[^f]printf)/p' foo`

##

12.	Locate all nonblank lines that don't begin with #, /* or //?

	`grep -v ^(#|/*|//|^$)`

##

13.	Locate lines longer than 100 and smaller than 150 characters using (i) grep, (ii) sed.

	(i) `grep {100,150}`

	(ii) `sed `

##

14.	Find out the occurrences of three consecutive and identical word characters (like aaa or bbb) using (i) grep, (ii) sed.

	(i) `grep .{3}`

	(ii) `sed`

##

15.	Devise a sequence to locate those users who have logged in yesterday or earlier but have not logged out, and mail the list to root. Users logged in more than once should feature only once in the list.

	Get a who listing along with login time and filter to find the unique members and pipe the result to mail command such that the email goes to the root user.

##

16.	```grep -c ENCRYPTION foo``` outputsthe number of lines containing ENCRYPTION, but if the pattern sometimes occurs more than once in a line, how do you then obtain a count of all these occurrences? (HINT: Use sed also.)

	Need to better understand the working of sed to crack this problem.

##

17.	Frame a command sequence that looks at romeo's mailbox to tell him that either he has received a message from henry or the Subject: line contains the word urgent or immediate in lower- or uppercase.

	The command line should take into consideration the location of mail files and write a pattern match search to look for the desired patterns.

##

18.	Using sed, how do you add the tags <HTML> at the beginning and >/HTML> at the end of a file?

	Need to look into how to accomplish this.

##

19.	How do you delete all leading and trailing spaces in all lines of a file?

	Need to write a sed script to accomplish this

##

20.	How do you locate lines beginning and ending with a dot using (i) grep, (ii) sed

	(i) For grep, use a regular expression.

	(ii) For sed, use a regular expression too I guess.

##

21.	Explain what these commands do and if there's anything wrong with them:

	(i) sed -e 's/print/printf/g'  -e 's/printf/print/g' foo
	
	(ii) sed -e 's/compute/calculate/g' -e 's/computer/host/g' foo

	substitute globally, -e enables us to use multiple expressions, foo is the name of the file.

	The first expression of the first command line changes all the occurrences of print to printf. It also touches embedded strings. All the occurrences of `print` are converted to `printf` and then all the occurrences of `printf` are converted back to `print`. Thereby the file remains unchanged.

	In the second expression, all the occurences of compute will be replaced with calculate. Also, the occurrences of computer would be affected. So the second expression would not get to act at all and is therfore unnecessary.

##

22.	Every <B> tag in an HTML file has a closing </B> tag as well. Convert them to <STRONG> and </STRONG>, respectively, using sed with a single s command.

	Need to frame a sed substitute command.

##

23.	Specify the command sequence needed to remove the directory /usr/local/bin from the PATH defined in $HOME/.profile.

	This would require a sed expression while acts on the file $HOME/.profile.

##
