# github-notes
# Basics

	git init 
	git status  // see the untracked file ... 

	git add <file_name> // add a specific file to staging area 
	git add .  // add all the new and modified files to staging area 

	git commit -m "message" //  -m stand for message 
	git log  // all commits 

# unstage a file before commiting  

	git retore --staged <file_name> // bring the file back to unstage area from staging area 


# go back to a specific commit

	git log  // get all commit history 
	git reset <commit_id> // updates (after the commit) in unstaged area 


# stash a file ( like keeping in a clipboard )

	git add <file_name>
	git stash  // all files in the staging area will move to a stash area, [like a clipboard]

	git stash pop // bring the files back from the stash area to unstage area 

	git stash clear // delete the stash area [pop moves the files from stash to unstage,]


# working with github 

	git remote add origin <repo_link>
		[add tells you're adding an url]
		[origin is the name given for the url] can be anything but naming 'origin' is a convention [origin - files on your pc]

git remote -v // shows all the urls attached to the folder ... all added urls...


	git push origin main  
		[git push <which_url> <which_branch>]

# working with branches 
	git branch <branch_name> // create a new branch
	git checkout <branch_name> // move the head to a branch, all commits will be on this branch 

# merge commits 
	git merge <branch_name> // merge the commit with main branch

#working with existing repo on github 
	git clone <repo_url>	
	git remote add upstream <url> // url from where you have forqed this project is known as upstream by convention.

	-- make some changes -- 
	git branch <branch_name> // never commit on the main branch.
	git checkout <branch_name> 
	git add .
	git commit -m "M" // commited on the new branch 

# making a pull request [merge our changes in the main project, owner will review the code, if satisfied - merge the code]
	git push origin <branch_name> // you cannot push to upstream URL, only origin (origin is your version, you don't have access to upstream )
make a different branch for different feature...
a pull request is associated with a single branch...


---- Your changes will be available in the upstream project ---- 


# stay updated with upstream   
# WAY - 1
git checkout main 
git fetch --all --prune // fetch all the branches from the upstream, prune -  deleted branches will also be fetched 

git reset --hard upstream/main // reset the main of origin to the main of upstream ... move the head to the updated code ....

git push origin main // push to local origin 

# WAY 2 - alternative for the above one

git pull upstream main  
git push origin main 

# WAY 3 - 
click on fetch upstream on github local repo ...


# Squash Commit (merge multiple commits in one )
way 1 :  reset and commit again ... 
way 2 : pick and squash

git rebase -i <commit_id> // i means interactice environment, now change the 'pick' to 's' to squash these commits with the previos 'pick'

	-- esc [enter]
	-- : <message for the merged commit >

# Handle  Merge Conflict 

