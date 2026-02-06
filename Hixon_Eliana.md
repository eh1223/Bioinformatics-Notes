# lab 3

how to find directories
1. pwd = print working directory

directories can contain files or folders

2. ls = list
ls ' = bumps to new line, waiting for other end of quote '
use ctrl+c to exit = used to cancel

3. cd shell_data
4. ls
ls -F = adds slashes st end of directories
man ls = manual, give operator manual for ls
q exits to command line
ls -lrth = directories and owners, creation date, permissions listed

5. cd untrimmed_fastq/
start with cd u then tab to autofill
in eh1223@ron untrimmed_fastq

6. ls
head S tab 7 or 8 tab.fastq
lists genome data in form of fastQ

to get out
1. cd ../
in eh1223@ron shell_data, one step out
../../ is two steps out
etc
cd ~ 
~ = shorthand for home directory
then cd DIRECTORY

rm = remove, equivalent to delete
anything not pushed to git will be deleted
$VARIABLE = takes to variable site
echo shows paths within VARIABLE

history = shows entire command history
bottom most recent, top oldest

grep = basically ctrlF, searches lines for specific things

^ = beginning of line
ex. grep '^@'
shows results with @ at beginning of line

head = shows first few lines of a file

ls *FILE
* = wildcard, anything works
only listed files after *

ws = word count
gives line #, word #, character #
ls /bin/LETTER* | wc -l
gives word count for files in /bin that start with LETTER
-l = lines

less = allows scrolling through files

What are 3 ways to change directories to your home directory from the  untrimmed_fastq directory?
1. cd ~
2. cd ../../../
3. cd $HOME
4. bonus = copy and paste

Do each of the following tasks from your current directory using a single ls command for each:
    - List all of the files in /bin that start with the letter ‘c’.
    - List all of the files in /bin that contain the letter ‘a’.
    - List all of the files in /bin that end with the letter ‘o’.

Start with the letter c ____ ls /bin/c* OR ls /bin/ | grep '^c'
Start with the letter a ____ ls /bin/a*
Start with the letter o ____ ls /bin/o*