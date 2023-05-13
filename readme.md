$ mkdir git_commands_practice 
# this command will create a directory named as 'git_commands_practice'

$ cd git_commands_practice/
# with this command we will change directory to 'git_commands_practice/'

# now we are in our 'git_commands_practice/' folder ,we will meake this folder to be tracked using git

$ git init
# output =>  hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint: 
hint: 	git config --global init.defaultBranch <name>
hint: 
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint: 
hint: 	git branch -m <name>

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
	new file:   index.html
	new file:   readme.md

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   readme.md

or we can stage a individual file

using

