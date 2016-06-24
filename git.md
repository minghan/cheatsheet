Useful Git commands
===================

Basics
------

Creating a repos

    $ git init

More basics

    $ git push -u origin master

Creating a remote repo, where 
path_working_folder has been git_init_ed and committed

    $ git clone --bare path_working_folder

Create a branch

    $ git branch experimental

Create a branch based on a remote branch
[more details](http://stackoverflow.com/questions/67699/how-do-i-clone-all-remote-branches-with-git)

    $ git branch -a # See what are the branches
    $ git checkout -b experimental origin/experimental
    $ git checkout -b <destination> <source>

List branches (current branch prefixed with *)

    $ git branch
    $ git branch -a # including remotes

Checking out a branch in working folder (either one)

    $ git checkout experimental # OR...
    $ git checkout master

Revert to state as of checkout (aka hg revert -a)

    $ git checkout -f master  # OR...
    $ git checkout .
    $ git checkout HEAD^ somefile  # Checkout a specific file from HEAD
    $ git checkout develop -- somefile.txt  # Checkout a file from another branch

Pull/push branch

    $ git pull origin experimental
    $ git push origin experimental

Merge from experimental onto the current branch

    $ git merge experimental

Commit

    # Commit with message
    $ git commit -m "Work in progress"
    # Commit and mark as fixup/squash
    $ git commit --fixup  <previous_commit_sha>
    $ git commit --squash <previous_commit_sha>

See git logs

    $ git log --oneline --decorate
    $ git log --pretty=oneline
    $ git log --pretty=format:'%h : %s' --graph

Checking diffs

    $ git diff master..test
    $ git diff HEAD~2
    $ git difftool --dir-diff HEAD
    $ git diff --no-index file\a file\b

Grep files in the work tree
(Note: always quit the pager with `q`, not `Control-C`)

    $ git grep some_pattern
    $ git grep FooBar -- ":(top)" ":(exclude)*.js" ":(exclude)*.json"

Git list/find files

    $ git ls-files "*.java"

Tagging a commit

    $ git tag stable-1 1b2e1d63ff

Commit to a new branch w/o first committing to a current branch

    $ git checkout -b new-branch    # then run git commit

Stash

    $ git stash save "message"
    $ git stash save --keep-index "message" # do not revert the state of the tree
    $ git stash list
    $ git stash apply # recommended
    $ git stash pop
    $ git stash clear

Undo a push (assuming no one has fetched)

    # git push -f origin last_known_good_commit:branch_name
    $ git push -f origin d0030e59f25f22d7d13f1a:exp_branch

Amend the commit message after a commit but before a push
    
    $ git commit --amend
    $ git commit --amend --no-edit # No changes to commit message

Undo the commit after a commit but before a push

    $ git reset --soft HEAD^
    # then edit your files...
    # then do your new commit

Garbage collection

    $ git gc --auto

Merge without fast forward (useful for explicitly declaring a merge was done)

    $ git merge --no-ff some-branch

Git addremove

    $ git add . ; git add -u    # OR...
    $ git add -A    # Supported in newer versions of git

Sync a fork (e.g. on [Github](https://help.github.com/articles/syncing-a-fork/))

    # First, see your remotes
    $ git remote -v
    # Configure git to point to a remote named 'upstream'
    $ git remote add upstream https://github.com/foo/repo.git
    # After fetching, upstream branches will be in upstream/*
    $ git fetch upstream
    # We want to sync the 'master' branch
    $ git checkout master
    $ git merge upstream/master

Merge and squash all commits in the merge

    $ git merge --squash some-src-branch
    # Commit the merge manually
    
Cherry pick

    $ git checkout <brach_you_want_to_apply_cherry_pick_on>
    $ git cherry-pick 9143a9

Cat a file (equivalent of `hg cat`)

    # git show rev:path/to/file
    $ git show HEAD:path/to/file.txt

Help

    $ git help <command>
    $ git help -a            # List all commands
    $ git help -g            # List all guides

Rebase
------

Rebase `develop` branch onto current working feature `foo` branch

    $ git fetch origin
    $ git checkout feature/foo
    $ git rebase origin/develop
    # Alternatively: $ git rebase -i --autosquash origin/develop

Squash last two commits into one using rebase

    $ git rebase HEAD~2 -i

    # Editor will then pop up.
    # Observe that the most recent commit is on the last line.
    # 1st line leave as pick, but from 2nd line onwards, replace pick with squash.
    # Editor will pop up again.
    # Merge the commit message and save.

Undo a rebase ([Reference](http://stackoverflow.com/a/135614/413672))

    # First, make sure you are in the right branch.
    # Assuming you have not garbage collected...
    # Then find the head you want to undo to in the ref log.
    $ git reflog
    # Verify that the version of HEAD you want is correct.
    $ git log "HEAD@{5}"
    # Reset to that state of HEAD.
    $ git reset --hard "HEAD@{5}"

See [this link](https://www.atlassian.com/git/tutorials/rewriting-history/git-rebase/) for a good rebase tutorial.

Patch
-----

Generate a patch for each of the last two commits

    $ git format-patch -2 HEAD

or

    # Dump 2 patches into one single file
    $ git format-patch -2 HEAD --stdout  > new_patch.diff
    # Still 2 patches, but apply as one
    $ git am < new_patch.diff --reject


Undoing a merge
---------------

If you get stuck and decide to just give up and throw the whole mess away,
you can always return to the pre-merge state with

    $ git reset --hard HEAD

Or, if you've already committed the merge that you want to throw away,

    $ git reset --hard ORIG_HEAD
    # Also: git reset --hard origin/<branch_name>

However, this last command can be dangerous in some cases -- never
throw away a commit if that commit may itself have been merged into 
another branch, as doing so may confuse further merges.

Clean
-----

Add `-n` flag for dry run.

    # Remove untracked files/directories
    $ git clean -fd
    # Remove untracked and (git)ignored files/directories
    $ git clean -fdx
    # Remove only (git)ignored files/directories, leave untracked files/directories
    $ git clean -fdX

Submodule
---------

Example usage:
    
    $ git submodule add git://github.com/altercation/vim-colors-solarized.git ~/.vim/bundle/solarized

To initialize the submodules when cloning:

    $ git clone --recurse-submodules git://github.com/minghan/cheatsheet.git

Alternatively, you can call submodule update after the clone:

    $ git submodule update --init --recursive

Etc
---

Git tree

    $ git log --graph --oneline
    $ git config --global alias.tree "log --graph --oneline"    # set as alias

Change remote url

    $ git remote set-url origin git@github.com:my_user_name/my_repo.git

Prune the remote branch list on local repo

    $ git fetch origin --prune
    # OR
    $ git remote update origin --prune

Delete a branch on remote

    $ git push origin --delete <branch_name>

For revision selection, see https://git-scm.com/book/en/v2/Git-Tools-Revision-Selection

Besides `git grep`, you might consider using [ack](http://beyondgrep.com/why-ack/) for navigating source code.

Gitflow
-------

Assumes you are using the [gitflow git extensions](https://github.com/nvie/gitflow).
Help is available at [gitflow wiki](https://github.com/nvie/gitflow/wiki/Command-Line-Arguments).

    $ git flow feature start <feature_x>
    # The above will create a new branch feature/feature_x
    # Now, do work...
    $ git flow feature finish <feature_x>
    # The above will merge changes into develop branch and delete the local copy of feature_x. 
