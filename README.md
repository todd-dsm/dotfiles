# dotfiles

The environmental controls that govern my technical eperience; I'm happy to share.

## Purpose

This will keep my configs in sync on multiple (work and personal) computers. I've been lazy about this for far too long and it's all out of control.

I'm using [GNU Stow] to manage local configs so they can be backed up to a central repository and be consistently available betwen ***n*** number of computers.

```shell
Work Laptop                    Personal Laptop
     ↓                              ↑
~/dotfiles/ ──→ Git Push ──→ GitHub ──→ Git Pull ──→ ~/dotfiles/
     ↓                              ↓
GNU Stow creates symlinks    GNU Stow creates symlinks
     ↓                              ↓
~/.zshrc ──→ Oh My Zsh ←──── ~/.zshrc
     ↓                              ↓
Terminal displays same environment on both machines (the ideal)
```

## The Stack

As in all technical pursuits, this is built in layers; start building from the bottom after peeling the cellophane.

```shell
┌───────────────────────────────────────────────────────────┐
│                  DOTFILE MANAGEMENT STACK                 │
├───────────────────────────────────────────────────────────┤
│ Layer 4: Git Repository (GitHub)                          │
│          • Version control & sync across machines         │
│          • Backup & collaboration                         │
├───────────────────────────────────────────────────────────┤
│ Layer 3: GNU Stow (Symlink Manager)                       │
│          • Creates symlinks: ~/dotfiles/* → ~/.config/*   │
│          • Package management (zsh/, git/, docker/, etc.) │
│          • Handles directory structures cleanly           │
├───────────────────────────────────────────────────────────┤
│ Layer 2: Oh My Zsh (Shell Framework)                      │
│          • Plugin system (ansible, docker, kubectl, etc.) │
│          • Themes & customizations ~/.oh-my-zsh/custom    │
│          • Command completion & aliases                   │
├───────────────────────────────────────────────────────────┤
│ Layer 1: macOS (BSD Unix base)                            │
│          • Default shell: zsh                             │
│          • GNU tools override BSD versions                │
│          • Terminal.app as interface                      │
└───────────────────────────────────────────────────────────┘
```

<!-- refs -->

[GNU Stow]:https://www.gnu.org/software/stow/
