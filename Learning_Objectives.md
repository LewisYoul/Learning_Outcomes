# Makers Academy - Learning Objectives

This document contains my thoughts on the learning objectives for the Makers Academy Precourse.

## Command Line

To be finished.

## Git and GitHub

GitHub is a version control system (VCS). It allows you to upload your code to a remote repository, which in turn allows you to work on your code from anywhere!

##### Common Commands:

* `git init` will initialize the remote repository within the directory you are working. You cannot work with git locally until this has been done.

* `git add <filename>` will add the specified filename to the staging area. If you would like to add all files in the directory to the staging area `-A` can be used instead of `<filename>`.

* `git status` will allow you to view the condition of the files in the staging area. It will let you know if there are new files present or if alterations have been made to existing files.

* `git commit -m "message"` Now that your file is in the staging area it is time to `commit` it to the *local repository.*

* `git log` will list the history al all previous commits. It gives you a history of all changes including when they were made and by whom. It will also show you the individual number associated with that commit. This can be used if you want to "go back in time" to a previous commit.

* `git rm <filename>` should be used if you want to remove a file from your repository. This will stage the change, but remember we still need to `commit` the change to the local repo.

* `git checkout <SHA>` should be used if we want to go back to an older version of our repository. The `<SHA>` is the unique code that can be found when we run `git log`. You will now be in an "alternate reality" where, if you run `ls` you will only see files from the old repo. To return to our current version we can run `git checkout master`.

* `git pull origin master` will pull any updates from the remote repo and add them to your local repo.

* `git clone <URL>` will clone the repository into the current directory you are in. It should be noted that cloning will also generate a directory for the repository so you do not need to do this yourself. The URL of the repository you want to clone can be found on the home page of that repo.

* `git fetch` will update your remotely tracked branches. It will not change your current working copy.

* `git merge` combines the branches, joining two or more development histories together. `git pull` essentially does `git fetch` followed by `git merge`. For example if you have created a new branch using `git branch <branchname>` `git checkout <branchname>`, completed your modifications on the branch and are happy with them. You can then merge this branch with the `master` after returning to it using `git checkout master`. Then run `git merge <branchname>` to merge your branch with the master.

#### Branching

Branching allows you to modify a certain aspect of the code without working directly on the `master` branch. For example, if a certain function within a program is not working we could run `git checkout -b fixfunc` to move to a new branch and work on it. Once we've got that function working again we can merge it with the original master branch using `git checkout master` `git merge fixfunc`.

#### Staging

The staging area is the purgatory of the git world. It is the middle ground between the working directory and the git directory (or git repository). `git add <filename>` will add  the specified file to the staging area. The status of the staging area can be observed using `git status`. To move a file from the staging area into the git repository `git commit -m "message"` should be used.

#### Upstream and Downstream

Generally speaking any repository that you `clone`, `pull` or `fetch` from is upstream from you, which you are downstream from it. Simples.

#### How do Repositories work?

When we call `git init` a hidden `.git` directory is created which will track all of the changes that are made within the repo. NOTE: if you want to remove the `.git` directory the command `rm -rf .git` can be used.

#### Forking a repository

This involves creating a copy of a repo you would like to work with, including a link back to the original. After clicking the "Fork" button on the original repo's page you will have a copy in you GitHub account. You can now `pull` the repo down to your machine to begin working on it, generate a branch and go to town.
