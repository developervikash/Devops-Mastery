GITHUB ADVANCE ->>>>>>

git - git is a version control system that allows you to keep a version track record and history for your code and files
as we covered now till now.

git init - that initialises a repo.

git status - that checks the status of the repo. 
git add - to add any file to version control; system.
 git commit - that saves your files inside the VSC. 

PULL REQUEST —

It’s a way of merging.

A 

pull request is basically merging branches. Let us have two branches; one is *master branch* and another is development branch. So after completing work, we have to merge the development branch into *master / main branch 

in professional way -

A pull request is a request to merge code from one branch into another branch on a remote repo , usually after reviewing the changes.

Pull requests -> reviewers -> check code -> push code.

REVERT AND RESEARCH
 In case of any wrong push

let we have worked on the development branch and we did commit but by mistake I did some bad commit here or code broke and some type of impact. Then in this case we use revert - undo.

commit -1 right
commit -2 right 
commit -3 wrong
commit  -4 wrong

So in case commit 1 is correct, commit 3 is wrong commit. 2 is correct 

in this case we take id that wrong commit by using [git log —oneline]
id is similar like (3d145v)
it will be conflict. 

CONFLICT -> whenever the same line has different values it is called a conflict.
OR Two commits trying  to prove to each commit wrong.

FIXING CONFLICT ->

git status - both modified

open that file that we have performed wrong changes. 
<<<<<<<
fine 
      not fine 
fine 
      not fine 
           >>>>>>>>>>>
Then correct file manually .

Save file - (git status) - (git add “file-name”) - (git revert —continue) - (git log —oneline).


RESET ->>  It means take that commit everything after that commit will be wiped off from your history but this is risky 😂

revert —> created history
reset —> wiped off history (always avoid it )
git reset “file-name” 

There are three types of reset.
 
1️⃣ Soft reset -> whatever will be the commit id everything after this command will be unstaged / will untrack things + stage
2️⃣ Mixed reset -> untracked
3️⃣ Hard reset -> everything after this will be deleted 


STASHING ->>>>

When you want to change branch but there’s something that is not committed, it is not allowed to change branch, then we use git stash

Stash is a process of saving it to the place where it gets saved, the stash

OR  you don’t want to commit something but you want to save it .

CHERRY-PICKING ->>>>>

When we are working on a second branch and want to merge with the master branch, then all the error commits are also going to be there in the master branch. In this case, we will use cherry-picking

Cherry picking  is only picking corrected work
(git cherry-pick) - Apply the changes introduced by some existing commits
git cherry-pick “a7c3b9e” using theri id

GIT REBASE ->> 
 Do take all of your commit dev branch and master branch and arrange them in a one sequence 
git rebase dev

It will create a linear history, this all got added with master and linear history will maintain. 

Levelling Up My Git & GitHub Skills with My Mentor Shubham Londhe (TrainWithShubham) 🚀





