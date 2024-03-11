**`git stash`**
**`git stash list`**
**`git stash apply stash@{0}`**
**`git reset --hard HEAD^`** : moves the HEAD pointer to the previous commit (reset last commit)
**`git reset --hard ca83a6df`**: apply reseted commit in another branch
**`git commit --amend -m "Votre nouveau message de commit"`**
**`git commit --amend --no-edit`** : add file to last commit
**`git revert HEAD^`** creates a new commit that reverses the changes made in the previous commit
**`git reset --soft commit`** : see code before commit
**`git blame file`**: find who to blame
**`git branch -r`** : list remote branches
**`git clean -fdx`** : clean all ignored files