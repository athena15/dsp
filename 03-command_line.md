# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

Print working directory: **pwd**

Create a directory: **mkdir** target_directory

Delete a directory: **rm -r** target_directory

Create a file: **touch** newfile.txt

Delete a file: **rm** targetfile.txt

List hidden files: **ls -a**

Copy a file from one directory to another: **cp** target_file.txt \target_dir

Copy *all* files from one directory to another: **cp *** /target_dir

Delete *all* files from a directory: **rm -r** /target_dir

Rename a file: **mv** oldname.txt newname.txt

Print contents of a file to terminal: **cat** target_file.txt

Print contents of a file to a different file: **cat** source_file.txt **>** target_file.txt

Append contents of a file to a different file [retains original file data]: **cat** source_file.txt **>>** target_file.txt

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  : List all files and directories (in cwd)
`ls -a`  : List all files and directories, *including hidden*
`ls -l`  : List all files and directories, *in long format*
`ls -lh`  : List all files and directories, *in long format,* **with readable file sizes**
`ls -lah`  : Lists all files and directories, *in long format (l), showing hidden files (a), with more readable file sizes (h)*
`ls -t`  : Lists all files and directories, *sorted by last modified*
`ls -Glp`  Lists all files and directories, *adding colors for files & directories (G), in long format (l), *including  trailing '/' for directories*

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -m` : Show all in comma separated notation

`ls -F` : Flags filenames

`ls -G` : Adds colors for filenames and directories

`ls -d` : Displays only directories

`ls -p | grep -v /` : Displays only files (not directories)

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` allows you to run Unix operations on multiple files. For example, you can use it to make new directories:

`dir1 dir2 dir3 | xargs mkdir`

