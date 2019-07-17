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
