# Git A version control system

# Terminal commands for file and folder management

```
ls
```

# It list all hidden file and folders current directory

```
ls -a
```

# It do work as above but also lists the hidden files and folders

```
ls dirName
```

# It is used to see content of directory , ‘dirName’ should be child directory of current folder or we can give path

```
mkdir folderName
```

# It is used to make directory (folder)

```
cd  dirName
```

# Change directory to dirName

```
cd ..
```

# Is used to go back to parent directory

```
touch fileName
```

# To create file name as fileName

```
rm -rf dirName
```

# It delete the folder as well as its inner folder and files

```
rmdir dirName
```

# It can only delete empty folder

```
cat fileName.extension
```

# It is used to see the contents of file it opens editor

# GIT Commands

```
git init
```

# Is used to start versioning in directory , form now this directory can access all features of git ,it initializes a directory as git local repository

```
git status
```

# Is used to check the status of local git repository; it gives current branch information and file status that which file is modified , not added in the staging area ,and which are to be committed .

```
git add fileName
```

# Is used to add file ‘fileName’ in staging area

```
git commit -m “give commit message”
```

# Is used to add a staged file to the commit area now this file will be added to that particular commit record.

```
git push url branchName
```

# Is used to push code to remote repository such as git hub,

# Url is the url of a remote repository .

```
git restore –staged fileName
```

# Bring back staged file to un staged area

```
git restore fileName
```

# Is used to discard  un staged changes it is like UNDO all changes which are not staged

```
git log
```

# Now we will see practical

# It give log (history) of all commits , branch hierarchy which branch is created from which branch and there associated commits

```
  mkdir git_commands_practice
```

# This command will create a directory named as 'git_commands_practice'

```
  cd git_commands_practice/
```

# With this command we will change directory to 'git_commands_practice/'

# Now we are in our 'git_commands_practice/' folder ,we will make this folder to be tracked using git

```
  git init
```

# Output ~

<pre>
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: git branch -m <name>

Initialized empty Git repository in /home/anshul/Desktop/git_commands_practice/.git
</pre>

```
  touch index.html
```

# Added a new file index.html

```
  nano index.html
```

# With this we will write some text in that file

```
  git status
```

# Output ~

<pre>
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
index.html
readme.md

nothing added to commit but untracked files present (use "git add" to track)
</pre>

# This message is showing that there are some files which are not tracked

```
  git add .
```

# With this all files which are not tracked will be added to staging area

```
  git status
```

# Output ~

<pre>
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to  un stage)
new file: index.html
new file: readme.md

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md
</pre>

# Or we can stage a individual file

# Using

```
  git add readme.md
```

# now if we have done our work we can commit these changes

```
  git commit -m "initial commit"
```

# Output ~

<pre>
[master (root-commit) d294ce9] initial commit
2 files changed, 71 insertions(+)
create mode 100644 index.html
create mode 100644 readme.md

</pre>

# Now we will have to add remote url in this local git repo

```
  git remote add origin git@github.com:w3villa-anshul-yadav/git_practice.git
```

# We can check this using

```
  git remote -v
```

# Output ~

<pre>
origin git@github.com:w3villa-anshul-yadav/git_practice.git (fetch)
origin git@github.com:w3villa-anshul-yadav/git_practice.git (push)
</pre>

# We have added file to staging area but if we weant to un stage that file then we have to use this command

# Current status is

```
  git status
```

# Output ~

<pre>
 On branch master
Changes to be committed:
(use "git restore --staged <file>..." to  un stage)
modified: readme.md
</pre>

# Now we will un stage this file

```
  git restore --staged readme.md
```

# If we check status

```
  git status
```

# Output ~

<pre>
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md
no changes added to commit (use "git add" and/or "git commit -a")
</pre>

```
  git status
```

# Output~

<pre>
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to  un stage)
modified: readme.md

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md
</pre>

# We can see that there are some modification in file

# If we want to undo these changes until previous staging area we can do so by

```
  git restore readme.md
```

# Now if we check status

```
  git status
```

# Output ~

<pre>
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to  un stage)
modified: readme.md
</pre>

# we can check history of all commits and details of commits by

```
  git log
```

# Output~

<pre>
commit a528dbe13678e0c3aaa0b745d64749192e2de163 (HEAD -> master, origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:11:24 2023 +0530

    added readme file and edited

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit
</pre>

# Now we have to push this code to remote repository

```
  git push origin master
```

# Output ~

<pre>
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 1.84 KiB | 314.00 KiB/s, done.
Total 7 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:w3villa-anshul-yadav/git_practice.git

- [new branch] master -> master
</pre>

# Now our commit log is as follows

<pre>
commit 64c44265e03f0ccfc890e88be00279805ed0cc1c (HEAD -> master, origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:14:34 2023 +0530

    some changes done

commit a528dbe13678e0c3aaa0b745d64749192e2de163
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:11:24 2023 +0530

    added readme file and edited

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit
</pre>

# If we want to remove this commit we can do this

```
  git reset d294ce98bcf
```

# Output~

<pre>
 un staged changes after reset:
M readme.md
</pre>

# Now again if we check the status we can see that the file is showing modified and that commit is removed

```
  git status
```

<pre>
On branch master
Your branch is behind 'origin/master' by 2 commits, and can be fast-forwarded.
(use "git pull" to update your local branch)

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md
No changes added to commit (use "git add" and/or "git commit -a")
</pre>

```
  git log
```

<pre>
commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3 (HEAD -> master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit
</pre>

# By default this git reset is git reset --mixed

# Which removes the commit and keep your work in us staged area head and master points to specified commit

# git reset --hard command

```
  git reset --hard ddcd354
```

# Output ~

<pre>
HEAD is now at ddcd354 updated
</pre>

```
  git status
```

<pre>
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
</pre>

```
  git log
```

<pre>
commit ddcd3547661ae5e395a0de0bcfbf63d9f96e95dc (HEAD -> master, origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:48:53 2023 +0530

    updated

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit
</pre>

# By using git reset --hard

# All changes in codebase and staging area are removed and head and master branch is pointing to commit ddcd354

```
  git reset --soft 0b2b7bf5
```

```
  git log
```

<pre>
commit 0b2b7bf51d22078022d7610d00c1e744f5d1a822 (HEAD -> master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:58:48 2023 +0530

    updated readme

commit ddcd3547661ae5e395a0de0bcfbf63d9f96e95dc (origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:48:53 2023 +0530

    updated

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit
</pre>

```
  git status
```

<pre>
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
(use "git push" to publish your local commits)

Changes to be committed:
(use "git restore --staged <file>..." to  un stage)
modified: readme.md
</pre>

# By using git reset --soft head and master are pointing to that specified commit and changes are in staging area

# If we want to push this code then we will get and error

```
  git push
```

<pre>
To github.com:w3villa-anshul-yadav/git_practice.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'github.com:w3villa-anshul-yadav/git_practice.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

</pre>

# We have to use a force flag after push command

```
  git push -f
```

<pre>
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 2.08 KiB | 710.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:w3villa-anshul-yadav/git_practice.git
 + 64c4426...ddcd354 master -> master (forced update)
</pre>
