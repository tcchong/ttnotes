## Git

# Frequently used commands

clone a repository

```
$ git clone <URL>
```

show status

```
$ git status
```

```
$ git merge
$ git rebase
```

### Add

add changes to stage

```
$ git add <PATH>
```

stage new, modified and deleted fileds

```
$ git add . (v2.x)
$ git add -A
```

stage new and modified files only

```
$ git add . (v1.x)
$ git add --ignore-removal .
```

stage modified and deleted files only

```
$ git add -u
```

### Diff

```
$ git diff
```

summarize diff

```
$ git diff --stat
```

### Branch

create  new branch

```
$ git checkout -b <BRANCH>
```

checkout remote branch

```
$ git checkout -b <LOCAL_BRANCH> <REMOTE_BRANCH>
```

switch to branch

```
$ git checkout <BRANCH>
```

list branches

```
$ git branch
```

list branches that are merged / not merged

```
$ git branch --merged / --no-merged
```

delete fully merged branch

```
$ git branch -d <BRANCH>
```

delete branch even if not merged

```
$ git branch -D <BRANCH>
```

rename or move a branch

```
$ git branch -m <NAME>
```

remove branches that match the codition

    $ git branch -D `git branch | grep -E 'feature/some-.*-test'`
    # feature/some-foo-test
    # feature/some-bar-test

remove remote branch

```
$ git push <REMOTE> --delete <BRANCH>
```

### Commit

make a commit

```sh
$ git commit -m "<MESSAGE>"
```

automatically stage files that have been modified and deleted

```sh
$ git commit -am "<MESSAGE>"
```

### Remote

add remote

```
$ git remote add <NAME> <GIT_URL>
```

modify remote

```
$ git remote set-url <NAME> <GIT_URL>
```

fetch all remote branches

```
$ git fetch --all
```

checkout and track specific remote branch

```
$ git checkout --track <REMOTE>/<BRANCH>
```

### Stash

save local changes to stash

```
$ git stash save
```

list local stash

```sh
$ git stash list
```

remove from stash list and apply to current woring tree state

```sh
$ git stash pop
$ git stash pop <INDEX>
```

apply to current working tree state but do not remove from stash list

```
$ git stash apply
$ git stash apply <INDEX>
```

remove from stash list

```sh
$ git stash drop <INDEX>
```

### Push

set upstream for git pull / status

```
$ git push --set-upstream <REMOTE_BRANCH> <LOCAL_BRANCH>
```

set upstream for git pull / status to current branch

```
$ git push --set-upstream origin $(git_current_branch)
```

### Log

find specific text

```
$ git log --oneline -S'<TEXT_TO_SEARCH>' <FILE>
```

compare between commit

```
$ git log --stat
```

## Bisect

* [https://git-scm.com/book/zh-tw/v1/Git-工具-使用-Git-做-Debug](https://git-scm.com/book/zh-tw/v1/Git-工具-使用-Git-做-Debug)



## FAQ

**Q. How to amend a change to specific commit**

1. git stash save
2. git rebase -i &lt;COMMIT\_SHA1&gt;~1
3. change `pick` to `edit`
4. git add &lt;FILE&gt;
5. git commit --amend
6. git rebase --continue
7. git push -f

## Ref

* [https://feeding.cloud.geek.nz/posts/querying-deleted-content-in-git/](https://feeding.cloud.geek.nz/posts/querying-deleted-content-in-git/)



