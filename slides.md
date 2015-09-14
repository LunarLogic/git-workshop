## Alias
* alias s='git status'
* alias gl='git log --graph --pretty="format:%C(yellow)%h%Cblue%d%Creset %s %C(white) %an, %ar%Creset"'
* alias gco='git checkout'


# Files
* mkdir -p bookstore; cd bookstore
* echo "beautiful day" > diary
* echo "Chapter 1" > book
* echo "buy milk" > memory


## Working directory
* git init
* touch .gitignore
* git add .gitignore
* git commit -m "Initial commit"
* (git clone)


## Staging Area (index)
* git add diary
* git status
* git ls-files
* blob is a snapshot of the working directory
* blobs are stored in trees
* index is a file that stores info you want to commit
* echo "ate a banana" >> diary
* git status


## Staging files
* git add .
* git reset HEAD
* git add -u .


## Repository
* git commit -m "Added diary"
* commit is a blob that gets a name
* commit is a named snapshot of a repo
* commit is always pointing to a parent
* different parent == different commit (rebasing)
* git commit -a -m "add and commit"
* git commit --amend


## Remote
* lets set up remote repo on github
* git remote add origin git@github.com:rusilko/bookstore.git
* git push
* git push origin master
* git branch -u origin/master
* git pull


## Checkout
* git checkout HEAD
* git checkout HEAD~
* git checkout HEAD~2
* git chekcout ABC
* git checkout ABC -- diary
* git checkout [HEAD] -- diary
* git checkout -- .
* checkout copies a snapshot to working tree


## Reset
* git reset ABC [--mixed] (moves index to working tree)
* git reset ABC --hard (removes index and working tree)
* git reset ABC --soft (leaves index untouched)
* git reset HEAD diary
* git reset HEAD
* git clean -fd
* reset moves around pointers
* watch out for detached HEAD state


## Branches
* git branch oklahoma
* git checkout -b arizona
* gl
* git branch -d oklahoma
* Branch is just a pointer to commit


## Merging 1
* gco arizona
* echo "a day in arizona" >> diary
* echo "1st chapter" >> book
* git commit -am "arizona 1"
* gco master
* echo "a day at home" >> diary
* git commit -am "home 1"
* git merge arizona
* (resolve conflicts)
* git add
* git commit


## Merging 2
* make some changes
* git merge arizona
* git merge --abort
* git merge arizona -X ours/theirs

* merge-commit has 2 parents


## Merging 3
* back merging
* gco -b oklahoma
* echo "a day in oklahoma" >> diary
* git commit -am "oklahoma 1"
* gco master
* git merge oklahoma
* uups CONFLICTS, lets back out
* git merge --abort
* gco oklahoma
* git merge master
* resolve conflicts
* git add; git commit
* gco master
* git merge oklahoma
* nice and easy merge


## Rebase
* gco -b california
* echo "Chapter 2" >> book
* git commit -am "add chapter 2"
* echo "Chapter 3"  >> book
* git commit -am "add chapter 3"
* gco master
* echo "Foreword" >> book
* git commit -am "add foreword"
* echo "Index" >> book
* git commit -am "add index"
* gl -all
* gco california
* git rebase master
* gl -all


## Fetch & Pull
* cd ..
* git clone git@github.com:LunarLogic/git-workshop.git
* gco pulling


## Interactive rebase


