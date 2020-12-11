# GIT Commands

###### Revert to specific version
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
