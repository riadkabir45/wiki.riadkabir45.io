# Git Documentations

All things I learned about Git

## Git Basics

Basics command to run git

> Git version

``` 
git --verion
```

> Git basic info setup

```
git config --global user.name "riadkabir45"
git config --global user.email "riadkabir45@gmail.com"
git config --global core.editor "vim --wait"
```



> Git Initialization

```
git init
```

> Check git folder status

```
git status
```

> Add file or folder to commit stage

``` fil
# Add all files
git add . 
# Add indivisual files
git add file1 file2 ...
```

> Finalize the commit

```
# Commit finalization needs a message for reference
git commit -m "Msg"
```



## Git commits

> List all commits

```
# Detailed commit history
git log

# Short commit history
git log --oneline
```



> Jump to previous commit

```
git checkout commit_id
```

> Jump to original head

``` 
git checkout branch_name
git reflog
```



## Git branch

> Create a new branch

```
git branch branch_name
```

> Rename branch

```
git branch -M branch_name
```



> Jump to that branch

```
git checkout branch_name
git switch branch_name
```

> Merge branch to current branch

```
# If both branch worked on different files. It will complete merge auto
git merge side_branch -m "msg"

# If conflict arise from both branch editing common file. Git will add hepler text to modified line. Users must chose what to keep and add and commit
```

> Rebase brunches

```
# Work undone
```



## Git extra

> Git ignore files

```
# Ignores all files in this file if it present
.gitignore
```

> Create a branch and move to it

```
git switch -c branch_name
git checkout -b branch_name
```

> Git check files edits

```
git diff --staged
```

> Git check time edits

```
git diff time1 time2
```

> Git stash to temporarily save current stage in a another head

``` 
# To store changes
git stash

# To get them back
git stash pop

# Get list of stashes
git stash list
```

