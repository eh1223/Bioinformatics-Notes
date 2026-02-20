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

# lab 4

### EXERCISE 1: NAVIGATION PRACTICE
Navigate to your untrimmed_fastq directory in one command
cd gen711-811/shell_data/untrimmed_fastq/
can access using ls *untrimmed_fastq

### EXERCISE 2: WILDCARDS
What would the output look like if the wildcard could *not* be matched? Compare the outputs

expect an error
ls: cannot access '*fq': No such file or directory

### EXERCISE 3: NAVIGATING PRACTICE
Navigate to your home directory. From there, list the contents of the untrimmed_fastq directory.

cd / cd $HOME / cd ~ = home directory
SRR907977.fastq
SRR098026.fastq
headliners.txt
### EXERCISE 4: FINDING HIDDEN DIRECTORIES
First navigate to the shell_data directory. There is a hidden directory within this directory. Explore the options for ls to find out how to see hidden directories. List the contents of the directory and identify the name of the text file in that directory.

Hint: hidden files and folders in Unix start with ., for example .my_hidden_directory

ls -a / ls --all = finding hidden directories
ls -Fa = all directories with a slash
ls -laF = shows domain, users, last edited or accessed

What is the hidden file name in the hidden directory?
youfoundit.txt

### EXERCISE 5: HISTORY
Find the line number in your history for the command that listed all the .sh files in /usr/bin. Rerun that command.

427  ls /usr/bin/*.sh
!# = rerun a specific code from history
/# = line number

### EXERCISE 6: FILE CONTENTS
Print out the contents of the ~/shell_data/untrimmed_fastq/SRR097977.fastq file. What is the last line of the file?
cat = prints whole file to screen

### EXERCISE 7: PATHS
From your home directory, and without changing directories, use one short command to print the contents of all of the files in the ~/shell_data/untrimmed_fastq directory.

### EXERCISE 8: LESS
What are the next three nucleotides (characters) after the first instance of the sequence quoted above?

CAC
less FILE NAME or less -S FILE NAME
use Shift+G to go to bottom and Q to exit
also use grep 'TTTTT' *fastq = 'TTTTT' can be replaced by anything within file (ex.nucleotide sequence)
head FASTQ to top
tail FASTQ to bottom
tail -n3 FASTQ gives last 3 lines

mkdir = make directory
cp = copy
cp SRR098026.fastq SRR098026-backup.fastq = copy fastq file
cp SRR098026.fastq /usr/SRR098026-backup.fastq = make copy from home directory
mv = move
mv *backup.fastq_backup/ = move everything that ends in backup.fastq to backup folder
mv *backup.fastq_backup backup = move fastq backup tp backup directory

-You can view file contents using `less`, `cat`, `head` or `tail`.
- The commands `cp`, `mv`, and `mkdir` are useful for manipulating existing files and creating new directories.
- You can view file permissions using `ls -l` and change permissions using `chmod`.
- The `history` command and the up arrow on your keyboard can be used to repeat recently used commands.

use clear to "erase" all data in terminal

echo = echoes everything back

# lab 5

- You can view file contents using `less`, `cat`, `head` or `tail`.
- The commands `cp`, `mv`, and `mkdir` are useful for manipulating existing files and creating new directories.

to read fastq files:
1. @SSR... is the first line that is succeeded by the sequence
@SRR097977.249 209DTAAXX_Lenski2_1_7:8:3:441:292 length=36
GGGTAGGTATTACTCAGGACGAGGCGGTCGTGCCAC

2. +SRR... is succeed by the quality score in charas, numbers, letters
+SRR097977.249 209DTAAXX_Lenski2_1_7:8:3:441:292 length=36
C:CCC::CCCCCCCC<8?6A:C28C<608'&&&,'$

3. tags and length should be identical
4. each quality score aligns to a base pair

chmod = change mode
removes privaleges to files
r = read 
w = write
x = execute
- = no permissions
chmod ug+rwx FILE NAME = allows read write execute to user and group
-rw-r--r--. 1 eh1223 domain users 47552 Feb 20 15:46 SRR097977.fastq_backup
to remove permissions: chmod -w FILE NAME

rm = remove
-R = recursive, goes inside folder
f = force, skips warning
rm -Rf backup/ = removes everything from and backup directory

exercise 1:
Make sure that you have deleted your backup directory and all files it contains.
rm -Rf backup/

Create a backup of each of your FASTQ files using cp
cp SRR097977.fastq SRR097977.fastq_backup
cp SRR098026.fastq SRR098026.fastq_backup

Use a wildcard to move all of your backup files to a new backup directory
mv *.fastq_backup backup

exercise 2:
Change the permissions on all of your backup files to be write-protected.
chmod -w SRR097977.fastq_backup
chmod -w SRR098026.fastq_backup

How do you know they are write protected?
A: w is replaced by -

everything so far has been bash/shell script
now moving onto conda

conda activate genomics = load genomics conda environment
conda deactivate = deactivates conda enviroment

fastqc -h = opens fastqc help menu, shows all available commands

fastqc *.fastq* = started analysis fastq files

which = shows where everything is installed

exercise 3:
where is the program 'fastqc' stored?
conda activate genomics
which fastqc

unzip = opens zip files
