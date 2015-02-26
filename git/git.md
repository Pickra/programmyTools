
# Git

## [Installation](installation.md)

## Git It
Git is like a bush. `master` is the dirt that the bush grows out of. Everything comes out of the dirt and eventually goes back to it. `develop` is the trunk that all the branches grow from. When you `cut a branch`, it's like you cloned the bush. The new branch has all of the same properties of the bush, `when` you cut it. A `feature/` branch has new stuff that's not ready for `develop`. A `release/` branch is a `feature/` you gave to your friend. You cut a `hotfix/` branch when your friend brings their `feature/` back because it has bugs on it.

This is called the [Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/).

Git is also kind of like a [tardis][tardis], but more about [time lord][time-lord] magic later.

### Geek Speak
- `local` 	= On your computer. Ex: That's a `local` branch.
- `remote` 	= On Github, or some other server. Ex: That's on the `remote` branch.
- `repo` 	= The repository that holds all the files. Ex: That's in my `local repo`.
- `merge`	= Merges 1 branch into the other branch. I `merged` smellyBranch into hairyBranch. Now hairyBranch is smelly too, and the smelly branch is gone; unless you use [time lord][time-lord] magic.
- `origin`	= The `remote` server where the `repo` lives.

#### How do I get all the things on the Githubs onto my `local`?
1. Find where you want to put your clone of the `repo`.
2. Go to the `repo` on Github.
3. Look for where it says `HTTPS clone URL`.
4. Press the `copy to clipboard` button.
5. Go to your [terminal](../terminal/terminal.md), `git clone URL`.

It'll look something like...

```
git clone https://github.com/projectName.git
```

## The following commands are run in the [terminal](../terminal/terminal.md).
#### Where are the branches?
- `git branch`, shows the branches on your `local`.
- `git branch -a`, shows the branches on the `repo`.
- `git branch -D someBranch`, deletes someBranch. You can't be in the branch you want to delete. Don't be afraid to delete branches because you can always you use [time lord][time-lord] magic to get it back.

#### How do I get into some branch?
- `git checkout someBranch`, move into some branch on your `local`.
- `git checkout -b someOtherBranch`, make a new branch and move into it.

#### How do I get a branch onto my `local`?
`git pull origin branchName`, `merges` a `remote` branch into your branch.

This is actually a more complex question. 

- Do you already have a clone of that branch?

	- If not, then `git pull origin thatBranch` is all you need.
- If so

	- do you need what's in your `local` branch? Watch out for a [merge conflict][merge-conflict]!
	- or will the version in the `repo` have everything you need? If you run into a [merge conflict][merge-conflict], you can just... 

```
git branch -D thatBranch 
```
then 

```
git pull origin thatBranch
```

`git fetch --all`, tells you about all the new stuff from the `remote repo`, so you don't have to ask your friend for the name of the branch you want to `checkout`. New stuff: new branches and new stuff not in existing `local` branches.


#### I changed some stuff, now what?
1. `git status`, shows the files you changed. These files are `unstaged`.
2. `git add fileName`, gets the `unstaged` files ready to go. These files are `staged`.

	- `git add -A`, `adds` all of the `unstaged` files without having to type in all of the file names. Be careful, with great power comes great responsibility.
3. `git commit -m "I did stuff!!"`, puts your `staged` files in a box with a message that says what you did to the files.
4. `git log`, shows you all the `commits`. Each `commit` has a message, a number, who wrote it, and when it was written.
	- `git log -p`, shows what files changed and what changed in each file, for that `commit`.
5. `q`, gets you out of `git log`.


#### I forgot to put something in my last `commit`, now what?
- `git commit --amend --no-edit`, throws a change in the last `commit` but doesn't change the message.
- `git commit --amend -m "What I meant to say was..."`, changes the `commit` message, and throws in a change IF you have one.

#### Once your files are committed to going, they need a little push...
`git push origin remoteBranchName`

---
### Do you want to learn about `merge conflicts`, how to be a `time lord` and [more git stuff](moreGitStuff.md)?


[tardis]: http://en.wikipedia.org/wiki/TARDIS
[time-lord]: https://github.com/Pickra/programmyTools/blob/master/git/moreGitStuff.md#time-lord-magic
[merge-conflict]: https://github.com/Pickra/programmyTools/blob/master/git/moreGitStuff.md#whats-a-merge-conflict