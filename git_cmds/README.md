# mygitcommands
This repository is used to record all the useful git commands I've been using 

## 1. Config 

Add a new remote

`git remote add origin git@github.com:User/UserRepo.git`

Change the url of an existing remote repository

`git remote set-url origin git@github.com:User/UserRepo.git`

Show config

`git config --list`

Add config

`git config --global user.email "username@yahoo.com"`

`git config --global user.name "username"`

## 2. Log

To show commit history 

`git log`

`git log --oneline`

To show changes in a specific commit

`git show commit_id`

`git show commit_id --name-only`

## 3. Add

Undo add file

`git reset <file>`

Undo add all

`git reset`

## 4. Commit 

Undo commit and add to all

`git reset HEAD~`

## 5. Branch

Delete local branch

`git branch -d <branch_name>`

Delete remote branch

`git push -d <remote_name> <branch_name>`

## 6. Diff

Shows the changes between the working directory and the index. This shows what has been changed, but is not staged for a commit.

`git diff`

Shows the changes between the index and the HEAD (which is the last commit on this branch). This shows what has been added to the index and staged for a commit.

`git diff --cached`

Shows all the changes between the working directory and HEAD (which includes changes in the index). This shows all the changes since the last commit, whether or not they have been staged for commit or not.

`git diff HEAD`

```

                     |---HEAD---|
 git diff --cached     |      |
                   |Index|    |           git diff HEAD
 git diff              |      |    
                      |Working Tree|
                      
```

## 7. file history

History from file bar is created

`git log -p bar`

History from file is created which contains both old names and new name

`git log --follow -p -- path-to-file`

## 8. discard local changes

`git checkout -- path/to/file/to/revert`

## 9. Stash 

Stash changes 

`git stash save "any name"`

Apply the most recent changes in stash 

`git stash pop`
          
          
   


