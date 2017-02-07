# Commands

```sh
$ git clone
$ git log
$ git status
$ git diff

$ git branch
# delete local branch
# git branch -d <BRANCH>
$ git branch -d dev
$ git branch -m <NEW_NAME>

# add to stage
# git add <FILE>
$ git add .

# add to repository
# git commit -m "<MESSAGE>"
# git commit -am "<MESSAGE>"
$ git commit -m "first commit"

# add to remote
# git push -u <REMOTE> <REF>
$ git push -u origin master

# delete remote branch
$ git push origin --delete <BRANCH_NAME>

# git rebase <BRANCH>
$ git rebase master

# git merge <BRANCH>
$ git merge dev

# changing branch
# git checkout <BRANCH>
$ git checkout dev

# discard change
# git checkout -- <FILE>
$ git checkout -- .

# checkout to a new branch
# git checkout -b <BRANCH>
$ git checkout -b new-branch

# checkout remote branch
# git checkout -b <LOCAL_BRANCH> <REMOTE_BRANCH>
$ git checkout -b dev-function origin/dev-function

# fetch specific branch
# git fetch <REMOTE> <BRANCH>
$ git fetch origin dev

$ git remote add origin https://github.com/tcchong/test.git

# edit remote url
# git remote set-url <REMOTE> <URL>
$ git remote set-url origin git://xxxxxx.git

# OR modify with text editor
$ vim .git/config

# remove file from staging area
$ git reset HEAD <FILE>

$ git stash 
$ git stash list
$ git stash save "TMP"
$ git stash pop
$ git stash drop stash@{0}

# fetch remote branch
$ git fetch --all
$ git checkout --track <REMOTE>/<BRANCH>

$ git log --oneline -S'<TEXT_TO_SEARCH>' <FILE>
```



