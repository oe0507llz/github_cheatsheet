# github_cheatsheet

#### How to initialize a new git repo to an existing folder (not empty)?

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

#### How to deal with "refusing to merge unrelated histories" error?
`git pull --allow-unrelated-histories`

#### git: diff between one file in local repo and remote repo
`git diff origin/master -- README.md`

#### Temporarily switch to a different commit
If you want to temporarily go back to it, fool around, then come back to where you are, all you have to do is check out the 
desired commit:

```bash
# This will detach your HEAD, that is, leave you with no branch checked out:
git checkout 1d3d7fcdc
```

#### Renaming a branch in github
https://stackoverflow.com/questions/9524933/renaming-a-branch-in-github

#### How do I update the password for Git?
https://stackoverflow.com/questions/20195304/how-do-i-update-the-password-for-git 
<br>
To fix this on macOS, you can use
```
git config --global credential.helper osxkeychain
```
A username and password prompt will appear with your next Git action (pull, clone, push, etc.).
<br><br>
For Windows, it's the same command with a different argument:
```
git config --global credential.helper wincred
```

#### How can I remove a commit on GitHub?
https://stackoverflow.com/questions/448919/how-can-i-remove-a-commit-on-github
<br>
For an easy revert if it's just a mistake (perhaps you forked a repo, then ended up pushing to the original instead of to a new one) here's another possibility:
```
git reset --hard 71c27777543ccfcb0376dcdd8f6777df055ef479
```
Obviously swap in that number for the number of the commit you want to return to.
<br><br>
Everything since then will be deleted once you push again. To do that, the next step would be:
```
git push --force
```
