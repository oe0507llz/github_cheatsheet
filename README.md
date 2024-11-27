# github_cheatsheet

#### Support for password authentication was removed. Please use a personal access token instead
https://stackoverflow.com/questions/68775869/support-for-password-authentication-was-removed-please-use-a-personal-access-to

#### git clone not working with error “ To access this repository, you must use the HTTPS remote with a personal access token or SSH with an SSH key”
https://stackoverflow.com/questions/67879615/git-clone-not-working-with-error-to-access-this-repository-you-must-use-the-h <br>
https://stackoverflow.com/questions/51634406/git-push-is-not-working-error-you-must-use-a-personal-access-token-or-ssh-key/60146283#60146283


#### How to initialize a new git repo to an existing folder (not empty)?

1. Create a new repo on github

2. On local computer
```
cd my/folder/
git init
git remote add origin https:path/to/the/repository.git
git pull origin main
git add .
git commit -m 'init commit'
git push --set-upstream origin main
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

#### How to switch branches?
When creating from scratch 
```
git clone xxx
cd xxx
git checkout chinese-translation
```
If we work with an existing repo
```
git pull
git checkout chinese-translation
git pull
```
If we would like to switch between master branch and feature branch
```
git checkout chinese-translation
git checkout master
git checkout chinese-translation
git checkout master
...
```

#### Working with Feature Branch
1. Every time before any sort of work in the local repo, always use `git pull` to pull the latest updates from remote to local

2. Always create feature branches based on the latest master branch (after `git pull`) by using `git checkout feature-branch-name`

3. If there are some new updates from others’ pull requests and merged into master branch, use `git merge master` on your feature branch to merge the latest updates from master branch into your own feature branch.

#### How do you attach a new pull request to an existing issue on github?
Simply reference the issue in your commit message using any of the supported keywords:
`close, closes, closed, fix, fixes, fixed, resolve, resolves, resolved`
For example: `this commit fixes #116`

#### Rollback to an old Git commit in github
```
git checkout [revision] .
```
where `[revision]` is the commit hash (for example: 12345678901234567890123456789012345678ab).

Don't forget the `.` at the end, very important. This will apply changes to the whole tree. You should execute this command in the git project root. If you are in any sub directory, then this command only changes the files in the current directory. Then commit and you should be good.

You can undo this by
```
git reset --hard 
```
that will delete all modifications from the working directory and staging area.

#### Checkout a branch from a fork with a pull request
https://github.community/t5/How-to-use-Git-and-GitHub/Checkout-a-branch-from-a-fork/td-p/77
```
git ls-remote --refs origin
git fetch origin pull/123/head:pr/123 && git checkout pr/123
```

#### How to change remote git repository
https://www.xenovation.com/blog/source-control-management/git/how-to-change-remote-git-repository 
<br>List existing remotes: `git remote -v`
<br>Change the remote repo: `git remote set-url origin https://github.com/oe0507llz/github_cheatsheet.git`

#### How can I make an older commit HEAD in Git?
https://stackoverflow.com/questions/13956207/how-can-i-make-an-older-commit-head-in-git
```
git reset --hard <commit-hash-id-to-put-as-head>
git push -f
```

#### Removing Files from a Git Repository Without Actually Deleting Them
https://danielmiessler.com/blog/removing-files-from-a-git-repository-without-actually-deleting-them/
```
git rm -rf --cached $FILES
```

#### How can I add an empty directory to a Git repository?
https://stackoverflow.com/questions/115983/how-can-i-add-an-empty-directory-to-a-git-repository
