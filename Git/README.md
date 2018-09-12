# Commands
## Local
```
git config --global push.default simple
git config --local user.name "aliang"
git config --local user.email aliang@
git commit -a -m "new examples"
git commit --amend
git checkout <commit> <file>
git cherry-pick -e <commit>
git stash
```

## Remote
```
git clone https://github.com/trymilix/cookbook.git
git pull  
git push
git remote -v
git remote set-url origin git@github.com:verigy/cookbooks.git
```

## Branch
```
git branch -a -v
git branch -r -v
git branch {new branch name}
git checkout {branch to switch}
```

# Reference
1. [Git](https://git-scm.com/docs/git)
2. [Git in Bash](https://git-scm.com/book/en/v2/Git-in-Other-Environments-Git-in-Bash)
3. [Git push requires username and password](http://stackoverflow.com/questions/6565357/git-push-requires-username-and-password)
4. [Grip -- GitHub Readme Instant Preview](https://github.com/joeyespo/grip)

