# Lecture Note on Shell Commands
*Using the markdown, I will Organize and review the shell command I learned in the 5th week of the Open-Source SW lecture.*

#
----
#
\*By default\*
**standard output** : screen
**standard input** : from keyboard

#### <output>
- using **">"** : can redirect output after a command (e.g., ls) to create and save the output in a file.
- Command **"cat"** : displays the content of a text file.
- Using **">>"** : appends output to an existing file (if it already exists), or create and write to a new file if it doesn't exist.

#### <input>
- using **"<"** : can redirect input from a file.
- **Pipeline** : feeds output of previous command to input of next command.

*\* You can mix "<" and ">" together in a single line.*
#
---
#
#### <Expansion>
Special characters expand its meaning when given to shell commands.
```
$ echo print out the text
print out the text
$

$ echo *
README.md classification_experiment.py file_list.txt hello_world sorted_words.txt test.sh words.txt
$

$ echo ~
/home/User
$ echo ~User
/home/User
$
```
#
#### <Tip : Backslash>
Backslash can be used to ignore line change in command ("enter"), to enter a long command in multiple lines.
![lab](https://github.com/yeoxxy/learning-github/blob/main/lab5.png?raw=true)

#### <Permissions>
Linux is a multi-user system.
Files and directories have a permission assigned differently to owner / group / others.

#### <Changing Permissions>
- "chmod" changes permissions.
```
[me@linuxbox me]$ chmod 600 some_file
```
- 6 = 110 = rw- for owner
0 = 000 = ---  for group
0 = 000 = ---  for others

| Value | Meaning |
| --- | --- |
| **777** | (rwxrwxrwx) No restrictions on permissions. Anybody may do anything. Generally not a desirable setting. |
| **755** | (rwxr-xr-x) The file's owner may read, write, and execute the file. All others may read and execute the file. This setting is common for programs that are used by all users. |
| **700** | (rwx------) The file's owner may read, write, and execute the file. Nobody else has any rights. This setting is useful for programs that only the owner may use and must be kept private from others. |
| **666** | (rw-rw-rw-) All users may read and write the file. |
| **644** | (rw-r--r--) The owner may read and write a file, while all others may only read the file. A common setting for data files that everybody may read, but only the owner may change. |
| **600** | (rw-------) The owner may read and write a file. All others have no rights. A common setting for data files that the owner wants to keep private. |

\* Change the permission of a file "word.txt" that only the owner(you) can read and write, but all the others (including others in the group) can only read it. No execution is needed for all users.
#
---
#
#### <Superuser>
- A superuser has all system administation authority.
- Some commands need superuser's privilleges.
- Put "sudo" before the command if you are a superuser.
```
[me@linuxbox me]$ sudo some_command
Password for me:
[me@linuxbox me]$

[me@linuxbox me]$ sudo -i
Password for me:
root@linuxbox:~#
```
- Type "exit" to get out of a superuser session.
#
---
#
#### <Text Editors>
- In Linux, you can choose CLI-based or GUI-based text editors.

| Name | Description | Interface |
| --- | --- | --- |
| **vi, vim** | The granddaddy of Unix text editors, **vi**, is infamous for its obtuse user interface. On the bright side, **vi** is powerful, lightweight, and fast. Learning **vi** is a Unix rite of passage, since it is universally available on Unix-like systems. On most Linux distributions, an enhanced version of **vi** called **vim** is provided in place of vi. **vim** is a remarkable editor and well worth taking the time to learn it. | command line |
| **Emacs** | The true giant in the world of text editors is Emacs originally wirtten by *Richard Stallman*. Emacs contains (or can be made to contain) every feature ever conceived of for a text editor. It should be noted that **vi** and Emacs fans fight bitter religious wars over which is better. | command line |
| **nano** | **nano** is a free clone of the text editor supplied with the **pine** email program. **nano** is very easy to use but is very short on features compared to **vim** and **emacs**. **nano** is recommended for first-time users who need a command line editor. | command line |
| **gedit** | **gedit** is the editor supplied with the GNOME desktop environment. gedit is easy to use and contains enough features to be a good beginners-level editor. | graphical |
| **kwrite** | **kwrite** is the "advanced editor" supplied with KDE. It has syntax highlighting, a helpful feature for programmers and script writers. | graphical |
#
---
#
#### <Tip: History>
- Type "history" to see previous command history.
- Or, save it to a text file.
```
$ history > history_command.txt
$ cat history
```

