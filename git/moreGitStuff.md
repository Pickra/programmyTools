## What's a merge conflict?
Count Chocula is working on the `feature/stuffAndThings` branch. He changed line 20 of someFile.js on his `local` branch and pushed it to the `remote` branch. You pulled his changes to your `local` branch. Git got mad and started talking about a `merge conflict`.

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
2. `git add` the files that changed.
3. `git rebase --continue` or `git merge --continue` (depends on the situation... Git will tell you which one to use), tells Git that you've fixed the `merge conflicts` and are ready to move on.

Once the merge is done, Git will ask you to put in a message about the merge. Now you're in `vi` or `vim`, more on that in [terminal](../terminal/terminal.md). Just ignore it and `:q`, to get out.

And the `merge conflict` is over!!

<br>
## Time Lord Magic
### Moving through time

In order to move through time, you need to know about the `HEAD`.

The `HEAD` is the most recent `commit` of the branch or the `tip` of the branch. A Time lord jumps through time in relation to the `HEAD`.

Ex: Doctor Who is in the year 2015. The 2015 `commit` is the `HEAD`. He wants to see some dinosaurs. He looks through the `git log` to find a `commit` with dinosaurs in it. He jumps back in time to a `commit` with dinosaurs. Now the `commit` with dinosaurs, is the `HEAD`.

- `git reset --hard commitNumber`, is like moving backwards in time to that commit. You have reset the `HEAD` of your branch to that commit.

- `git reset --soft commitNumber`, is like the `--hard` command, except you're not actually there. You can look at stuff and move stuff around, but the `HEAD` is still 2015. If that's confusing, make a `pull request` for a better explanation.

- `git reflog`, is a more robust `git log`. It shows all of your Git activity; `checkouts`, `pulls/pushes`, moving through time, etc... It looks something like... 

```
commitNumber HEAD{0}: commit: did some stuff
commitNumber HEAD{1}: commit: deleted some stuff I needed
commitNumber HEAD{2}: commit: gave a dinosaur a cool mustache
commitNumber HEAD{3}: checkout: moving from develop to feature/DinosaursOnSkateboards
commitNumber HEAD{4}: pull origin develop: Fast-forward
commitNumber HEAD{5}: checkout: moving from master to develop
```

`HEAD{0}` is the `tip` of your branch, the current `HEAD`.

If you delete some stuff that you needed, you can `git reflog` to find a spot before you deleted that stuff.

```
git reset --hard commitNumberWithDinosaurMustache
```
or

```
git reset --hard HEAD{2}
```

<br>
### More Time Lord Magic

```
git merge feature/someBranch
``` 
...`merges` some feature branch into the branch you're in. It's like when Doctor Who [regenerates][regenerates]. He's still Doctor Who, an alien with a tardis who travels through time... but with new features.

#### I have a bunch of commits on this branch and I don't want to fix the same merge conflict 20 times...
- `git rebase -i HEAD~the-number-of-commits-you-want-to-squash`, takes the number of commits after `HEAD~` and squashes them into 1 `commmit`.
- `git rebase --abort` or `git merge --abort`, when your rebase or merge goes wrong and you just want to get out of there.

<br>

## More Git Stuff
[The Simple Guide](http://rogerdudler.github.io/git-guide/)
<br>
[Git for Beginners](http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)
<br>
[Git Configuration](http://git-scm.com/book/en/v2/Customizing-Git-Git-Configuration)


[regenerates]: http://en.wikipedia.org/wiki/Regeneration_%28Doctor_Who%29