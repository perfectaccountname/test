# test

		TERMINAL USE everything is a FILE(each file have a FD)
						(file discriptor)
/*--------------------------------------*/
Some basic navigation 
/*--------------------------------------*/

pwd	current dir
cd .. 	up 1 level
cd / 	root
cd ~	home
cd ./<dir>or<file>	exec
cd <dir>	dir in this level
ls -R 	show dir under level
ls -a 	show .<file>	hidden
ls -l	information
ls -la 	detail
ls "options" <dir>
cat > <filename>	newfile ctrl+d to end
cat <file1> <file2> > <file3>	concat 2 file to 1
cat <filename>	show content
rm <file>
mv <file> <newpath>
mv <file> <newfilename>
mkdir <dirname>or<path/dirname>
rmdir <dir>
man <commandName>	manual
history
ctrl+alt+T	terminal
ctrl+C	cop
ctrl+shift+V paste in term
shift+Insert paste in term
clear

/*--------------------------------------*/


/*--------------------------------------*/
Ownership and Permission concept (multi user system)
/*--------------------------------------*/

Owner: user create file, user-group(same access permission), other 
Permission: rwx- Read Write Execute No permission
dr-x: directory read nowrite execute
-'rw-'rw-'r-- file;user;usergroup;other

chmod xxx <fileordir>	change mode 0-7 3bit rwx					absolute
chmod o=rwx <fileordir>		o:other-u(user)-g(group)-a(all)	=:+'-' permission	symbolic

chown <user> <fileordir>	change ownership
chown <user>:<group user> <fileordir>
chgrp <group user> <fileordir>	
groups		find groups that user is a member of
newgrp	<newgroup>

2 groups cannot own same file
/etc/group			present groups on system

/*--------------------------------------*/

/*--------------------------------------*/
Printing,Email and Install software
/*--------------------------------------*/

pr <option> <filename>	format file
lp <filename>
lpr <filename>
lp -nN <filename> N number of print
lpr N <filename>
lp -d<printername> <file>
lpr -P<printername> <file>

sudo apt-get install <soft>	soft include a packet of soft itself and dependent component packet need down separately.	

sudo apt-get install mailx

mailx anme@gmail.com
Subject:
 
body

ctrl + d: end and send

/*--------------------------------------*/

/*--------------------------------------*/
Re-direction in linux
/*--------------------------------------*/

>	:output direction	stdout

ls -al > listfile.docs			ls command result will write in listfile.docs
echo testtexthere > listfile.docs	this will overwrite old data so use >> it will not overwrite it
echo notoverwrite old text >> listfile.docs	

<	:input direction	stdin
ex: mail -s "news" abc@gmail.com < newsfile.docs

FILE Discriptor:
FD0 standard input
FD1 standard output
FD2 standard error	, run shell script if error heppend and dont redirect it to
			  a file it will clutter the output of file so have to redirect
			  error messages to another file
ex: telnet localhost 2> errorMSGfile.docs
cat errorMSGfile.docs   can see what kind of errors heppend

find . -name 'my*' 2> errorfile.log

ls Documents ABC> dirlist 2>&1		both standard output and error output return to
					dirlist file
>& re-directs output of one file to another

/*--------------------------------------*/


/*--------------------------------------*/
Pipes    Grep      Sort Command
/*--------------------------------------*/

'|' denotes a pipe. use Pipes to run two commands consecutively

cat fruits.docs | less   		scroll file up down q to quit
		| pg     | more

grep <options> <search_string>    scan a document, present the result in a format
-v show all line not match string -c displays only count -n -i - 

cat fruits.docs | grep Melon	


sort <options> <filename>	-r -n -f 
sort fruits.docs


filters output of 1st command become input of 2nd command

command1 | command2

cat fruits.doc | grep -v a | sort -r		<=== pipes

/*--------------------------------------*/

/*--------------------------------------*/
Regular expressions	regexp	regex
/*--------------------------------------*/
special character
Basic regular expressions: tr sed vi grep

.	replaces any character
^	matches start of string
$	end
*	matches up zero or more than preceding char
\	represent special char
()	groups regular expressions
?	matches up exactly one char

cat sample.txt | grep ^a	: line start with "a"
cat sample.txt | grep t$

cat sample.txt | grep -E p\{2}

Extended regexp
\+
\?

cat sample.txt | grep "a\+t"	

Interval regexp
{aa,bb,cc}	string = aa bb cc
{a..z}
{1..11}
a{0..9}b

regular exp are set of char use to check pattern in strings


/*--------------------------------------*/	

/*--------------------------------------*/
Environment Variables
/*--------------------------------------*/



/*--------------------------------------*/

/*--------------------------------------*/
Ping, FTP, SSH
/*--------------------------------------*/



/*--------------------------------------*/
