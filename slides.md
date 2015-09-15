Setup: Aliases

* alias s='git status'
* alias gl='git log --graph --pretty="format:%C(yellow)%h%Cblue%d%Creset %s %C(white) %an, %ar%Creset"'
* alias gco='git checkout'


Setup: Files

* mkdir -p bookstore; cd bookstore
* echo "beautiful day" > diary
* echo "Chapter 1" > book
* echo "buy milk" > memory


Working directory

* git init
* git ls-files
* touch readme.md
* git add readme.md
* git commit -m "Initial commit"
* git ls-files


Staging Area (index)

* git add diary
* blob is created
* git status
* index is a file that stores info
  about you want to commit
* echo "ate a banana" >> diary
* git status
* git diff --color
* git diff --staged --color
* alias d="git diff -M --color"
* alias gds="git diff --staged --color"


Local Repository

* git commit -m "Added diary"
* commit is a blob/tree which gets a name
* commit is a named snapshot of a repo
* commit always has a parent
* different parent == different commit (rebasing)
* git commit -a -m "add and commit"
* git commit --amend


Remote Repository

* git push
* lets set up remote repo on github
* git remote add origin git@github.com:rusilko/bookstore.git
* git push
* git push origin master
* git branch -u origin/master
* git pull


Staging files

* git add . (all)
* git reset HEAD
* git add -u . (only tracked)
* git add -A (all with deletes)


Checkout

* git checkout HEAD
* git checkout HEAD~
* git checkout HEAD~2
* git chekcout 123abc
* echo "ate a banana" >> diary
* git checkout [HEAD] -- diary
* git checkout ABC -- diary
* checkout copies a snapshot(commit)
  to your working directory
* git checkout -- .


Reset

* git reset ABC --mixed (moves index to working tree)
* git reset HEAD
* git reset HEAD diary

* git reset ABC --hard  (removes index)
* git clean -fd

* git reset ABC --soft  (leaves index untouched)
* reset moves around pointers
* watch out for detached HEAD state


Stash

* git stash
* git stash pop
* git stash drop


Branches

* git branch oklahoma
* git checkout -b arizona
* gl
* git branch -d oklahoma
* Branch is just a pointer to commit


Merging 1

* gco arizona
* echo "a day in arizona" >> diary
* echo "Chapter X" >> book
* git commit -am "arizona 1"
* gco master
* echo "a day at home" >> diary
* git commit -am "home 1"
* gl --all
* git merge arizona
* (resolve conflicts)
* git add
* git commit


Merging 2

* make some changes
* git merge arizona
* git merge --abort
* git merge arizona -X ours/theirs

* merge-commit has 2 parents


Merging 3: Back merging


* gco -b oklahoma
* echo "a day in oklahoma" >> diary
* git commit -am "oklahoma 1"
* gco master
* echo "a day in school" >> diary
* git commit -am "shool day"
* git merge oklahoma
* uups CONFLICTS, lets back out
* git merge --abort
* gco oklahoma
* git merge master
* resolve conflicts
* git add; git commit
* gco master
* git merge oklahoma
* nice and easy merge (fast forward)


Rebase

* gco -b california
* echo "Chapter 4" >> book
* git commit -am "add chapter 4"
* echo "Chapter 5"  >> book
* git commit -am "add chapter 5"
* git push
* gco master
* echo "Foreword" >> book
* git commit -am "add foreword"
* echo "Index" >> book
* git commit -am "add index"
* gl -all
* gco california
* git rebase master
* gl -all
* git push


Interactive rebase

* gco master
* git rebase -i HEAD~4
...

Fetch & Merge

* cd ..
* git clone git@github.com:LunarLogic/git-workshop.git
* (I make some changes, push)
* make some changes to diary.md
* git fetch origin
* git merge origin/master


Fetch && Rebase

* (I make some changes, push)
* make some changes
* git fetch origin
* git rebase origin/master


Pull

* pull = fetch + merge
* git pull --rebase = fetch + rebase
* git pull --rebase --ff-only (will back out in case of conflicts)


Workflow

* gco -b my-feature-name
* work on your branch:
* frequent small commits
* diff before commiting to check
* use amend if needed
* concise & meaningful commit messages
* when work is done, check if any clean up is needed
* use interactive rebase to squash/remove/edit commits
* push to remote
* open a "pull request" on github (as in "I want you to pull in my changes")
* if merge to master is not trivial: back-merge or rebase your branch
* after rebase push with force (only your branch)
* NEVER force push master/production or any branch which is shared with others


Dealing with fuckups
* if on your local branch: reset && clean && start over
* if on master/production: git revert
* create helper branches to test your ideas first


Next

* good commit messages:
http://dev.solita.fi/2013/07/04/whats-in-a-good-commit.html
* git-fu by Przemek
* git add -p
* git cherry-pick
* hooks
* aliases
* global gitignore
* assume-unchanged


Thank you

Happy gitting

