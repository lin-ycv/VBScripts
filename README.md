# Git commands
| Function | Command | Notes |
|:---:|---|---|
| Create git | `git init` |
| Cloning a repo | `git clone URL folder-name-optional` | `--depth 1` to clone only lastest commit (saves space)
| Rename branch | `git branch -m old-name new-name`| `-M` to force rename
| New branch (clone) | `git switch -c branch-name`  | `-C` to force creation
| New branch (empty) | `git switch --orphan branch-name` |
| Delete branch | `git branch -d branch-name` | `-D` to force deletion
| Link to remote git | `git remote add origin URL` |
| Push to remote (first time) | `git push --set-upstream origin branch-name` |
| Push to Wiki| `git push  --force --set-upstream origin HEAD:master` | (older) Wiki still uses master instead of main
| Linking a git submodule | `git submodule add URL folder-name-optional` | this will clone the submodule, great if there's no local copy |
| Linking submodule without clone | `git update-index --add --cacheinfo 160000 <subrepo commit hash> <submod path>`<br>`git submodule init` | Edit/Create `.gitmodules` at root and add in <br>`[submodule "<submod path>"]`<br>`	path = <submod path>`<br>`	url = https://.....git`<br>and create the respective folder (can be empty)|
| Stage (selective) | `git add file-name folder/*` | enclose in single quote (') if there's space in name/folder |
| Stage (all) | `git add .` |
| Stage (interactive) | `git add -i`<br>`2`<br>`1,2,3,4,6` OR `1-4,6`<br>*enter*<br>`7` | use negative index to unstage `-1-4,-6` |
| Unstage (selective) | `git reset file-name folder/*` | enclose in single quote (') if there's space in name/folder |
| Unstage (all) | `git reset` |
| Commit | `git commit -m "Message"` |
| Undo commit | `git reset HEAD~1` |
| Push | `git push`|
| Push to new branch | `git push -u origin new-branch` | `-u` to set branch tracking local<-->remote |
