## What's a merge conflict?
Count Chocula is working on the `feature/stuffAndThings` branch.
He changed line 20 of someFile.js on his `local` branch and pushed it to the `remote` branch.
You pulled his changes to your `local` branch. Git got mad and started talking about a `merge conflict`.

Count Chocula's line 20:

	I vant to eat your cereal!

Your line 20:

	I ride dragons.

#### You have a `merge conflict` because Count Chocula's line 20 is different than yours. 
- Git is mad because it doesn't know which version of line 20 to use.
- Do a `git status` to see the file(s) that are in conflict and open a file.
- In the file you will see...

```
<<<<<<< HEAD
I vant to eat your cereal!
=======
I ride dragons.
>>>>>>> theCommitNumber
```
	
... delete the extra stuff that Git throws in there, and the line that you don't want.

#### When you've fixed all your `merge conflicts`:
1. `git status`
2. `git add` the file(s) that changed.
3. `git rebase --continue` or `git merge --continue`
(depends on the situation... Git will tell you which one to use),
tells Git that you've fixed the `merge conflicts` and are ready to move on.

Once the merge is done, Git will ask you to put in a message about the merge.
Now you're in `vi` or `vim`, more on that in [terminal](../terminal/terminal.md).
Just ignore it for now and `:q`, to get out.

And the `merge conflict` is over!!

<br>

## Time Lord Magic

### Moving through time

In order to move through time, you need to know about the `HEAD`.
The `HEAD` is the most recent `commit` of the branch or the `tip` of the branch.
A Time lord moves through time in relation to the `HEAD`.

Ex: Doctor Who is in the year 2015, the 2015 `commit` is the `HEAD`. He wants to see some dinosaurs.
He looks through the `git log` to find a `commit` with dinosaurs in it.
Then he uses `git reset` to move through time to a `commit` with dinosaurs.

- `git reset --soft commitNumber`, is like visiting the past in virtual reality.
You can see and interact with everything, but you're not actually there.
When Doctor who uses `reset --soft` to move to a `commit` with dinosaurs,
he's still in the present; the `HEAD` is still 2015.

- `git reset --hard commitNumber`, changes the timeline.
When Doctor who uses `reset --hard` to move to a `commit` with dinosaurs,
he's now in the time of dinosaurs; he has `reset` the `HEAD` to the commit with dinosaurs.
Be careful when using `--hard`, you can easily lose changes.

- `git reflog`, is a more robust `git log`.
It shows all of your Git activity; `checkouts`, `pulls/pushes`, moving through time, etc...
If Doctor Who gets stranded in the past, he can use `git reflog` to `git reset --hard`
back to the commit before he went to the past.

Let's look at an example of accidental deletion. If you delete some stuff that you need,
you can `git reflog` to find a spot before you deleted that stuff...

```
2l3h9ck HEAD{0}: commit: gave a dinosaur a cool mustache
mwns720 HEAD{1}: commit: deleted my ancestor
28y3hw1 HEAD{2}: commit: taught dinosaurs how to ride a skateboard
m2w0jw2 HEAD{3}: checkout: moving from develop to feature/DinosaursOnSkateboards
2lkwn22 HEAD{4}: pull origin develop: Fast-forward
```

The first line is the current point in time, the last change that was made, or the `tip` of your branch.

```
2l3h9ck HEAD{0}: commit: gave a dinosaur a cool mustache
```

The 1st 7 characters are an abbreviated `commit` number or `commit` `hash`.
`HEAD{0}` is just another representation of that `commit` `hash`.
Either can be used like an bookmark in time.
Since I accidentally deleted my ancestor at `commit` number mwns720, or `HEAD{1}`,
I can reset time back to before I deleted my ancestor.
`git reset --hard mwns720` or `git reset --hard HEAD{1}`;

<br>

### More Time Lord Magic

`git merge feature/someBranch` ...`merges` some feature branch into the branch you're in.
It's like when Doctor Who [regenerates][regenerates].
He's still Doctor Who, an alien with a tardis who travels through time, but with new features.

#### I have a bunch of commits on this branch and I don't want to fix the same merge conflict multiple times!$!@&!!!!!

You can use `git rebase` to squash as many `commits` as you want into 1 `commit`.

- `git rebase -i HEAD~the-number-of-commits-you-want-to-squash`,
takes the number of commits after `HEAD~` and squashes them into 1 `commmit`.
- `git rebase --abort` or `git merge --abort`,
when your rebase or merge goes wrong and you just want to get out of there.

<br>

## More Git Stuff
[The Simple Guide](http://rogerdudler.github.io/git-guide/)
<br>
[Git for Beginners](http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)
<br>
[Git Configuration](http://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)


[regenerates]: http://en.wikipedia.org/wiki/Regeneration_%28Doctor_Who%29