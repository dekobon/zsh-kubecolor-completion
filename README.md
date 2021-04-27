# dekobon/zsh-kubecolor-completion
Rich [zsh](http://zsh.org) completion for the [kubecolor](https://github.com/dty1er/kubecolor) command.

This is a not-well maintained fork of [nnao45/zsh-kubectl-completion](https://github.com/nnao45/zsh-kubectl-completion)
that provides autocompletions for the [kubecolor](https://github.com/dty1er/kubecolor) command.


# Version
| kubecolor | zsh-kubecolor-completion |
|:---:|:---:|
| v1.12.2 | v0.1.6 |
| v0.13.5 | v0.1.7 |
| v0.13.5 | v0.1.8 |
| v0.13.5 | v0.1.9 |
| v0.13.5 | v0.1.10 |
| v0.13.5 | v0.1.11 |
| v0.13.5 | v0.1.12 |

# Install

## zplug
write this in your `.zshrc`.
```bash
zplug "dekobon/zsh-kubecolor-completion"
```

## Prezto
```bash
$ curl -fLo ~/.zprezto/modules/completion/external/src/_kubecolor \
  https://raw.githubusercontent.com/dekobon/zsh-kubecolor-completion/master/_kubecolor 
$ exec zsh
```

## Manual
for example, you set `~/.zsh/completion`, 
```bash
$ curl -fLo ~/.zsh/completion_kubecolor \ 
  https://raw.githubusercontent.com/dekobon/zsh-kubecolor-completion/master/_kubecolor
$ exec zsh
```

# Resource Filitling
This completion of kubecolor has several flags corresponding to context override, for example, specify the namespace of the operation target --namespace flag should be set before entering resource name such as pod name So we will use the target namespace resource as a candidate for completion. The options supported for override are as follows.
- --kubeconfig
- --cluster
- --user
- --context
- --namespace
- --server

## And...
If you want to complete list is "non grouped", you set additional attr.  
(I don't like grouped complete list when same word comment.)

By default,
```bash
$ kubecolor describe namespaces <TAB>
namespace
kkk  jjj  iii  hhh  ggg  fff  eee  ddd  ccc  bbb  aaa
vvv  uuu  ttt  sss  rrr  qqq  ppp  ooo  nnn  mmm  lll
zzz  yyy  xxx  www                                     -- Active
```

Add this setting in your `.zshrc`,
```bash
zstyle ':completion:*:*:kubecolor:*' list-grouped false
```

Show this😍
```bash
$ kubecolor describe namespaces <TAB>
namespace
aaa  -- Active
bbb  -- Active
ccc  -- Active
ddd  -- Active
eee  -- Active
fff  -- Active
ggg  -- Active
hhh  -- Active
iii  -- Active
jjj  -- Active
kkk  -- Active
lll  -- Active
mmm  -- Active
nnn  -- Active
ooo  -- Active
ppp  -- Active
qqq  -- Active
rrr  -- Active
sss  -- Active
ttt  -- Active
uuu  -- Active
vvv  -- Active
www  -- Active
xxx  -- Active
yyy  -- Active
zzz  -- Active
```
