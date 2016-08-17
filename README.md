###Git Commands
- `git init`
- `rm -rf .git/`
- `git remote add <name> <link>`
- `git remote -v`
- `git clone <repo url>`
- `git status`
- `git add -A`
- `git commit -m "<msg>"`
- `git push`
- `git pull` equals `git fetch && git merge`
- `git branch`
- `git checkout -b <branch name>` equals `git branch <branch name> && git checkout <branch name>`
- `git merge <from branch>`
- `git branch -d <branch name>`
- to stash untracked files --> `git add -A && git stash`
- `git stash pop` equals `git stash apply && git stash drop`
` `git log`
- `git log --oneline`
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
- `git diff --cached` to diff staging area and last commit
- `git diff HEAD` to diff all uncommited changes and last commit
- `git diff --stat`
- `git fetch && git diff origin/master` to compare local master and remote master
- `git fetch && git diff origin/master file1.js`
- `git blame file1.js`
- `git log -p -- file1.js`
- `git tag -a v1.0.0 -m "new feature added"`
- `git tag`
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
- `git rm --cached` to untrack files by looking at the latest .gitignore config
- `cd ~ && touch .gitignore_global && subl .gitignore_global`
- `git config --global core.exclude ~/.gitignore_global`

To remove unstaged files,
- `git clean -df && git checkout -- .`
