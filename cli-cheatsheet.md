## CLI Cheatsheet

#### [touch Command](https://www.geeksforgeeks.org/touch-command-in-linux-with-examples/)

Touch command is use to create files with **empty** content.
```
touch [option] [filename]
```

```
touch filename 
```

Touch can create multiple files at same time
```
touch filename1 filename2
``` 

Touch command can also check if file exist and whether or not to create file.
```
touch -c filename
```

#### [cat Command](https://www.geeksforgeeks.org/cat-command-in-linux-with-examples/)
Cat commands read data from file and gives it content as output on terminal.

```
cat [filename]
```

To view multiple files at same time

```
cat filename1 filename2
```

To view line number along side the content
```
cat -n filename
```

Copy content of one file to another

```
cat filename > destination
```

Append the content of one file to another

```
cat file1 >> file2
```

To merge content of multiple files
```
cat file1 file2 file2 > merged_file
```

#### [less command](https://www.geeksforgeeks.org/less-command-linux-examples/)
less command is used to read the content of files one page at a time. The less command doesn’t load the entire file, but loads it part by part which makes it faster.
less command also allow user to scroll up and down through page.

```
less [option] [filename]
```


To start at certain pattern in file 

```
less -p pattern filename
```

To print line number with content

```
less -n filename
```

#### [more](https://www.geeksforgeeks.org/more-command-in-linux-with-examples/)

more command is used to view the text files in the command prompt, displaying one screen at a time.

```
more [option] [filename]
```

Clear the screen and then display text

```
more -p filename
```

We use more command after a pipe to see long outputs. For example, seeing log files, etc.

```
cat filename | more
```

#### [tail](https://www.geeksforgeeks.org/tail-command-linux-examples/)

tail commands print the last N number of data in the given file.

```
tail [option] [filename]
```

tail command options</br>
![tail options](https://media.geeksforgeeks.org/wp-content/uploads/tail.png)


#### [rsync](https://linuxize.com/post/how-to-use-rsync-for-local-and-remote-data-transfer-and-synchronization/)

Rsync (Remote Sync) is the most commonly used command for copying and synchronizing files and directories remotely as well as locally.

```
rsync options source destination
```

Using rsync to copy files recursively and watch the progress: 
```
rsync -avP <source> <destination>
```

Some common options used with rsync commands

- -v : verbose
- -r : copies data recursively (but don’t preserve timestamps and permission while transferring data.
- -a : archive mode, which allows copying files recursively and it also preserves symbolic links, file permissions, user & group ownerships, and timestamps.
- -z : compress file data.
- -h : human-readable, output numbers in a human-readable format.
- -P : shows progress bar during the transfer and keeps the partially transferred files. It is useful when transferring large files over slow or unstable network connections.


#### [grep](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)
grep filter searches a file for a particular pattern of characters, and displays all lines that contain that pattern.

```
grep [options] pattern [files]
```

```
Options Description
-c : This prints only a count of the lines that match a pattern
-h : Display the matched lines, but do not display the filenames.
-i : Ignores, case for matching
-l : Displays list of a filenames only.
-n : Display the matched lines and their line numbers.
-v : This prints out all the lines that do not matches the pattern
-e exp : Specifies expression with this option. Can use multiple times.
-f file : Takes patterns from file, one per line.
-E : Treats pattern as an extended regular expression (ERE)
-w : Match whole word
-o : Print only the matched parts of a matching line,
 with each such part on a separate output line.

```

Examples

* count and ignore case matching
```
grep -c -i pattern filename
```

* find in which file does my patter exist
```
grep -l -i pattern *
```
_* stands for everyfile in that directory_ 

* Check for whole word as pattern not substring

```
grep -w -i "pattern" filename
```

* We want to display only matched patterns in the file.
```
grep -o -i "pattern" filename.txt
```


#### [find](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)

find command is use to search for file or folder and perform some operation on them.

```
find foldername -name filename.extension operation
```

Example
We want to delete all the log files in our current directory.

```
find . -name *.log -delete
```


find empty file  
```
find . -empty
```

find with permission
```
find . -perm 774
```

_here . stands for current folder or directory_

#### [sort](https://www.geeksforgeeks.org/sort-command-linuxunix-examples/)

SORT command is used to sort a file, arranging the records in a particular order.

sort the content inside the file.
```
sort filename
```

reverse sort or descending order sort
``` 
sort -r filename
```

save sorted file?
```
sort -o temp.txt states.txt 
```

sort by number
```
sort -n number.txt
```

sort and remove redundant values.
```
sort -u number.txt
```

check if file is sorted?
```
sort -c number.txt
```


#### [date](https://www.geeksforgeeks.org/date-command-linux-examples/)

date command is used to display the system date and time. date command is also used to set date and time of the system.

```
date [OPTION] [+FORMAT]
```

Display current time.
```
date
```

Display time in GMT

```
date -u
```

Displays the given date string in the format of date.

```
date --date="string"
```

```
date --date="2 years ago"
```

```
date --date="01/01/1998"
```

If we want to display date which are inside a file we use --file option.

```
date --file=filename
```

#### [tree](https://www.geeksforgeeks.org/tree-command-unixlinux/)

tree command is use to list the directories and files inside those directories in tree format

To get started with tree we need to install it.

```
sudo apt-get install tree

or

brew install tree
```

Display tree hierarchy of a directory.

```
tree -a directory
```

Find the files with certain pattern.
for eg we want to find files with txt extension

```
tree -P *.txt directory
```

List files with their permissions.

```
tree -p foldername
```

Show full path of the files.

```
tree -f foldername
```

Show only directory
```
tree -d foldername
```