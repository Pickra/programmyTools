
// TODO: make a repo with this readme, a gitignore, spilt content into seperate .MDs

# what you need
- [Terminal](#terminal)
- [Git](#git)
- [Github]
- [Sublime](#sublime)

## Terminal <a name="terminal">*</a>
### Windows

### Mac
#### Iterm:

Move through the file system.
`cd name of child folder`, moves you down.
`cd ..`, moves you up.

__Let's make an some aliases__ 

 `alias subl='open -a "Sublime Text 2"'`.<br>
Now `subl . `, opens the folder you're in, in sublime.


#### .zshrc: 
`alias finder="open --reveal` opens the folder you're in, in the finder window: 
Now `finder`
	
shortcuts:

	cmd + return -> Fullscreen mode
	cmd + D -> Split panes vertically
	cmd + shift + D -> Split panes horizontally
	cmd + ~ -> Switch between fullscreen iterm windows


## Git <a name="git">*</a>
### Installation
#### Windows
[installation options](http://git-scm.com/book/en/v2/Getting-Started-Installing-Git#Installing-on-Windows)

#### Mac
##### homebrew
It's easy. __Copy__...

```
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```
... __in your terminal.__

then: `brew install git`

More about  [Homebrew](http://brew.sh/)

### Git It
Git is like a bush. `master` is dirt. Everything comes out of the dirt and eventually goes back to it. `develop` is the trunk that all the branches grow from. When you `cut a branch`, it's like you made a clone of the bush. The new branch has all of the same properties of the bush, **when** you cut it. A `feature/` branch grows out of the `develop` trunk, they have new stuff. A `release/` branch is a `feature/` you gave to your friend. You make a `hotfix/` branch when your friend brings his `feature/` back because it has bugs on it. 

##### Get  comfortable using words like:
- __Local__ = on your computer. Ex: That's a *local* branch.
- __Remote__ = on Github, or some other server. Ex: That's on the *remote* branch.
- __Repo__ = The repository that holds all the files. Ex: That's on my *local repo*. I put it on the *remote repo*
- __Root__ = The folder that holds all the files. Ex: I'm in  the *root* of the *repo*. Go to the *root* of your computer. 

### Configure Git
- Add a file named `.gitignore` to the root of your working copy. 

##### How do I get all the things off of Github and onto my computer?
- `git clone https://github.com/projectName.git`

##### Where are the branches?
- `git branch`,  show the branches on your computer.
- `git branch -a`, show the branches on the *repo*.
- `git branch -D someBranch`, deletes some branch
- `git fetch origin` or `git fetch origin --all` pulls all the branches, from Github, onto your `local`. 

##### How do I get into a branch?
- `git checkout someBranch`, move into some branch on your computer.
- `git checkout -b someOtherBranch`, make a new branch and move into it.

##### I changed some stuff, now what?
-  `git status`, shows the files you changed.
- `git add`,  gets files that you changed, ready to go.
- `git commit -m "I did stuff!!" `, puts your changed files in a box with a message that says what you did to the files.
- `git log`, shows you all the commits. Each commit has a message, a number, who wrote it, and when it was written. `q`, to get out of `git log`.
- `git log -p`, shows the lines in the commit that changed. 

#### ALIASES
Some of these git commands can get really long. An alias is just shorthand for a command. 

	git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

That's way too long! Let's make an __alias__:

	git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
	
Now just `git lg` instead of `git log`, and your commits will look pretty. But your __alias__ can be anything, just change the __lg__ in __alias.lg__ to whatever you want.

##### I forgot to put something in my last commit, now what?
- `git commit --amend --no-edit`, throw a change in the last commit, and don't change the message.
- `git commit --amend -m "What I meant to say was..."`, throw a change in the last  commit, and change the message.

##### Once your files are committed to going, they need a little push...
`git push origin remoteBranchName`

The 3rd guy in line is where you're pushing to.`origin` is the original *repo* on Github that your branch belongs to. But the 3rd guy could be someone else's *repo* too.

##### How do I get Count Chocula's branch changes, onto my *local*  branch?
`git pull origin branchName`, *merges* Count Chocula's changes onto your branch

##### What's a merge conflict?

You pulled some stuff from Count Chocula's copy of someBranch. Git got mad and started talking about a merge conflict.

Count Chocula's changed line 20 of thisFile.js, and pushed it to the *remote* branch. You pulled his changes to your *local* branch.

Count Chocula's line 20:

	I vant to eat your cereal!

Your line 20:

	I like dragons

You have a __merge conflict__ because Count Chocula's line 20 is different than yours. 

thisFile.js now has 2 copies of line 20. Do a `git status` to see the files that are in conflict and open the file... 

	<<<<<<< HEAD
	
	I vant to eat your cereal!
	=======
	I like dragons
	>>>>>>> commit #
	
... delete the extra stuff that Git throws in there, and the line that you don't want.

When you're done with all your *merge conflicts*:

1. `git status`
2. `git add` the files that changed.
3. `git rebase --continue`, tells git you're done with the merge.

Once the merge is done, your terminal will ask you to put in a message about the merge, but you can ignore it and just `:q!`, to get out. And the *merge conflict* is over!!

##### I have a bunch of commits on this branch and I don't want to fix the the same merge conflict 20 times...
- `git rebase -i HEAD~the-number-of-commits-you-want-to-squash-into-one-commit`
-  `git merge --abort`, when your rebase goes wrong and you just want to get out of there.

##### How to be a time lord
- `git reset --soft commitNumber`
- `git reset --hard commitNumber`
- `git reflog`

[The Simple Guide](http://rogerdudler.github.io/git-guide/)
<br><br>
[Git for beginners](http://stackoverflow.com/questions/315911/git-for-beginners-the-definitive-practical-guide)



## Sublime <a name="sublime">*</a>

shortcuts:

- cmd + option + arrow keys =  Moves line(s) around.
- cmd + D =  selects a word where the cursor is, repeat to select multiple instances.
- cmd + shift + D = Duplicates the current line.
- cmd + P = Opens a fuzzy search
- cmd + shift + P = Opens the package manager
- cmd + f = Search current file for a word or phrase
- cmd + shift + f = Search entire project for a word or phrase


