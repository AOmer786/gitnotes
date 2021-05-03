Working Remotely 

Step 1 - Git Remote 
Remote repositories allow you to share changes from or to your repositoy. Remote locations are generally a build server, a tem members machine or a centralised store such as Github.com. Remotes are added using the git remote command with a friendly name and the remote location, typically a HTTPS URL or a SSh connection for example https://github.com/OcelotUproar/ocelite.git or git@github.com/OcelotUproar/ocelite.git

The friendly name allows you to refer to the location in other commands your local repository can reference multiple different remote repositories depending on your scenario. 

Protip :If you use git clone, discussed in a future scenario, then the location you're cloning from will be automatically added as a remote with the name origin. 


```
$ git remote add origin ( < friendly name. This could be anything )  https://github.com/OcelotUproar/ocelite.git. ( < friendly name points to the URL aka Github repository) 
```

Step 2 - Git Push 
When you're ready to share your commits you need to push them to a remote repository via git push. A typical Git workflow would be to perform multiple small commits as you complete a task and push to a remote at relevant points, such as when the task is complete, to ensure synchronization of the code within the team.
The git push command is followed by two parameters. The first parameter is the friendly name of the remote repository we defined in the first step. The second parameter is the name of the branch. By default all git repositories have a master branch where the code is worked on.

```
$ git push origin master
```


Repository Info 
Protip

```
# shows the friendly name of the remote repository
$ git remote show

# To get only the remote repo url use the below command 
$ git config --get remote.origin.url

$ git remote show origin ## the origin is a friendly name which can be anything But is like an alias to the ##Regmote repo for example GitHub. 
```

Step 3 - Git Pull 
Where git push allows you to push your changes to a remote repository, git pull works in the reverse fashion. git pull allows you to sync changes from a remote repository into your local version.

The changes from the remote repository are automatically merge into the branch you're currently working on. 

```
$ git pull <ahmed "friendly-name" usually "origin"> master
```

Step 4 - Git Log 
As described in the previous scenario you can use the git log command to see the history of the repository. The git show command will allow you to view the changes made in each commit.

In this example, the output from git log shows a new commit by "DifferentUser@JoinScrapbook.com" with the message "Fix for Bug #1234". The output of git showhighlights the new lines added to the file in green.
Protip

Use the command git log --grep="#1234" to find all the commits containing #1234

Step 5 - Git Fetch and Branches 
The command git pull is a combination of two different commands, git fetch and git merge. Fetch downloads the changes from the remote repository into a separate branch named remotes/<remote-name>/<remote-branch-name>. The branch can be accessed using git checkout.

Using git fetch  is a great way to review the changes without affecting your current branch. The naming format of branches is flexible enough that you can have multiple remotes and branches with the same name and easily switch between them.

```
$ git fetch
and then 
$ git checkout remotes/origin/master ## to view the changes. 

Note: checking out 'remotes/origin/master'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by performing another checkout.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -b with the checkout command again. Example:

  git checkout -b <new-branch-name>
```

List All Branches

1. To see local branches, run this command: git branch.
2. To see remote branches, run this command: git branch -r.
3. To see all local and remote branches, run this command: git branch -a

The following command will merge the fetched changes into master.

```
git merge remotes/<remote-name>/<remote-branch-name> master
```


