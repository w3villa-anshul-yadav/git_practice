$ mkdir git_commands_practice

# this command will create a directory named as 'git_commands_practice'

$ cd git_commands_practice/

# with this command we will change directory to 'git_commands_practice/'

# now we are in our 'git_commands_practice/' folder ,we will meake this folder to be tracked using git

$ git init /'
output => hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: git branch -m <name>

Initialized empty Git repository in /home/anshul/Desktop/git_commands_practice/.git/

$ git add README.MD

$ touch index.html

# added a new file index.html

$ nano index.html

# with this we will write some text in that file

$ git status
output =>
On branch master

No commits yet

Untracked files:
(use "git add <file>..." to include in what will be committed)
index.html
readme.md

nothing added to commit but untracked files present (use "git add" to track)

# this message is showing that there are some files which are not tracked

$ git add .

# with this all files which are not tracked will be added to staging area

$ git status

output =>
On branch master

No commits yet

Changes to be committed:
(use "git rm --cached <file>..." to unstage)
new file: index.html
new file: readme.md

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md

# or we can stage a individual file

using

$ git add readme.md

# now if we have done our work we can commit these changes

$ git commit -m "initial commit"
output =>

[master (root-commit) d294ce9] initial commit
2 files changed, 71 insertions(+)
create mode 100644 index.html
create mode 100644 readme.md

# now we will have to add remote url in this local git repo

$ git remote add origin git@github.com:w3villa-anshul-yadav/git_practice.git

# we can chek this using
$ git remote -v
output =>

origin git@github.com:w3villa-anshul-yadav/git_practice.git (fetch)
origin git@github.com:w3villa-anshul-yadav/git_practice.git (push)

# we have added file to staging area but if we weant to un stage that file then we have to use this command

# current status is

$ git status
output => On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
modified: readme.md

now we will un stage this file
$ git restore --staged readme.md

if we check status
$ git status
output =>
On branch master
Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md

no changes added to commit (use "git add" and/or "git commit -a")

$ git status
output=>
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
modified: readme.md

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md

# we can see that there are some modification in file
# if we want to undo these changes untill previous staging area we can do so by

$ git restore readme.md

# now if we check status

$ git status
output =>
On branch master
Changes to be committed:
(use "git restore --staged <file>..." to unstage)
modified: readme.md

# we can check history of all commits and details of commits by
$ git log
output=>

commit a528dbe13678e0c3aaa0b745d64749192e2de163 (HEAD -> master, origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 17:11:24 2023 +0530

    added readme file and edited

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit

# Now we have to push this code to remote repository

$ git push origin master

output =>
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 1.84 KiB | 314.00 KiB/s, done.
Total 7 (delta 1), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (1/1), done.
To github.com:w3villa-anshul-yadav/git_practice.git

- [new branch] master -> master

# now our commit log is as follows

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

# if we want to remove this commit we can do this

$ git reset d294ce98bcf

output=>
Unstaged changes after reset:
M readme.md

# now again if we check the status we can see that the file is showing modified and that commit is removed

$ git status
On branch master
Your branch is behind 'origin/master' by 2 commits, and can be fast-forwarded.
(use "git pull" to update your local branch)

Changes not staged for commit:
(use "git add <file>..." to update what will be committed)
(use "git restore <file>..." to discard changes in working directory)
modified: readme.md

# no changes added to commit (use "git add" and/or "git commit -a")

$ git log
commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3 (HEAD -> master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date: Sat May 13 16:57:20 2023 +0530

    initial commit


# by defalut this git reset is git reset --mixed
# which removes the commit and keep your work in staging area head and master points to specified commit 

# git reset --hard
$ git reset --hard ddcd354
output => HEAD is now at ddcd354 updated


$ git status
    On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean


$ git log
commit ddcd3547661ae5e395a0de0bcfbf63d9f96e95dc (HEAD -> master, origin/master)
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date:   Sat May 13 17:48:53 2023 +0530

    updated

commit d294ce98bcff3d1b01b4a426ad6f39e114d2f4d3
Author: Anshul Yadav <anshul.yadav@w3villa.com>
Date:   Sat May 13 16:57:20 2023 +0530

    initial commit


# by using git reset --hard 
# all changes in codebase and staging area are removed and head and master branch is pointing to commit ddcd354

sjdhsjd