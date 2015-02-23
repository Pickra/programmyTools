
# Git

## [Installation](installation.md)

## Git It
Git is like a bush. `master` is the dirt that the bush grows out of. Everything comes out of the dirt and eventually goes back to it. `develop` is the trunk that all the branches grow from. When you `cut a branch`, it's like you cloned the bush. The new branch has all of the same properties of the bush, `when` you cut it. A `feature/` branch has new stuff that's not ready for `develop`. A `release/` branch is a `feature/` you gave to your friend. You cut a `hotfix/` branch when your friend brings their `feature/` back because it has bugs on it. 

### Geek Speak
- `Local` 	= on your computer. Ex: That's a `local` branch.
- `Remote` 	= on Github, or some other server. Ex: That's on the `remote` branch.
- `Repo` 	= The repository that holds all the files. Ex: That's on my `local repo`. I put it on the `remote repo`

#### How do I get all the things on Github onto my computer?
- Find where you want to put your copy of the `repo`.
- Go to the `repo`on Github.
- Look for where it says `HTTPS clone URL`.
- Press the `copy to clipboard` button.
- Go to your [terminal](../terminal/terminal.md), `git clone` and paste in the url.

It'll look something like...

```
git clone https://github.com/projectName.git
```
## The following commands are run in the [terminal](../terminal/terminal.md).
#### Where are the branches?
- `git branch`, shows the branches on your computer.
- `git branch -a`, shows the branches on the `repo`.
- `git branch -D someBranch`, deletes some branch
- `git fetch origin` or `git fetch origin --all` pulls all the branches, from Github, onto your `local`. 

#### How do I get into a branch?
- `git checkout someBranch`, move into some branch on your computer.
- `git checkout -b someOtherBranch`, make a new branch and move into it.

#### I changed some stuff, now what?
1. `git status`, shows the files you changed. These files are `unstaged`.
2. `git add fileName`, gets the `unstaged` files ready to go. These files are `staged`.

	- `git add -A`, `add`s all of the `unstaged` files without having to type in all of the file names. Be careful, with great power comes great responsibility.
3. `git commit -m "I did stuff!!"`, puts your `staged` files in a box with a message that says what you did to the files.
4. `git log`, shows you all the `commit`s. Each `commit` has a message, a number, who wrote it, and when it was written.
	- `git log -p`, shows the files that changed, and what was changed in the `commit`.
5. `q`, gets you out of `git log`.


#### I forgot to put something in my last `commit`, now what?
- `git commit --amend --no-edit`, throws a change in the last `commit`.
- `git commit --amend -m "What I meant to say was..."`, changes the `commit` message, and throws in a change IF you have one.

#### Once your files are committed to going, they need a little push...
`git push origin remoteBranchName`

#### How do I get Count Chocula's branch changes, onto my `local` branch?
`git pull origin branchName`, `merges` Count Chocula's changes onto your branch.

---
### Congratulations! You just got some basic Git!

### Do you want to learn about `merge conflicts`, how to be a time lord and more [git stuff](intermediateGit.md)?



