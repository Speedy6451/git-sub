# git-sub
Opinionated porcelain for git-subtree

### Description

This git command stores remote information to use when calling `git subtree`

`git sub init --parent example-subfolder git@example.com:repo.git master`  
`git sub add example-subfolder --squash`

### Installation

get `git-sub` into your path, or:
```
$ git clone https://github.com/Speedy6451/git-sub
# install -m 755 git-sub/git-sub /usr/bin
```

### Commands

`git sub init [--parent|-p] <prefix> <repository> <remote-ref>`  
Creates a `prefix/.subtree`[^1] file with remote information  
Required before calling any other `git sub` commands  
The `--parent` option will move the `.subtree` file into the parent directory

`git sub <git-subtree-command> <prefix> <git-subtree-args>`  
  Runs `git subtree` with the specified prefix against the associated remote

[^1]: note: `.subtree` files will appear in the subtree by default  
If that isn't your desired behavior, add `**/.subtree*` to your `.gitignore` if you don't want to track remotes, or pass `--parent` to put the metadata in the containing folder
