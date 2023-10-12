# Week 6 Lecture Notes
*Using the markdown, I will Organize and review the shell command I learned in the 6th week of the Open-Source SW lecture.*


----

#### <Git config : First-time setup>
Git configurations are stored in three levels:
(1) System level : --system option. Affects all uses and repositories on the system (administrative)
file: /etc/gitconfig
(2) Global (user) level: --global option. Affects all repositories of a current user
file: ~/.config/git/config
(3) Local level: --local option. Specific to the current repository
file: .git/gitconfig

\* Each level overrides values in the previous level : system -> global -> local

\* **This image is the default setting using the git config command.**
![lab](https://raw.githubusercontent.com/yeoxxy/learning-github/46cb4150d28c7d6c7431d3d017623afd67978fcc/lab6.png)

#### <Initializing a Repository in an Existing Directory>
Enter the command 'git init' in the directory where we practiced until the last week.
```
$ git init
Initialized empty Git repository in C:/Users/User/.git/
$ ls -lha
#After the 'ls' command, 'option a' means to print out all hidden files and directories
```

#### <Checking Repository Status>
```
$ git status
#Command to see which of the three statuses (Working Directory  /Staging Area / .git directory (repository)) we studied prior
```

\* **Untracked files** : It means that currently exists in this directory but git is not tracking (out of git's interest). Git doesn't care if we excuse or even delete the names of these files.

---

#### <Adding a new file to be staged (tracked)>
\* When we want to upload a particular file to the 'staging area', enter the command 'git add' and write the file name

\* **$ git add [file_name]**
```
$ git add README.md
$ git status
On branch master

No commits yet

Changes to be commiteed:
(use "git rm --cached <file>..." to unstage)
new file : README.md
```
Once we put it up here (because these are the files we're going to commit to) Git cares if there's a change in these files (the rest of the files are still out of interest)

\* **$ git add .** : Command to upload all files and directories in the current directory to the 'staging area' together.

\* **$ git rm --cached [file_name]** : Command to unstaging again. Use if we are ready to stage, but have files that we want to modify or remove again. It's not actually disappearing, it's just that the file is removed from the 'staging area' of the git (we can check through the 'ls command' that it's still in the directory)

\* We moved it to the staging area using 'git add', and if we want to modify the file, if we edit it and save it as it is, if we enter git status, the file uploaded to the staging area will still be displayed. However, the file with the same name is still displayed in the 'staged for commit.'
**If we commit like this, the content before the revision will go up. In this case, we should avoid committing as it is, and if we modify a file, we should upload the modified file again to the 'staging area.'**


#### <Ignoring a file>
\* **$ nano .gitignore** : It's annoying to use 'git rm --cahced' every time to unstag a particular file, so we can choose only the files we want to ignore (creating a file named '.gitignore' in our current directory, not the command from git). At first, there's nothing in 'gitignore', but if we write the name of the file you want to ignore in that file, and we write "git add." and do the git status, we'll see it appear without that file (we can literally make that file completely ignored by git)
\* **.gitignore file** : If we use it well, we can make git ignore the files completely we want.

#### <Commit>
\* **$ git commit -m "commit message"** : "-m" is just an option, but almost all recommend putting this after the git commit (if we do not put it, committing becomes a bit cumbersome and difficult)
\* **$ git commit -m "initial commit"**
[master (root-commit) 4b0c4f3] initial commit <- Master branch is created and a commit message is displayed
```
$ git status
On branch master
nothing to commit, working tree clean #There is nothing left in the middle anymore because all the files are committed. Meaning that the content currently committed and the content currently in our working tree are exactly the same.
$
```
After this process, we did our first commit under the name 'initial commit', and we finally took the first snapshot(that is, version 1) of what we worked on.

\* **$ git log** : we can check what we have committed so far

---

#### <Change branch name>
```
$ git branch
#Commands to use when you want to check the branch content that is currently in this repository
* master
$ git branch -m master main
#When we want to change the name of the branch, write "-m" after "git branch" and "name of the branch we want to change"
$ git branch
* main
$ git status
On branch main
nothing to commit, working tree clean
$
```

