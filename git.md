# Git

## Clone a specific branch

```
git clone <url> -b <branch> --single-branch
```

From https://stackoverflow.com/questions/1778088/how-to-clone-a-single-branch-in-git

## Do a merge OSX-style

```
git config --global merge.tool opendiff
```

Then

```
git mergetool
```

## Push an existing repository to Github

So that next time you don't have to go through the "Create a new repository UI" just to get these magic incantations

```
git remote add origin git@github.com:radamanthus/myawesomeproject.git
git push -u origin master
```
## Squash the last two commits into one

```
git rebase --interactive HEAD~2
```

If you've already pushed the first commit, you'll have to do a push force. This is considered bad practice, unless you're absolutely the only one working on this repository.
