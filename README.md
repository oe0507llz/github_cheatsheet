# github_cheatsheet

### How to initialize a new git repo to an existing folder (not empty)?

1. Create a new repo on github

2. On local computer
```
cd my/folder/
git init
git remote add origin https:path/to/the/repository.git
git pull origin master
git add .
git commit -m 'init commit'
git push --set-upstream origin master
```

### How to deal with "refusing to merge unrelated histories" error?
`git pull --allow-unrelated-histories`

### git: diff between one file in local repo and remote repo
`git diff origin/master -- README.md`

### Temporarily switch to a different commit
If you want to temporarily go back to it, fool around, then come back to where you are, all you have to do is check out the 
desired commit:

```bash
# This will detach your HEAD, that is, leave you with no branch checked out:
git checkout 1d3d7fcdc
```

### Renaming a branch in github
https://stackoverflow.com/questions/9524933/renaming-a-branch-in-github
