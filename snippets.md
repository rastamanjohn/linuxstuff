
## These are random snippets I use:
These snippets should just be added to your `~/.bashrc` or `~/.bash_aliases`.
You can also do the following, replacing `alias_name` and `alias_definition` accordingly, you can also change `~/.bashrc` to another file (like `~/.bash_aliases`):
```bash
echo "alias alias_name=alias_definition" >> ~/.bashrc && . ~/.bashrc
```
#### transfer
This will upload the specified file, and give you a download link. Very useful when building on Google Cloud. You can find more info on [their website](http://transfer.sh).
```bash
transfer() {
    curl -w "\n" --progress-bar --upload-file $1 https://transfer.sh/$(basename $1) | tee
/dev/null;
}
```
To use it:
```bash
$ transfer path/to/file
```
This will output:
```bash
transfer.sh/gIBbeR15h/file
```
#### nuke
This is just an alias for `rm -rf`, I find it more comfortable especially when using ssh from phone, no need to find the `-` in the symbols keyboard. Also, it makes bring-ups more fun.
```bash
alias nuke='rm -rf'
```
#### more shortcuts:
##### Shortcuts for git:
This allows to just type `commit more fixes in readme.md`
```bash
commit() {
    git commit -m "$*";
}
```
```bash
alias push="git push -u origin master"
```
```bash
alias log="git log --oneline"
```
This is a combination of `cd` and `ls`:
```bash
cs() {
    cd "$@" && ls;
}
```
This is useful to go back to the ROMs source root:
```bash
ad() {
    cd '~/android/$@';
}
```
For example, this is like `cd ~/android/lineage`, but shorter and with less symbols:
```bash
$ ad lineage
```
You can also do `ad lineage/framework/base` etc., tho i don't know how to make autocomplete work correctly.



#### prompt
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

