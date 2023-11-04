# GIT Notes & commands:

1. initialise a folder to git repo
	```git
	$ git init
	```


2. check hidden .git file in a folder
	```git
	$ ls -a
	```


3. now we need to check if your file is added in staging area where you can choose specific version to download later
- so to check for files if they are untracked or not
	```git
	$ git status
	```


4. to add the untracked files in staging area
	```git
	$ git add FILE_NAME
	```
- to add all files to staging area use 
	```git
	$ git add .
	```


- to undo the added files from staging area back to untrack files
	```git
	$git rm --cached -r .
	```


5. check again for files added in staging or not (files will be highlighted in green color ) 
which means it is added in staging area and ready to be COMMITTED.
	```git
	$ git status
	```


6. to commit a file and save it with some message 
	```git
	$ git commit -m "Complete Chapter 1"
	```	
- Always put message in present tense as this convention is followed


7. check the committed logs(ie. commit(unique hash no for each commit), name of author, committed log time) using following command
	```git
	$  git log
	```
- The hash code is also present with each commit which uniquely seperates the commits. 


8. Now you mistakenly make changes in chapter3.txt file and saved the changes and you want to check what differences in code was save then use below command
	```git
	$ git diff chapter3.txt
	```
- It will show the changes previously added and now made.


9. To revert the changes made in chapter3.txt file use below command
	```git
	$git checkout chapter3.txt 
	```


10. To add all your data into the remote repository on github. 
- first create a remote repository on github and copy the path of https and paste it below
	```git
	$ git remote add origin https://github.com/shindetejas08/story.git
	```
- origin is the repository of my github account, always use word origin because it is used as convention.
- After entering this command our remote repository is created and ready to push the code into it


11. Now push your code into the github repository
	```git
	$ git push -u origin master
	```

12. Cloning a git repository
	```git
	$git clone github_link
	```
13. If you want push new code/file into existing git repository then you need to run below commands firt and then push else you will get following error:
    	```git
    To https://github.com/shindetejas08/react-projects
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/shindetejas08/react-projects'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
    	```
    - use following command to solve above issue
	```git
 	$ git pull --rebase origin master
 	$ git push origin master
	 ```
14. Using Git Token:
    - As of Aug 2021 git stopped using password authentication and started token system. Follow below steps to use token
    1. go to profile > settings > developer settings > personal access tokens > tokens (classic) > Generate New Token > Select All options and set duration.
    2. Copy the generated token and save it somewhere.
    3. Now After running command  ```git add.``` run the below command after adding all the values in it
    ```git
    git remote set-url origin https://<token>@github.com/<username>/<repo>
    ```
    4. Now you are done. Commit and push the changes. END

# MAIN vs MASTER BRANCH:
- This is the main branch of commits or save points and it is sequential.And this is where your main progress is saved or committed.  

- GITHUB repository also called as REMOTE Repository. It is where all our code is hosted

- GITIGNORE: Prevent commiting some sensitive files data into the local and remote repositories
-Steps:
	1. make ".gitignore" named file in the required project folder
	2. add the file names one by one one on a new line
	3. if you want all files to be ignored of specific extension then use *.extensionName eg *.txt(all .txt files will be ignored)
- You can add comments in .gitignore file using #
- standard gitignore file template for various languages is available on https://github/gitignore.com
- branching and merging:
- to create a new branch which can be used parallely on the remote repository 
	```git
	$  git branch branch_name
	```
- to check the current branch, here you will see which branch you are currently on which will be denoted using *
	```git
	$ git branch
	```

- to change the current branch 
	```git
	$ git chechout branch_name
	```

# Merging branches:
- after you make changes to the alternate branch and you want to merge that changes to the master branch then use foll code
- First change your branch to master
	```git
	$ git checkout master
 	$ git merge branch_name		eg. $ git merge alien-plot
	```
- To check the commits on GITHUB change the view from main->master

- to check the insights of branches, goto insights->network there you will see the master branch and alternate branch







