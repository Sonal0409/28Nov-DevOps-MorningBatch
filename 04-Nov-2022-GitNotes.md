Install git:

$ sudo su -

yum install git -y

git --version


Scenario 1:


Create a working a working directory

$ sudo su -

$ mkdir myproject

$ ls

go inside the folder

$ cd myproject

Create a new file in the directory

$ touch index1.html

Scenario 2:

Create the local repo
***********************
$ git init

$ ls -al ==> . git folder is available

Scenario 3:
**************
git configuration to set up a username and email address

3 types:
 system : configuration of git done for entire system
 global : configuration of git done for that particular user you are logged into the server(root)
 local : configuration of git done for that particular folder (myproject)

$ git config --global user.name sonal0409

$ git config --global user.email mittal.sonal04@gmail.com

Interview questions:

1. List all the config done by you on your git repo

 $ git config --list

Where is this config saved- in which file

 --global config will be save : ~/.gitconfig

 $ cat ~/.gitconfig


Scenario 4:
*******************

Add the file from working directory to stagging area

 $ git status

 $ git add index1.html

 $ git status

 $ git commit -m "added file"

 $ git ls-files  ==> see if file is in local repo or not
 
 
Scenario 6: git log

$ git log
$ git log --oneline

$ git show <commitid>

$ git show 8020b67

Assignment: Interview Question:

Save the commit history in a txt file

$ git log >> /pathoffile/filename.txt


**********
Scenario 6: Modify an exisitng file, which is already in Local repo

add the modification to LR

$ nano index1.html

add some lines

ctl X ==> y ==> press enter

OR

$ vim index1.html

add some lines

press esc ==> :wq! 


Chnages==> file1 file2 index1 index2


1 method:

$ git add index1.html
$ git commit -m "modification"


add all the modification to LR

2nd method:(using -a option: add all the changes & commit it)

$ git commit -a -m "modification index2.html"


************

Scenario 7: to check difference between 2 version of a file

$ git diff filename

$ git diff commit1 commit2


********************************************************
Scenario6: Deletion of file

- Deletion of file from WD & local repo

# git rm file1
# git status
# git commit -m "deletion of file1"
# ls
# git ls-files

- Deletion of file local repo only

# git rm --cached file2
# git commit -m "deteled file from local"
# git status    // file will be untracked
# ls
# git ls-files

# add the untracked file to local repo


*****************************************

If chnages are in stagging area and you have to work on them again--you need to rewrite the code

We need to unstage the changes, so as to write code again

$ git reset HEAD filename

OR

$ git restore --staged <file>

all chnages form stagging area==> move back to working directory(unstagged)

***************************************
 to discard changes in working directory
if changes of an existing file(tracked by git)  are to be removed
ie: remove the modifications from working directory using a git command

$ git checkout -- index2.html

OR 

$ git restore <file>.


permanently delete the changes

******************************************

***********************************************************


Scenario7: Ignoring Files

# vim log
# git status  // file untracked
# vim .gitignore   // add name of file "log" , which wil be noe ignored
# git status   // log will be ignored and .gitignore untracked
# git add .gitignore
# git commit -m "added ignore file"
# git status // working tress has to be clean

***********************************************************

Scenario 8: Reverting the changes:

# vim file3  // create a new files
# git add file3
# git commit -m "added file3"

//Delete the file

# git rm file3
# git commit -m "deleted file3"
# ls
# git ls-files

# git log --oneline    // last commit id is of delete action, copy it
// lets revert the commit

# git revert commit id

// file back to WD and local
# ls
# git ls-files


*******************************************************************


