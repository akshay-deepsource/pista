# pista

> a simple bash prompt for programmers 

### installation
```shell
$ cargo install pista
```

cargo is rust's package manager. if you dont have cargo installed, head over to
http://rustup.rs and follow the instructions.  
make sure to add `$HOME/.cargo/bin` to your `$PATH`!


once you have installed `pista`, set your `PS1` to use it!
```shell
PS1="$(pista)"    # regular variant
PS1="$(pista -m)" # minimal variant
```


`pista` handles prompt modifications when you enter virtual environments.
make sure to disable `virtualenv`'s changes.
```shell
export VIRTUAL_ENV_DISABLE_PROMPT=1
```

thats it! read on if you aren't happy with the defaults.

### configuration

this is the default configuration. drop this in your `.bashrc` to get started.
remember to `source ~/.bashrc` to observe the changes!

```
# prompt string to display, for regular users
export PROMPT_CHAR="$"
export PROMPT_CHAR_COLOR="green"

# prompt string to display, for the root user
export PROMPT_CHAR_ROOT="#"
export PROMPT_CHAR_ROOT_COLOR="red"

# if SHORTEN_CWD is set to 1, `/home/nerdypepper/code` is shortened to
# `/h/n/code`
export SHORTEN_CWD=1
export CWD_COLOR="white"

# if EXPAND_TILDE is set to 0, `/home/nerdypepper` is shortened to `~`
export EXPAND_TILDE=0

# there are three possible states for a git repo
# - unstaged (working tree has been modified) 
# - staged (staging area has been modified)
# - clean (all staged changes have committed)

# symbol to represent clean repo state
export GIT_CLEAN="·"
export GIT_CLEAN_COLOR="green"

# symbol to represent unstaged repo state
export GIT_WT_MODIFIED="×"
export GIT_WT_MODIFIED_COLOR="red"

# symbol to represent staged repo state
export GIT_INDEX_MODIFIED="±"
export GIT_INDEX_MODIFIED_COLOR="yellow"

# if HEAD ref peels to branch
export BRANCH_COLOR="green"

# if HEAD ref peels to a commit (detached state)
export COMMIT_COLOR="green"
```

all 16 colors are available:
```
black
red
green
yellow
blue
magenta (or purple)
cyan
white

bright black
bright red
bright green
bright yellow
bright blue
bright magenta (or purple)
bright cyan
bright white
```