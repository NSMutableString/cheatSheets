# Git cheat sheet

> My Git cheat sheet to handle :octocat:

## Menu
- [Verifying](#verifying)
- [Commiting](#commiting)
- [Branching](#branching)
- [Pulling](#pulling)
- [Pushing](#pushing)
- [Rebase](#rebase)
- [Stash](#stash)
- [Cherry-picking](#cherry-picking)
- [Revert](#revert)
- [Advanced](#advanced)

## Verifying

#### Show the current work state (staged and non staged)

```sh
git status
```

#### Show the difference of the non staged work

```sh
git diff
```

#### Show the difference of the work, also with the staged work

```sh
git diff --cached
```

#### show the last commit(s)

```sh
git log -p
```

__Tip:__ use `-- FILENAME` to list all the changes made to the given file.

## Commiting

#### Stage all files ready to commit

```sh
git add .
```

#### Stage certain file ready to commit

```sh
git add FILENAME
```
__Tip:__ use `-p` to go over all changes in that file by chunks so you can still choose what to stage or not.

#### Commit latest changes in your previous commit without changing the commit message

```sh
git commit --amend --no-edit
```

#### Fixup

```sh
git commit --fixup REF
```
__Tip:__ will look like a normal commit on top of your branch. We can rebase these changes in the commit where it belongs to.

## Branching

#### Create a new branch

```sh
git checkout -b BRANCH_NAME
```

#### Show all local branches

```sh
git branch
```

__Tip:__ use `-a` to list all remote and local branches

#### Delete a local branch

```sh
git branch -d BRANCH_NAME
```

__Tip:__ The `-d` option is an alias for `--delete`, which only deletes the branch if it has already been fully merged in its upstream branch. You could also use `-D`, which is an alias for `--delete --force`, which deletes the branch "irrespective of its merged status.

## Pulling

#### Reset your master branch to remote equivalent

```sh
git fetch origin
git reset --hard origin/master
```

#### Pull changes from remote server but saving uncommitted changes

This command makes this for you:

- Save your uncommitted changes locally with `git stash`.
- Local changes you made will be rebased on top of the remote changes.
- Return your uncommitted changes locally again.

```sh
git pull REMOTE_ORIGIN TARGET_BRANCH --rebase --autostash
```

#### Fetch all changes from remote server

git fetch really only downloads new data from a remote repository - but it doesn't integrate any of this new data into your working files. Fetch is great for getting a fresh view on all the things that happened in a remote repository.

```sh
git fetch --all
```

__Tip:__ add `--prune` for cleaning outdated local branches

## Pushing

#### Push changes to remote server

```sh
git push origin HEAD --force-with-lease
```

__Tip:__ create an alias like `git fp` for this in your .gitConfig

## Rebase

#### Rebase active branch to the given REF

```sh
git rebase REF -i --autosquash
```

__Tip:__ use `-i` to handle it interactive yourself

#### Rebase active branch on origin/master

```sh
git rebase -i origin/master --autosquash
```

__Tip:__ option `--autosquash` to handle fixups the correct way can be added as default in your .gitconfig

#### Abort the current rebase process

```sh
git rebase --abort
```

#### Continue the current rebase process

```sh
git rebase --continue
```

## Stash

#### Stash your current changes 

```sh
git stash
```

#### Apply your latest stash 

```sh
git pop
```

## Cherry-picking

Add the commit with REF to your branch

```sh
git cherry-pick REF
```

## Revert

Revert a commit with REF from your branch

```sh
git revert REF
```

## Advanced

#### Find and manage the history of all your Git stuff

```sh
git reflog
```

#### Show me the content of a certain file on another branch

```sh
git show BRANCH_NAME:FILE_NAME
```

#### remove your local git repository (Attention!)

```sh
rm -rf .git
```
