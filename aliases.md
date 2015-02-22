# ALIASES
Some commands can get really long. An alias is just shorthand for a command.

## Git Aliases

	git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit

That's way too long! Let's make an __alias__:

	git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
	
Now just `git lg` instead of `git log`, and your commits will look pretty. But your __alias__ can be anything, just change the __lg__ in __alias.lg__ to whatever you want.

## Terminal aliases

### Where do the aliases live?
- `.gitconfig` is located in the **home** directory; see [terminal](terminal/terminal.md).

`alias subl='open -a "Sublime Text 2"'`.
 <br>
Now... 

```
subl .
 ``` 
 ...opens the folder you're in, in sublime.


#### .zshrc:
`alias finder="open --reveal`
Now...

```
finder
```
... opens the folder you're in, in the finder window.