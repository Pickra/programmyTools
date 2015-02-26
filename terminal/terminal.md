# Terminal

## Where is it?
#### Windows
1. Go [here](http://git-scm.com/).
2. Download and use the setup wizard.
3. On the 3rd screen, select `Get Bash Here` and the `On The Desktop` icon.
4. On the 4th screen, select `Use Git ftom the Git Bash Only`.
5. Select the 2nd option.
6. There should be a desktop icon, click it.

#### Mac
1. Hold the `command` button ( next to the space bar ) and tap the space bar. 
2. A search bar will pop up.
3. Type in `terminal`.
4. There it is.


## Geek Speak
- `file system`             = is how you access all your files and `directories`; like the `finder` on a mac or the search box on the Start menu in Windows.
- `directory`               = is a folder in your `file system`.
- `parent`                  = is the first `directory`. The `directory` that holds all the other `directories` of the group, project, or computer.
- `child`                   = is a `directory` inside of a `parent`.
- `root`                    = is the `parent directory`. Where all of the `child directories` live on your computer.
- `path`                    = is the location you're at in the `file system`. Ex: `root`/`child`/`child`.
- `cli` or `command line`   = are commands that you use in the [terminal](../terminal/terminal.md) to maneuver through the `file system`.
- `vim` or `vi`             = a program in your terminal, where you run commands to interact with Git.

### I got the terminal open, now what?

Let's make a place for your stuff to live...

...`pwd` = shows you where you are in the `file system`; what `path` you're on.

You're in the home `directory`. Let's do a...

...`mkdir` = make a directory.

```
mkdir apps
```

Now lets..

- `cd` = change (the) `directory`. Running just `cd` will move you to the `~`, no matter where you are.
- `cd childDirectory` = `cd` into a `child directory`.

```
cd apps
```

### Time to get [Git](https://github.com/naviance/programmyTools/blob/master/git/git.md)

## Using the `cli`
- `/` = is the `root directory`.
- `~` = is the `home directory`. The `parent directory` where <span style="color: green;">your</span> stuff lives.
- `cd ..` = `cd` up to the `parent directory`.
- `ls` = lists all the regular files in the `directory` you're in.
- `ls -la` = lists the hidden files + regular files, in the `directory` you're in.
- [command line cheat sheet](http://linuxcommand.org/lc3_lts0010.php)

## vim
- `:q`  = quit wherever you are. If you needed to save stuff, too bad.
- `:q!` = Whatever you were doing, never happened.
- `:wq` = write (save) and quit.
- [cats who code](http://www.catswhocode.com/blog/100-vim-commands-every-programmer-should-know)
- [vim cheat sheet](http://www.fprintf.net/vimCheatSheet.html)

## Fun Stuff
### iTerm
- install

### ZSH
- install

### Putty