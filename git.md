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

## Configure git

```
git config --global core.editor "vim"
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

## Splitting a commit

1. Edit the commit(s)

Replace "3" with the actual number of commits to be edited:

```
git rebase -i HEAD~3
```

Mark the commits to be edited, then save

2. Reset the commit

```
git reset HEAD^
```

3. Re-add the modified files to the staging area, and commit

4. Finish the rebase when done

```
git rebase --continue
```
