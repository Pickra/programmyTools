
# Git

## [Installation](installation.md)

## Git It
Git is like a bush. `master` is the dirt that the bush grows out of. Everything comes out of the dirt and eventually goes back to it. `develop` is the trunk that all the branches grow from. When you `cut a branch`, it's like you cloned the bush. The new branch has all of the same properties of the bush, `when` you cut it. A `feature/` branch has new stuff that's not ready for `develop`. A `release/` branch is a `feature/` you gave to your friend. You make a `hotfix/` branch when your friend brings his `feature/` back because it has bugs on it. 

### Geek Speak
- `Local` 	= on your computer. Ex: That's a `local` branch.
- `Remote` 	= on Github, or some other server. Ex: That's on the `remote` branch.
- `Repo` 	= The repository that holds all the files. Ex: That's on my `local repo`. I put it on the `remote repo`

#### How do I get all the things off of Github and onto my computer?
Find where you want to put your new `repo`, then: `git clone https://github.com/projectName.git`

#### Where are the branches?
- `git branch`, shows the branches on your computer.
- `git branch -a`, shows the branches on the `repo`.
- `git branch -D someBranch`, deletes some branch
- `git fetch origin` or `git fetch origin --all` pulls all the branches, from Github, onto your `local`. 

#### How do I get into a branch?
- `git checkout someBranch`, move into some branch on your computer.
- `git checkout -b someOtherBranch`, make a new branch and move into it.

#### I changed some stuff, now what?
- `git status`, shows the files you changed. These files are `unstaged`.
- `git add`, gets files that you changed, ready to go. These files are `staged`.
- `git commit -m "I did stuff!!"`, puts your `staged` files in a box with a message that says what you did to the files.
- `git log`, shows you all the `commit`s. Each `commit` has a message, a number, who wrote it, and when it was written.
- `q`, gets you out of `git log`.
- `git log -p`, shows the files that changed, and what was changed in the `commit`.

#### I forgot to put something in my last `commit`, now what?
- `git commit --amend --no-edit`, throws a change in the last `commit`.
- `git commit --amend -m "What I meant to say was..."`, changes the `commit` message, and throws in a change IF you have one.

#### Once your files are committed to going, they need a little push...
`git push origin remoteBranchName`

#### How do I get Count Chocula's branch changes, onto my `local` branch?
`git pull origin branchName`, `merges` Count Chocula's changes onto your branch.

---
### Congratulations! You just got some basic Git!

### Do you want to learn about `merge` conflicts, how to be a time lord and [more](intermediateGit.md)?



