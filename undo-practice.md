# Git Toolkit

This file documents the Git Undo and Recovery Tools, I have learned.

## Reset

- git reset --soft Head~1: undo last commit, keep changes staged
- git reset --mixed Head~1: undo last commit, keep changes in working directory (default)
- git reset --hard Head~1: undo last commit and discard all changes (dangerous!)

- Only SAFELY use reset on commit that have not been pushed

## Revert

- git revert HEAD: create a new commit that undoes the last commit.
- git revert is safe for shared/pushed branches because it doesn't rewrite history.
- The original commit stays in the log, plus a new "undo" commit is added.

## Reflog

- git reflog: shows eevrywhere HEAD has pointed (commits, resets, checkouts).
- Reflog entries last about 90 days before being garbage collected.
- To recover: find the SHA in reflog, then git branch <name> <SHA>.

## Cherry-Pick

- git chery-pick <SHA>: apply a specific commit to the current branch.
- Creates a new commit with the same changes but a different SHA.
- Use for hotfixes: fix on feature branch, chery-pick to main.

## Bisect

- git bisect start: begin a binary search session
- git bisect bad: mark current commit as containing the bug
- git bisect good <ref>: mark a known-good commit 
- Git checks out middle commits; you test and mark good/bad
- git bisect reset:  end the session and return to original HEAD

