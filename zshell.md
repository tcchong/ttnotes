# zsh

map ⌥ + ← / → to work in iTerm2 for Mac

```
# .zshrc
bindkey "[D" backward-word
bindkey "[C" forward-word
```



### zsh compinit on Mac

Issues

```
zsh compinit: insecure directories, run compaudit for list.
Ignore insecure directories and continue [y] or abort compinit [n]?
```

How to fix on OSX 10.11.X

```
$ cd /usr/local/share/
$ sudo chmod -R 755 zsh
$ sudo chown -R root:staff zsh
```

## Ref

[http://stackoverflow.com/questions/13762280/zsh-compinit-insecure-directories](http://stackoverflow.com/questions/13762280/zsh-compinit-insecure-directories)

