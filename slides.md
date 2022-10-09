---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss
---

# Just engouh Git

A quick tour of Git.

---

# Git fundamentals


- Working Area, Staging Area, Repository

   * Working Area (Untracked files)
   * Staging Area (Going to be committed)
   * Repo (All commits)

- Commits(CODE SNAPSHOT)

- References(POINTERS TO COMMITS)

    * branches
    * tags(fixed pointer)
    * HEAD(moves along)


- `.git` folder

---

<div class="bg-white">
  <img src="/lifecycle.png">
</div>

---


# What does git do

- git move 

- git rm

- git rm --cached



---

# Commit

- git commit --amend

- git commit -a

- git commit -a --amend


---


# Undo things

- git restore

- git restore --staged

- git reset 

- git reset HEAD --hard

- git revert

- git checkout

---

# Stash


- git stash save  "doning feature xxx"

- git stash --include-untracked

- git stash apply

- git stash  pop

- git stash list

---


# Merge Code

- merge code

- fast forward

- merge commit

- resolve confilict


---

# Alias (just bash alias)



```bash
alias gstash="git stash --include-untracked"

alias gst="git status"

alias ggpush="git push origin HEAD"

alias ga="git add"

alias gd="git diff"

alias gco="git checkout"
```


--- 

# Git Tools

- tig

- gh

- rg( git grep)

- git bisect

---

# Advanced Git

- rebase

- squash

- git reflog

- git cherry-pick


---

# Github

- remote

- fork

- upstream

- fetch, pull & push

- issues

- pull requets

- squash

- [octotree](https://chrome.google.com/webstore/detail/octotree-github-code-tree/bkhaagjahfmjljalopjnoealnfndnagc)

---


# Workflow

## Always fork

fork -> clone -> add remote -> fetch -> rebase -> push -> pull request

```
git remove add upstream
```


## Merge to develop branch for testing


feature branch -> merge to develop -> push

<div class="grid grid-cols-2 gap-2">

<div>
make a clean develop branch

```bash
git branch -D develop
git checkout master
git branch -u upstream/master
git pull
git checkout -b develop
git branch -u upstream/develop
```
</div>

<div>
make dev

```
dev:
		git push --set-upstream origin HEAD
		git checkout develop
		git pull
		git merge - --no-edit
		git push
		git checkout -
```
</div>
</div>
