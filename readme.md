# git-sub
Opinionated porcelain for git-subtree

### Description

This git command stores remote information to use when calling `git subtree`

`git sub init example-subfolder git@example.com:repo.git master`  
`git sub add example-subfolder --squash`

### Installation

get `git-sub` into your path, or:
```
$ git clone https://github.com/Speedy6451/git-sub
# install -m 755 git-sub/git-sub /usr/bin
```

### Commands

`git sub init <prefix> <repository> <remote-ref>`  
Creates a `prefix/.subtree`[^1] file with remote information  
Required before calling any other `git sub` commands

`git sub <git-subtree-command> <prefix> <git-subtree-args>`  
  Runs `git subtree` with the specified prefix against the associated remote

[^1]: note: `.subtree` files will appear in the subtree.  
If that isn't something that you want, add `**/.subtree` to your `.gitignore`
