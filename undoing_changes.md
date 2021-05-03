Step 1 - Git Checkout 
When working with Git, a common scenario is to undo changes in your working directory. The command git checkout will replace everything in the working directory to the last committed version.

If you want to replace all files then use a dot (.) to indicate the current directory, otherwise a list the directories/files separated by spaces.

```
# in the current working directory. ( the git repo folder )
$ git checkout . 

```

Step 2 - Git Reset 
If you're in the middle of a commit and have added files to the staging area but then changed your mind then you'll need to use the git reset command. git reset will move files back from the staging area to the working directory. If you want to reset all files then use a . to indicate current directory, otherwise list the files separated by spaces.

This is very useful when trying to keep your commits small and focused as you can move files back out of the staging area if you've added too many.

```
# The period at the end will rest all files in the current working directory.
$ git reset HEAD .
```

Step 3 - Git Reset Hard 
A git reset --hard will combine both git reset and git checkout in a single command. The result will be the files removed from the staging area and the working directory is taken back to the state of the last commit.

Protip

Using HEAD will clear the state back to the last commit, using git reset --hard <commit-hash> allows you to go back to any commit state. Remember, HEAD is an alias for the last commit-hash of the branch.

Step 4 - Git Revert 
If you have already committed files but realized you made a mistake then the command git revert allows you to undo the commits. The command will create a new commit which has the inverse affect of the commit being reverted.
If you haven't pushed your changes then git reset HEAD~1 has the same affect and will remove the last commit.

Step 5 - Git Revert 
To revert multiple commits at once we use the character ~ to mean minus. For example, HEAD~2 is two commits from the head. This can be combined with the characters ... to say between two commits.
Task

Use the command git revert HEAD...HEAD~2 to revert the commits between HEAD and HEAD~2.
Protip

You can use the command git log --oneline for a quick overview of the commit history.






