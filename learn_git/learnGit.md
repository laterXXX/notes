# Configuration before first use of git

  <table><tr><td bgcolor=#735322> 
## Basic

#### Enter the following command in command mode

* git config --global user.name "username"
* git config --global user.email "email"

#### Get information about user

* git config --list

#### what did the git record

* git records every file change

<img src="/home/later/Pictures/image-20191125135257005.png" alt="image-20191125135257005" style="zoom:50%;" />

* Git backs up all files in each version

#### How does git work?

* Git relies on three trees to work
* Tree is one of the data structures in algorithm

<img src="/home/later/Pictures/image-20191125140545271.png" alt="image-20191125140545271" style="zoom:67%;" />

#### Git's workflow consists of three parts

* add or delete files in your working directory
* put files that need to  be managed by git into the staging area
* submit files from the staging area to the repository

####  <font color=#455599 size=6 face="黑体">When managed by git, the file has three states</font> 

* modified
* staged
* committed

#### Let's get started

* mkdir empty_folder, then git init
* touch a readme file -->git add file --> git commit
* After creating the file, you need to add the file to git. Let git manage files
* git commit -m "what has changed in this version"
* check file status with git status
* if you don't add a file to git, git will not  manage the file, which means untracked files
* However, if you want to undo git add, you need to use the command git reset HEAD <file>. Note: This command places the file in the Stage area to the workspace. If you have already committed the file, this command will do nothing.
* Every time you use the git commit command, git builds a version for you.



#### Some cases

##### case 1: add file  no commit --> edit file execute git status

* When you edit a file in the workspace, the file also requires git add, but it is also in the Stage area because you haven't committed the file since the last time you added it. If you execute git checkout -- <file>, files in the Stage area will overwrite files in the workspace, which means discard changes in workspace. If you execute git add, files in the workspace will overwrite files in the Stage area, which means updating  changes in the workspace.

  

#### Git command summary so far:

- git add <file>
- git status
- git commit -m "description"
- git reset HEAD <file>
- git checkout -- <file>
- git log

#### reset and checkout

<img src="/home/later/Pictures/image-20191126103156320.png" alt="image-20191126103156320" style="zoom:50%;" />

- I did some experiments and I found that before committing the file, reset will undo git add and checkout will overwrite the workspace file.
- reset also will find the changes from repository to stage area, so reset file --> checkout -- file, the file in the repository will overwrite file in the workspace.

##### Change HEAD 

* Initial status

  <img src="/home/later/Pictures/image-20191126105015347.png" alt="image-20191126105015347" style="zoom:50%;" />

* Execute command git reset HEAD~.  This command change HEAD pointer to the pervious version.

  <img src="/home/later/Pictures/image-20191126110133426.png" alt="image-20191126110133426" style="zoom:50%;" />

* reset's options

  <img src="/home/later/Pictures/image-20191126115320881.png" alt="image-20191126115320881" style="zoom:40%;" />

* execute git reset --hard HEAD~. This command can be replaced with --mixed and checkout

<img src="/home/later/Pictures/image-20191126120229329.png" alt="image-20191126120229329" style="zoom:33%;" />



#### Compare Staging area and workspace

- git diff

  ![image-20191126151323616](/home/later/Pictures/image-20191126151323616.png)

- If you edit a file in the workspace without performing git add, you can get the difference between this file in the staging area and the workspace.

- `-` means old staging status. + means new workspace status.  -1,2 means old file has two lines.

  +1,3 means new file has three lines

  

#### Compare  repository and workspace or two historical versions

* git diff id _1 id_2

* git diff HEAD

* git diff id

  

#### Compare staging area and repository

- git diff --cached id



#### Git diff Summary

- <img src="/home/later/Pictures/image-20191126162427644.png" alt="image-20191126162427644" style="zoom:50%;" />

#### Edit last commit

- git commit --amend.
- <img src="/home/later/.config/Typora/typora-user-images/image-20191126203149175.png" alt="image-20191126203149175" style="zoom:33%;" />

#### Recover accidentally deleted file

- git checkout -- <file>

#### Delete a file seriously

- git rm file_name
- if the files in the workspace are different from the staging area, use git rm --cached file_name

#### Rename file

- note: If the file is under git management, use git mv 

## Git branch

