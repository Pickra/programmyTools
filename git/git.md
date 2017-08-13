
# Git

## [Installation](installation.md)

### Geek Speak
- `local` = On your computer. Ex: That's a `local` branch.
- `remote` = On Github, or some other server. Ex: That's on the `remote` branch.
- `repo` = The repository that holds all the files. Ex: That's in my `local repo`.
- `origin` = The `remote` server where the `repo` lives.

### Git It
Git creates a time line. `master` is your home time line, a record of everything you’ve done.
The [git documentation](https://rogerdudler.github.io/git-guide/) will refer to `master` as a `branch`.
You can add `commits` to the `master` `branch`. A `commit` is a moment in time where someone did stuff.
If multiple people are working on a `repo`, it's safer to cut a new branch from `master`.
When you cut a new `branch`, you're cloning the old branch.
It's like creating a new time line, where everything in the past is the same
but you're creating a new future different from the old time line.
The new branch is a safe place for you to make changes and add more stuff;
you can always throw it away if something goes wrong. Once you've done some stuff on your new branch,
and `committed` your changes, you can `merge` your branch into `master`.
`Merging` a branch into another branch will either change the past or create a new future.
Congratulations, you're now a [Time Lord](https://en.wikipedia.org/wiki/Time_Lord).
Continue reading for some more basics or jump ahead to learn about
[Time Lord magic](https://github.com/Pickra/programmyTools/blob/master/git/moreGitStuff.md#time-lord-magic). 

Git/Time Lords have conventions for making branches:

- Again, `master` is the home time line.
- The `develop` branch is the recent history.
- A `feature/` branch is an alternate timeline cut from `develop`.
If everything works out on the `feature/` branch, it'll be `merged` to `develop`
and included in the recent history.
- A `release/` branch is cut from `develop`, and `merged` to `master`
where all the new changes from `develop` are then released into the universe for all your friends to see.
- You cut a `hotfix/` branch when something's broken on `master` and a fix is needed asap.

The above gives you a basic idea of some of these conventions,
but you should read more about the [Git Branching Model](http://nvie.com/posts/a-successful-git-branching-model/).

#### How do I get all the things on the Githubs onto my `local`?

1. Find where you want to put your clone of the `repo`.
2. Go to the `repo` on Github.
3. Look for the `Clone or download` button.
4. Copy the clone command. It'll look something like... 

```
git@github.com:AccountName/projectName.git
```

5. Go to your [terminal](../terminal/terminal.md), type `git clone URL` and paste in the clone command.


## The following commands are run in the [terminal](../terminal/terminal.md).

#### Where are the branches?
- `git branch`, shows the branches on your `local`.
- `git branch -a`, shows the branches on the `repo`.
- `git branch -D someBranch`, deletes someBranch on your `local`.
You can't be in the branch you want to delete.
Don't be afraid to delete branches because you can always you use [time lord magic][time-lord] to get it back.

#### How do I `git` into some branch?
- `git checkout someBranch`, moves you into some branch on your `local`.
- `git checkout -b someOtherBranch`, makes a new branch, on your `local` and moves you into it.

#### How do I `git` a branch onto my `local`?
`git pull origin branchName`.

This is actually a more complex question. 

- Do you already have a clone of that branch?
	- If not, then `git pull origin thatBranch` is all you need.
	- If so,
		- do you need what's in your `local` branch? Watch out for a [merge conflict][merge-conflict]!
		- if the version in the `remote` has everything you need, you can just delete that `local` branch... 

```
git branch -D thatBranch 
```
then pull down a fresh copy...

```
git pull origin thatBranch
```

`git fetch --all`, pulls down all the new branches from the `remote`.


#### I changed some stuff, now what?
1. `git status`, shows the files you changed. These files are `unstaged`.
2. `git add fileName`, gets the `unstaged` files ready to go. These files are now `staged`.
	- `git add -A`, `adds` all of the `unstaged` files without having to type in all of the file names.
	Be careful, with great power comes great responsibility.
3. `git commit -m "I did stuff!!"`, `commits` your `staged` changes.
4. `git log`, shows you all the `commits`, all the moments in time where something happened.
Each `commit` has a message, a number, who wrote it, and when it was written.
	- `git log -p`, shows what files changed and what changed in each file, for that `commit`.
	- `git diff`, is very similar but only shows the changes that occurred.
5. `q`, gets you out of `git log`.


#### I forgot to put something in my last `commit`, now what?
- `git commit -a --amend --no-edit`, puts all of the changes into the last `commit`
but doesn't change the message.
- `git commit -a --amend -m "What I meant to say was..."`, changes the `commit` message,
and adds your new changes.

#### Once your files are committed to going, they need a little push...
`git push origin branchName`, pushes the new `local `commits to the `remote` `branch`.

#### How do I delete a `remote` `branch`?
`git push origin :branchName`, deletes the `remote` `branchName`.

---
### Do you want to learn about `merge conflicts`, how to do `time lord magic` and [more git stuff](moreGitStuff.md)?


[time-lord]: https://github.com/Pickra/programmyTools/blob/master/git/moreGitStuff.md#time-lord-magic
[merge-conflict]: https://github.com/Pickra/programmyTools/blob/master/git/moreGitStuff.md#whats-a-merge-conflict