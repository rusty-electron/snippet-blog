## GitBlog - 1 

### Adding files 
* add files to git with a specific extension
```bash
# adding .py files
git add *.py
```

* if the files are inside a directory

```bash
git add models/\*.py

# or simply

git add models/*.py
```
### Removing files with clean
* remove all files that are not tracked by git
```bash
# If you want to see which untracked files will be removed before removing then you can run this command.

git clean -dn

# remove files by 
git clean -df
```
### Removing files with rm
* to delete your tracked files
```bash
git rm <file-path>

# if file is in staging area
git rm <file-path> -f
```

* to delete file from git repository but not from the file system

```bash
git rm --cached <file-path>
```

## Working with branches
You can create a branch locally as long as you have a cloned version of the repo.

* From your terminal window, list the branches on your repository.
```bash
git branch 

* master
 ```
This output indicates there is a single branch, the `master` and the `asterisk` indicates it is currently active.

* Create a new `feature branch` in the repository

```bash
git branch <feature_branch>
```

* Switch to the `feature branch` to work on it.

```bash
git checkout <feature_branch>
# You can list the branches again with the git branch command.
```

* Commit the change to the `feature branch`:
```bash
git add . 
git commit -m "adding a change from the feature branch"
```

* Switch back to the `master branch`.
```bash
git checkout master
```

* Push the `feature branch`:
```bash
$ git push origin <feature_branch>
```

### Altering branch name
* alter current branch name
```bash
git branch -m <new-branch-name>
```

* alter given branch name
```bash
git branch -m <old-branch-name> <new-branch-name>
```

*Note* : If you’ve already pushed the `branch` with old name, then there are a couple of extra steps required. You need to delete the `old branch` from the `remote` and push up the new one.

```bash
git push <remote-name> --delete <old-branch-name>

# change the name of the branch
git branch -m <new-branch-name>

# push changes
git push <remote-name> <new-branch-name> 

# if local branch name doesn’t match with the name of remote repository branch name, then

git push <remote-name> <local-branch-name>:<remote-branch-name> 
```


