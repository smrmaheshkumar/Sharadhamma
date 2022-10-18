## DevOps:
DevOps is the combination of cultural philosophies, practices and tools that increases an organization’s ability to deliver applications and services at high velocity: evolving and improving products at a faster pace than organizations using traditional software development and infrastructure management processes. 
This speed enables organizations to better serve their customers and compete more effectively in the market.

## Git:-
Git is a distributed version-control system for tracking changes in source code during software development. It is designed for coordinating work among programmers, but it can be used to track changes in any set of files. Its goals include speed, data integrity, and support for distributed, non-linear workflows. Wikipedia

## To Setup the configuration:

	$ git config --global user.name “smrmaheshkumar”

	$ git config --global user.email “smr.maheshkumar@gmail.com”

## To check the above status:

	$ git config --global --list

	Seeing Git’s user-based config file

	$ cat ~/.gitconfig

## Git Commands:

## Pushing to Github:
 	$ git init
 	$ git add filename or git add .
  	$ git commit -m "first commit'
 	$ git remote add origin https://
 	$ git push -u origin master
	$ git clone https://
	$ git ls-files 		# shows file on localrepo

## Git Logs:
	$ git log
	$ git log --oneline
	$ git log file1.txt
	$ git show
	$ git restore --staged index.html	# Bring back file from staging to working directory
	$ git rev-list -–all -–count 		# To see the commit counts

## Removing file from WD & Local repository:
	$ rm file.txt     	# Removes from working directory
	$ git rm about.html     # Remove files from local repo as well as working directory
	$ git ls-files		# To see the files in repository

If there is two readme file in local and github account. We will encounter an error. To resolve the issue please type the below command.

	$ git pull origin master –allow-unrelated-histories

## Git Conflict:

Changes in both local and repository makes conflict. To merge the files use the below command.

	$ git pull

Changes done in same file and changes of same file in remote repo. It will conflicts.
	
	$ git pull

It will show one conflict file which you edited. So remove the separator lines. Issue resolved.


## To Create a Branch:
	$ git branch –a              	# list all the branches in Git
	$ git branch production		# Create a branch production
	$ git checkout production       # Switches from master to production
 	$ git merge production          # Merges data from master to production
 	$ git push origin production    # Pushes data to production


## To delete the branch:
	$ git branch –d production		# Delete in local
	$ git branch –D production 		# Delete force
	$ git push origin production –delete	# Delete in remote repo

## Deleting files along with the commits:
	$ git reset bdhbcks –hard
	$ git push –f 				# Push forcefully
