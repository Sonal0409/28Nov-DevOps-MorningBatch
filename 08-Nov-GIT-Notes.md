Branching is a concept in git which allows to you freely work on multiple features at he same time without impacting the main master branch

Whenever we do commits on our repository we have seen a branch named master which gets updated.

Master branch is the default branch which get created upon initializing a repo

You can create any number of branched, a branch is copy of master branch

You can switch to a branch and work/develop on it. Once development or changes are complete on a branch , you can merge it to master branch

You can also rename and delete a branch.

But you cannot delete the master branch.

Scenario 1: Create branches in Local repo

Command to check how many branches are in Local repo

… git branch … Create a new branch in our Local repository … git branch f1 …

Switch to a particular branch … git checkout f1 …

Add new file and commit on the branch f1 $ touch feature1 $ git add . $ git commit -m “added onf1”

$ git log –oneline // check the new commit Switch back to master branch and compare the 2 branches

… git checkout master … Assignment

Compare the 2 branches: …

git diff --name-status master..f1

… OR

git diff master..f1

Scenario 2:

Command to create a new branch as well as switch to new branch … git checkout -b f2 …

Add new file and commit on the new branch

Switch back to master

Scenario 3: Merge the changes from feature branch to master

Always switch to the branch where you want to merge the files from feature branch … git checkout master …

Merge the changes from new branch to master branch … git merge …

… git merge f1 master … Check the commit history on master

Scenario 4:

Change the name of the branch … git branch -M f1 dev …

Delete a branch in local:

Make sure , you are not on the branch that is to be deleted

First checkout to master branch … git checkout master …

… git branch -D f2 …

List of branches that have not been merged to master

git branch --no-merged

List of branches that have been merged to master

git branch --merged

Cherry-pick scenario:

... git branch ... git checkout f2 ... ls ... touch login ... git add . ... git commit -m "f2 login" ... touch sonal ... git add .

... git commit -m "f2 sonal" ...

git log --oneline ... git checkout master ... git cherry-pick 66922bf f86a4c9 ... ls
