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

# Just Enough Git

A quick tour of Git.

---

# Git Fundamentals


- Working Area, Staging Area, Repository

   * Working Area (untracked files)
   * Staging Area (going to be committed)
   * Repo (all commits)

- Commits(code snapshot)

   Mental Model(key value store)

- References(pointers to commits)

    * Branches
    * Tags(fixed pointer)
    * HEAD(moves along)



---

<div class="bg-white">
  <img src="/lifecycle.png">
</div>

---


# What does git do under the hood?

- git move file_a file_b 

<v-click>

Make a clean diff

</v-click>

<v-click>

## What's the difference?

- git rm

- git rm --cached (keep file, when to use?)

</v-click>


---

# Commit

- git commit --amend (new commit)

- git commit -a



---


# Undo things

- git restore

- git restore --staged

- git reset (move HEAD) 
   - --mixed(default)
   - --soft
   - --hard

- git reset HEAD --hard

- git revert (rollback)


---

# Stash (The one I love the most)


- git stash

- git stash --include-untracked

- git stash save  "doning feature xxx"

- git stash apply

- git stash  pop

- git stash list

---


# Merge Code


- Fast forward

- Merge commit

- Resolve conflict(enjoy the process)


---

# Useful Alias (just bash alias)


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

  * gh pr create -w
  * gh repo fork

- rg( git grep -n)

- git bisect

---

# More Git

- rebase (different from merge)

- squash (using rebase -i)

- git reflog (recover from mistakes)

- git cherry-pick 


---

# Github

- remote

- fork

- upstream

- fetch, pull & push

- pull requests

- [octotree](https://chrome.google.com/webstore/detail/octotree-github-code-tree/bkhaagjahfmjljalopjnoealnfndnagc)

---


# Workflow

## Always fork

fork -> clone -> add remote -> fetch -> rebase -> push -> pull request

<v-click>

### Setup a fork


```bash
gh repo fork <repo> # do everything for you
```

</v-click>

<br>

<v-click>

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

</v-click>


---

# Co-work on Other's Branch

```bash
git remote add jun git@github.com:XiaoJunMi/cloudservice.git
git fetch jun
git checkout -b branch_from_jun # auto set tracking branch
git push # never -f to other's branch
```

---

# Questions?
