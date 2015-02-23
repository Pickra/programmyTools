## What's a merge conflict?
Count Chocula's changed line 20 of thisFile.js on his `local` branch and pushed it to the `remote` branch. You pulled his changes to your `local` branch. Git got mad and started talking about a `merge conflict`.

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
3. `git rebase --continue`, tells git you've fixed the `merge conflicts` and are ready to move on.

#### Once the merge is done, the terminal will ask you to put in a message about the merge.
- Now you're in `vim`, more on that in [terminal](../terminal/terminal.md).
- For now, you can just ignore it and `:q`, to get out.
- And the `merge conflict` is over!!

## I have a bunch of commits on this branch and I don't want to fix the the same merge conflict 20 times...
- `git rebase -i HEAD~the-number-of-commits-you-want-to-squash`, takes the number of commits after `HEAD~` and squashes them into 1 `commmit`.
- `git merge --abort`, when your rebase goes wrong and you just want to get out of there.

## How to be a time lord
- `git reset --soft commitNumber`
- `git reset --hard commitNumber`
- `git reflog`

## More Info
[The Simple Guide](http://rogerdudler.github.io/git-guide/)
<br>
[Git for beginners](http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)
<br>
[git branching model](http://nvie.com/posts/a-successful-git-branching-model/)