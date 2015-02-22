
# Git

## [Installation](installation.md)

## Git It
Git is like a bush. `master` is the dirt that the bush grows out of. Everything comes out of the dirt and eventually goes back to it. `develop` is the trunk that all the branches grow from. When you `cut a branch`, it's like you cloned the bush. The new branch has all of the same properties of the bush, **when** you cut it. A `feature/` branch has new stuff that's not ready for `develop`. A `release/` branch is a `feature/` you gave to your friend. You make a `hotfix/` branch when your friend brings his `feature/` back because it has bugs on it. 

### Geek Speak
- __Local__ = on your computer. Ex: That's a *local* branch.
- __Remote__ = on Github, or some other server. Ex: That's on the *remote* branch.
- __Repo__ = The repository that holds all the files. Ex: That's on my *local repo*. I put it on the *remote repo*

#### How do I get all the things off of Github and onto my computer?
Find where you want to put your new *repo*, then: `git clone https://github.com/projectName.git`

#### Where are the branches?
- `git branch`, show the branches on your computer.
- `git branch -a`, show the branches on the *repo*.
- `git branch -D someBranch`, deletes some branch
- `git fetch origin` or `git fetch origin --all` pulls all the branches, from Github, onto your `local`. 

#### How do I get into a branch?
- `git checkout someBranch`, move into some branch on your computer.
- `git checkout -b someOtherBranch`, make a new branch and move into it.

#### I changed some stuff, now what?
- `git status`, shows the files you changed. These files are **unstaged**.
- `git add`, gets files that you changed, ready to go. These files are **staged**.
- `git commit -m "I did stuff!!"`, puts your **staged** files in a box with a message that says what you did to the files.
- `git log`, shows you all the commits. Each commit has a message, a number, who wrote it, and when it was written. `q`, to get out of `git log`.
- `git log -p`, shows the files that changed and what was changed in the commit.

#### I forgot to put something in my last commit, now what?
- `git commit --amend --no-edit`, throw a change in the last commit, and don't change the message.
- `git commit --amend -m "What I meant to say was..."`, throw a change in the last  commit, and change the message.

#### Once your files are committed to going, they need a little push...
`git push origin remoteBranchName`

#### How do I get Count Chocula's branch changes, onto my *local* branch?
`git pull origin branchName`, *merges* Count Chocula's changes onto your branch

#### What's a merge conflict?

You pulled some stuff from Count Chocula's copy of someBranch. Git got mad and started talking about a merge conflict.

Count Chocula's changed line 20 of thisFile.js, and pushed it to the *remote* branch. You pulled his changes to your *local* branch.

Count Chocula's line 20:

	I vant to eat your cereal!

Your line 20:

	I ride dragons.

You have a __merge conflict__ because Count Chocula's line 20 is different than yours. 

Git is mad because it doesn't know which version of line 20 to use. Do a `git status` to see the files that are in conflict and open the file... 

	<<<<<<< HEAD
	
	I vant to eat your cereal!
	=======
	I ride dragons.
	>>>>>>> commit #
	
... delete the extra stuff that Git throws in there, and the line that you don't want.

When you're done with all your *merge conflicts*:

1. `git status`
2. `git add` the files that changed.
3. `git rebase --continue`, tells git you're done with the merge.

Once the merge is done, your terminal will ask you to put in a message about the merge, but you can ignore it and just `:q!`, to get out. And the *merge conflict* is over!!

#### I have a bunch of commits on this branch and I don't want to fix the the same merge conflict 20 times...
- `git rebase -i HEAD~the-number-of-commits-you-want-to-squash`
-  `git merge --abort`, when your rebase goes wrong and you just want to get out of there.

#### How to be a time lord
- `git reset --soft commitNumber`
- `git reset --hard commitNumber`
- `git reflog`

#### More Info
[The Simple Guide](http://rogerdudler.github.io/git-guide/)
<br><br>
[Git for beginners](http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)
<br><br>
[git branching model](http://nvie.com/posts/a-successful-git-branching-model/)



