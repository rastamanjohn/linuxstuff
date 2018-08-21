
## These are random snippets I use
### Aliases
These snippets should just be added to your `~/bashrc` or `~/bash_aliases`.
#### transfer
This will upload the specified file, and give you a download link. Very useful when building on Google Cloud.
```bash
transfer() {
    curl -w "\n" --progress-bar --upload-file $1 https://transfer.sh/$(basename $1) | tee
/dev/null;
}
alias transfer=transfer
```
To use it:
```bash
$ transfer path/to/file
```
This will output:
```bash
transfer.sh/gIBbeR15h/file
```
### nuke
This is just an alias for `rm -rf`, I find it more comfortable especially when using ssh from phone, no need to find the `-` in the symbols keyboard.
```bash
alias nuke='rm -rf'
```
### prompt
This is the prompt I use:
```bash
green="\[\033[01;32m\]"
white="\[\033[00m\]"
blue="\[\033[01;34m\]"
export PS1="${debian_chroot:+($debian_chroot)}$green\u@\h$white:$blue\w$white\$(__git_ps1) \$ "
```
The prompt will look like:
```bash
user@host:~/working/directory (git_branch when availble) $
```

