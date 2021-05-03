
origin = the Github repo location original t will change from the original origin ( https://github.com/Effyis/fluentd-aggregator) to my repo https://github.com/AOmer786/fluentd-aggregator.git

Before the above command is issued you have to create a repo on GitHub first to be able to used it as an organ and to push to after you clone it from any repository. 

 To remove git origin and add new origin:
```
git remote set-url origin https://github.com/AOmer786/fluentd-aggregator.git
```

To remove a remote origin:

git remote remove origin
To add a remote: 
git remote add origin yourRemoteUrl
and finally 
git push -u origin master 
