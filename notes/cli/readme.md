# Command-Line Notes

What I learned in commandline

## Setting up `$PATH` (environment) variables

1. Find your rc file. `.bashrc` for bash, `.zshrc` for zsh. Open with your editor.

2. Put your environment variables in the `export PATH`. Local path is `$HOME`

```zsh
PATH="$HOME/Library/Python/3.7/bin:$PATH"
PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
export PATH
```

## Restarting apache server on Mac

`sudo killall httpd` and `sudo apachectl start`
