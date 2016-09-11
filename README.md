###Git Commands
- `git init`
- `rm -rf .git/`
- `git remote add <name> <link>`
- `git remote -v`
- `git remote show origin`
- `git remote rm <remote name>`
- `git clone <repo url> [<local dir name>]`
- `git status`
- `git add -A`
- `git rm <file>`
- `git add "*.txt"`, Add all txt files in the whole project
- `git reset HEAD <file>`, to unstage the file, dont do this after push
- `git commit -m "<msg>"`
- `git reset --soft HEAD^`, to undo a local commit and reset into staging
- `git add <file> && git commit --amend -m <msg>`, to add file to the previous commit, dont do this after push
- `git push <remote name> <local branch to push>[:<remote branch name>]`
- `git pull` equals `git fetch && git merge`, and a new merge commit is created
- `git branch <new branch name>`, to create a new branch locally
- `git branch -a`
- `git checkout -b <branch name>` equals `git branch <branch name> && git checkout <branch name>`
- `git merge <from branch>`
- `git push <remote name> :<branch name>`, to remove a remote branch
- `git branch -d <branch name>`
- `git remote prune origin`, To clean up deleted remote branches
- to stash untracked files --> `git add -A && git stash`
- `git stash [<message>]`
- `git stash --keep-index`, stash only files not in staged area
- `git stash --include-untracked`
- `git stash list -stat`
- `git stash pop` equals `git stash apply && git stash drop`
- `git stash show stash@{0} --stat`, show stat of a stash
- `git stash show stash@{0} --patch`, show file diff of a stash
- `git stash clear`
` `git log`
- `git log --oneline`
- `git log --oneline -p`
- `git log --decorate`
- `git log --graph`
- `git log -p`
- `git log --stat`
- `git log --stat --oneline`
- `git log -3`
- `git log --after="yesterday"`
- `git log --after="30 minutes ago"`
- `git log --after="2 weeks ago"`
- `git log --after="last tuesday"`
- `git log --after="last week"`
- `git log --after="3-15-16"`
- `git log --after="3/15/16" --before="yesterday"` equals `git log --since="3/15/16" --until="yesterday"`
- `git log -i --author="Tony\|Wini"`
- `git log --grep="copyright"`
- `git log -p -S"myFunc()"` to search for code changes
- `git log -p -GmyFunc()\|myFunc2()`
- `git log --no-merges`
- `git log master..cool-feature`
- `git log -p -- file1.js`
- `git diff` to diff last commit and cwd
- `git diff --staged` to diff last commit and staging files
- `git diff --cached` to diff staging area and last commit
- `git diff HEAD` to diff all uncommited(both staged and unstaged) changes and last commit
- `git diff HEAD~5..HEAD~4` to diff between commits
- `git diff <branch A>..<branch B>` to diff between branches
- `git diff --since=1.week.ago --until=1.minute.ago` to do time-based diff
- `git diff --stat`
- `git fetch && git diff origin/master` to compare local master and remote master
- `git fetch && git diff origin/master file1.js`
- `git blame file1.js`
- `git log -p -- file1.js`
- `git tag`, to show all tags
- `git tag -a v1.0.0 -m "new feature added"`
- `git push --tags`
- `git rebase -i origin/master` to allow us to squash commits to a single commit
- `git push -f origin/feature-1`, after squashing commits, force push
- `git rebase --abort`
- `git bisect start`
- `git bisect good`
- `git bisect good <commit hash>`
- `git bisect bad`
- `git bisect reset`
- `cd .git/hooks && touch pre-commit && chmod +x ./pre-commit`
```
#!/bin/bash
go test -v
```
- `git config --global user.name 'Tony Kung'`
- `git config --global user.email 'tony@tony.com'`
- `git config --global core.editor subl`
- `git config --global alias.graph 'log --graph --oneline'` to have `git graph`
- `cat ~/.gitconfig`
- `git config --list`
- `touch .gitignore`
- `git rm --cached <file>` to untrack files (the file remains in the local file system) by looking at the latest .gitignore config
- `git rm <file>` to untrack files & remove it from the file system
- `cd ~ && touch .gitignore_global && subl .gitignore_global`
- `git config --global core.exclude ~/.gitignore_global`

To remove unstaged files,
- `git clean -df && git checkout -- .`
- `git checkout -- <file>`

To force push to feature branch, never do this on master branch unless you know what you are doing,
- `git push --force origin <feature branch>`

To fix line break on different OS
- `git config --global core.autocrlf input`, used on linux and os x, Changes CR/LF to LF on commit
- `git config --global core.autocrlf true`, used on Windows, Changes LF to CR/LF on checkout and converts back to LF on commit

To pick a message and merge to a branch
- `git cherry-pick --edit <git commit hash>`
- `git cherry-pick --no-commit <git commit hash 1> <git commit hash 2>`, pull in changes from those two commits and put in staged area
- `git cherry-pick -x <git commit hash>`, include the source commit hash in the commit message of the new commit

Working with submodules
- `git submodule add <repo url>`
- `cat .gitmodules`
- `git submodule init && git submodule update`
