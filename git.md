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

List branches (current branch prefixed with *)

    $ git branch
    $ git branch -a # including remotes

Checking out a branch in working folder (either one)

    $ git checkout experimental # OR...
    $ git checkout master

Revert to state as of checkout (aka hg revert -a)

    $ git checkout -f master  # OR...
    $ git checkout .
    $ git checkout HEAD^ somefile  # Checkout a specific file

Pull/push branch

    $ git pull origin experimental
    $ git push origin experimental

Merge from experimental onto the current branch

    $ git merge experimental

See git logs

    $ git log --pretty=oneline
    $ git log --pretty=format:'%h : %s' --graph

Checking diffs

    $ git diff master..test

Grep files in the work tree

    $ git grep some_pattern

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

    $ git push -f origin d0030e59f25f22d7d13f1a:exp_branch

Amend the commit message after a commit but before a push
    
    $ git commit --amend

Undo the commit after a commit but before a push

    $ git reset --soft HEAD^
    # then edit your files...
    # then do your new commit

Garbage collection

    $ git gc

Merge without fast forward (useful for explicitly declaring a merge was done)

    $ git merge --no-ff some-branch

Git addremove

    $ git add . ; git add -u    # OR...
    $ git add -A    # Supported in newer versions of git

Add upstream remote

    $ git remote add upstream http://some_github_url/

Pull in upstream changes (e.g github)

    $ git fetch upstream
    $ git merge upstream/master

Rebase
------

Squash last two commits into one using rebase

    $ git rebase HEAD~2 -i

    # Editor will then pop up.
    # Observe that the most recent commit is on the last line.
    # 1st line leave as pick, but from 2nd line onwards, replace pick with squash.
    # Editor will pop up again.
    # Merge the commit message and save.


Patch
-----

Generate a patch for each of the last two commits

    $ git format-patch -2 HEAD

or

    # Dump 2 patches into one single file
    $ git format-patch -2 HEAD --stdout  > new_patch.diff
    # Still 2 patches, but apply as one
    $ git am < new_patch.diff


Undoing a merge
---------------

If you get stuck and decide to just give up and throw the whole mess away,
you can always return to the pre-merge state with

    $ git reset --hard HEAD

Or, if you've already committed the merge that you want to throw away,

    $ git reset --hard ORIG_HEAD

However, this last command can be dangerous in some cases -- never
throw away a commit if that commit may itself have been merged into 
another branch, as doing so may confuse further merges.

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

Change remote url

    $ git remote set-url origin git@github.com:my_user_name/my_repo.git
