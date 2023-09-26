# Lecture Note on Shell Commands
*Using the markdown, I will Organize and review the shell command I learned in the 4th week of the Open-Source SW lecture.*
<br>

### 
- **pwd** : Shows the current path in a hierarchical directory (indicates the current folder's absolute path)  
Shows the current path or directory (Linux-based systems mount in a specific directory in the root, no matter how many drives are at the top of the list)
- **cd** : Change directory (Move folders)
- **ls** : List files and directories (Check folders and files in the current folder)

---
### ls

| Command | Results |
| --- | --- |
| **l** | List the files in the working directory |
| **ls /bin** | List the files in the /bin directory (or any other directory we care to specify) |
| **ls -l** | List the files in the working directory in long format (Prints the file's permissions, owner, date created, capacity, etc.) |
| **ls -l /etc /bin** | List the files in the /bin directory and the /etc directory in long format |
| **ls -la ..** | List all files (even ones with names beginning with a period character, which are normally hidden) in the parent of the working directory in long format |

- options:
    - **-l** : Shows more detailed information than file names and extensions (long format)
    - **-lh** : Same as above, but size in units
    - *Differences from -l: If you give the -l option, a really large number will be taken for large files. The format that converts it into a more human-readable form such as kb, mb, gb, etc. that we are more familiar with is -lh*

---

- **clear** : Empty the terminal (***Warning!*** *these commands may delete or overwrite your files and directories!*)
```
$ ls
neuralintlab transformers
$ cd neuralintlab/
$ ls
README.md
$ clear
```

---
### cp

| Command | Results |
| --- | --- |
| **cp** | Copy files and directories |
| **cp *file1* *file2*** | Copies the contents of *file1* into *file2*. If *file2* does not exist, it is created; **otherwise, *file2* is silently overwritten with the contents of *file1*.** |
| **cp -i *file1* *file2*** | Like above however, since the "-i" (interactive) option is specified, if *file2* exists, the user is prompted before it is overwritten with the contents of *file1*. |
| **cp *file1* *dir1*** | Copy the contents of file1 (into a file named *file1*) inside of directory *dir1*. |
| **cp -R *dir1* *dir2*** | Copy the contents of the directory *dir1*. If directory *dir2* does not exist, it is created. Otherwise, it creates a directory named *dir1* within directory *dir2*. |

---
### mv

| Command | Results |
| --- | --- |
| **mv** | Move files and directories or rename them |
| **mv *file1* *file2*** | If file2 does not exist, then file1 is renamed file2. **If *file2* exists, its contents are silently replaced with the contents of *file1.*** |
| **mv -i *file1* *file2*** | Like above however, since the "-i" (interactive) option is specified, if *file2* exists, the user is prompted before it is overwritten with the contents of *file1*. |
| **mv *file1* *file2* *dir1*** | The files *file1* ad *file2* are moved to directory *dir1*. If *dir1* does not exist, **mv** will exit with an error. |
| **mv *dir1* *dir2*** | If *dir2* does not exist, then *dir1* is renamed *dir2*. If *dir2* exists, the directory *dir1* is moved within directory *dir2*. |  

---
### rm
```
$ pwd
/c/Users/User
$ ls
README.md new_module.py
$ rm new_module.py
$ ls
README.md
```
| Command | Results |
| --- | --- |
| **rm** | delete files and directories ***permantely and irreversevely!!!*** |
| **rm *file1* *file2*** | Delete *file1* and *file2*. |
| **rm -i *file1* *file2*** | Like above however, since the "-i" (interactive) option is specified, the user is prompted before each file is deleted. |
| **rm -r *dir1* *dir2*** | Directories *dir1* and *dir2* are deleted along with all of their contents. |

---

- **mkdir** : make a new directory
```
$ ls
neuralintlab transformers
$ mkdir new_directory
$ ls
neuralintlab new_directory transformers
```

---
### Manipulation: Wildcards

| Pattern | Matches |
| --- | --- |
| **\*** | All filenames |
| **g\*** | All filenames that begin with the character "g" |
| **b\*.txt** | All filenames that begin with the character "b" and end with the characters ".txt" |
| **Data???** | Any filename that begins with the character "Data" followed by exactly 3 more characters |

| Command | Results |
| --- | --- |
| **cp \*.txt text_files** | Copy all files in the current working directory with names ending with the characters ".txt" to an existing directory named *text_files*. |
| **mv dir1 ../*.bak dir2** | Move the subdirectory *dir1* and all the files ending in ".bak" in the current working directory's parent directory to an existing directory named *dir2.* |
<br>

| **rm \*~** | Delete all files in the current working directory that end with the character "~". Some applications create backup files using this naming scheme. Using this command will clean them out of a directory. |
