# git-basic-commands
git basic commands and details

Git tracks changes of the source code

Git Configuration
------------------
Configurations found in three levels:
- Repository (local)
- User account (global)
- Git installation (System)

configuration values are evaluated from the repository up

Path of the respositories:
- repository/.git/config -> Local(repository)
- User/vijay/.gitconfig -> Global (user directory)
- usr/local/etc/gitconfig -> System(git installation)

Git Config Commands
--------------------
git config --local user.name "test"

git config --local user.email "test@test.com"

git config --global credential.helper wincred

git config --list --show-origin -> show all config values and the file where they are defined

git config user.name  -> show the current user.name config value

git config -- global --unset user.name  -> Remove a specific setting for a specific level of config

git config -- global --edit  -> Edit a specific level of config directly

git config -- global --remove-section user  -> remove a section of config for a specific level

Git Hooks
------------
Server side Git Hooks:
- Pre-Receive
- Update
- Post-receive
 
Server side Git Hooks use cases:
 - Enforcing commit message format
- Enforcing user identity information
- Enforcing the signing of tags and/or commits
- Blocking access for specific IP addresses
- Blocking specific file extensions

Pull request workflow
-----------------------
1) push branch to remote & open pull request
2) Add reviewers & discuss changes
3) Make fixes in local branch & push to remote
4) Do not rebase, After pushing to remote
5) Merge to main & delete the branch 

Git Commands
-------------
git init

git clone <remote url>

origin - default name for remote server

git remote add <name> <remote url>  -> Provide the name for a remote server

git remote -v  -> list remotes and the URLs

git remote update

git ls-remote  -> list branches on remote 

git show-ref -> to view what refs you have in local

git add . -> add unstaged changes to staged area

git commit -m "" -> commit staged changes to local repository

git commit -a -m "" -> commit all changes(both unstaged and staged changes) to local repository

git commit --amend -> to change/modify the current commit which is not yet pushed

git status [--long(default)]

git status -s(--short)

git diff

git diff --staged  (git add .)

git diff --cached  (git commit)

git diff -w  -> with white sace changes 

git diff HEAD     (git commit -a)

git diff <commit>

git diff --cached <commit>

git diff <commit> <commit>

git diff feature main

git diff feature... main

git diff feature main file.txt

git log

git log --oneline -> To view the commit details in one line

git log --stat

git log --patch -> To get the detailed differences

git log -1 -> To view the history previous commit details

git log HEAD-5..HEAD^ -> To view the history previous commit within the specified range(difference between ie branch difference)

git log --grep <string> --oneline -> To search/filter the commits based on the search string

git log --graph --decorate --oneline -> show the commit history in graphal view with additional details(--graph=graph like structure, --decorate=positional references like branches& HEAD)

git show <hash> or <branch-name> or <HEAD> or <HEAD>~2 or <HEAD>^^

git blame <filename> -> shows you wher the lines in the file are comming from and when(shows how the commits are connected)

git rm --cached <filename> -> Delete file from index and not from Working area and Git repository

git rm <filename> or git rm -f <filename> -> Delete file from Git repository, index and local file system(working area) with force removal

git mv README.md README -> rename the file from local file system(working area), index nd does not touch Git repository

git restore [--staged] [--worktree] <filename> -> revert file changes availe in stage/index(--staged) or working/local file system(--worktree) area

git branch -l(--list)  -> list branch names(local)

git branch -a(--all) -> list both remote-tracking and local branches

git branch <new_branch_name> -> creating new branch

git branch -m <new-branch-name>  -> creating new branch and checkout that newly created branch

git branch -m <current-branch-name> <new-branch-name>  -> rename branch name

git branch -d <delete-branch-name>  -> delete a branch

git branch -D <delete-branch-name>  -> delete a branch forcefully that contains unmerged commits

git checkout -b <new-branch-name> -> creating new branch and checkout that newly created branch

git checkout <branch-name> (checkout the specified branch)

git checkout --track <branch-name> -> set up a local branch to track the remote branch

git stash

git stash list

git stash show

git merge <new_branch>

git merge abort

git reset --soft <HEAD^ or commit> -> moves the current branch and skip copies data from currenct commit in repository to both index and local file system(working area)

git reset or git reset --mixed <HEAD^ or commit> -> moves the current branch, copies data from currenct commit in repository to index

git reset --hard <HEAD^ or commit> -> moves the current branch, copies data from currenct commit in repository to both index and local file system(working area)

git fetch

git fetch origin <branch-name> -> fetch the feature branch from remote to local

git push or git push origin master -> Push the feature branch to remote

git push -u origin feature4  -> Push the feature branch to remote and set origin as the upstream branch

git pull 

git switch <branch-name> (if it does not work, then use git checkout)

git rebase

git rebase --interactive

git reflog <branch-name> -> shows the operation logs captured from local history

git revert
