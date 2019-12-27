# The Cheat Sheet Resources

## k8s:

```bash
kubectl get pods -n
kubectl logs -f  -n

```

## docker

```bash
kill all running containers
docker kill $(docker ps -q)

delete all stopped containers 
docker rm $(docker ps -a -q)

delete all images
docker rmi $(docker images -q)
```

## Git
* Workflow

```bash
- Git stash (if any local changes made).
- Create new branch / checkout  checkout -b JIRA-XXX-comment
- Pull rebase
- Git stash pop
- git status
- Git add
- git commit -am "JIRA-XXX-comment"
- git push origin JIRA-XXX-comment
- Create new pull request for it.
- Merge if accepted :)

```

* Combining the commits, To squash the last 2 commits into one:


```bash
- git reset --soft HEAD~2
- git commit -m "New message for the combined commit"

```

* Pushing the squashed commit, If the commits have been pushed to the remote:
git push origin +name-of-branch
The plus sign forces the remote branch to accept your rewritten history, otherwise, you will end up with divergent branches
If the commits have NOT yet been pushed to the remote:
git push origin name-of-branch
```


* If you are reusing a branch which current behind master: 

```bash

git fetch && git rebase origin/master OR git pull --rebase origin master

To avoid fast forward 
git push --force-with-lease
```

## linux

```bash
find . -mtime -1 -type f |xargs tar cvzf file.tar
ntpq -p
tcpdump -n -S -s 0 -A 'tcp dst port 80'
tar -czvf /tmp/logs.tar.gz logs/
rsync -avzPh origin:destination
:%s/foo/bar/g
```