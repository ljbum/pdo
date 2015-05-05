#Zsh
* Set user@host path with color
* If you want, you can delete %n@%m to make short prompt
```
autoload -U colors && colors
PS1="%{$fg[red]%}%n%{$reset_color%}@%{$fg[blue]%}%m %{$fg[yellow]%}%~ %{$reset_color%}%% "
```
* My setting on .zshrc
```
autoload -U colors && colors
export PS1="%{$fg[blue]%}%. %{$reset_color%}%% "
```
* Ref: [zsh prompt](http://www.nparikh.org/unix/prompt.php)
