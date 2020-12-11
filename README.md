# Git Commands

### Tell Git Who You Are
Configure the author name and email address to be used with your commits.
Note that Git strips some characters (for example trailing periods) from user.name
```
git config --global user.name "Sam Smith"
git config --global user.email sam@example.com
```

### Create a New Local Repository
```
git init
```

### Check Out a Repository
Create a working copy of a local repository:
```
git clone </path/to/repository>
```
For a remote server, use:
```
git clone username@host:/path/to/repository
```
### Add Files
Add one or more files to staging (index):
```
git add <filename>
```
or
```
git add *
```
or [mac]
```
git add .
```

### Commit
Commit changes to head (but not yet to the remote repository):
```
git commit -m "Commit message"
```
Commit any files you've added with git add, and also commit any files you've changed since then:
```
git commit -a
```

### Push to Repo
Send changes to the master branch of your remote repository:
```
git push origin master
```

### Status
List the files you've changed and those you still need to add or commit:
```
git status
```
List all currently configured remote repositories:
```
git remote -v
```

### Connect to a Remote Repository
If you haven't connected your local repository to a remote server, add the server to be able to push to it:
```
git remote add origin <server>
```

### Branches
Create a new branch and switch to it:	
```
git checkout -b <branchname>
```
Switch from one branch to another:	
```
git checkout <branchname>
```
List all the branches in your repo, and also tell you what branch you're currently in:	
```
git branch
```
Delete the feature branch:	
```
git branch -d <branchname>
```
Push the branch to your remote repository, so others can use it:	
```
git push origin <branchname>
```
Push all branches to your remote repository:	
```
git push --all origin
```
Delete a branch on your remote repository:	
```
git push origin :<branchname>
```

### Update From the Remote Repository
Fetch and merge changes on the remote server to your working directory:
```
git pull
```
To merge a different branch into your active branch:	
```
git merge <branchname>
```
View all the merge conflicts:
```
git diff
```
View the conflicts against the base file:
```
git diff --base <filename>
```
Preview changes, before merging:
```
git diff <sourcebranch> <targetbranch>
```
After you have manually resolved any conflicts, you mark the changed file:	
```
git add <filename>
```

### Tags
You can use tagging to mark a significant changeset, such as a release:	
```
git tag 1.0.0 <commitID>
```
CommitId is the leading characters of the changeset ID, up to 10, but must be unique. Get the ID using:	
```
git log
```
Push all tags to remote repository:	
```
git push --tags origin
```

### Undo Local Changes
If you mess up, you can replace the changes in your working tree with the last content in head:
```
git checkout -- <filename>
```
Changes already added to the index, as well as new files, will be kept.

Instead, to drop all your local changes and commits, fetch the latest history from the server and point your local master branch at it, do this:
```
git fetch origin
git reset --hard origin/master
```

### Search
Search the working directory for foo():	
```
git grep "foo()"
```

### Revert to Specific Version
Note: Using this is dangerous in a collaborative environment: you're rewriting history!
```
git reset --hard <old-commit-id>
git push -f <remote-name> <branch-name>
```
you may need to do a
```
git push origin HEAD --force
```
instead of 
```
git push -f origin branch
```
as that may give you an error.
