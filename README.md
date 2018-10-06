# Github how-to-use documentation for Beginners


## Setting up a Windows Environment
- Goto https://git-scm.com/ and install git for windows
- Use special command line interface "Git Bash" which is easy to work with Git
- First we need to configure git on our local machine
  - git config --global user.name "TMK Computers"
  - git config --global user.email "computers.tmk@gmail.com"
  - git config core.editor "notepad++ -multiInst -nosession"
  - git config --edit --global

## Creating git repository on local machine
- To create a new repository on local machine run below commands
  - git init DemoApp
  - cd DemoApp
  - ls -la
- You can check the status of repository with command
  - git status
- Create a new file README.md
  - notepad++ README.md
- Add some content in README.md. I have added "# Hello World". Save the file.
- Then check status again which shows status that we have an **untracked file**
  - git status
- Track the changes in README.md file with command
  - git add README.md
- If we have multiple new and edited files then we can track them all with a single command
  - git add .
- Then check status again which shows status that we have a **staged file**
  - git status
- Now we can commit the file with readable message
  - git commit -m "Intitial Commit"
  
## Creating git repository on GitHub.com
- We can create a new repository on github.com with clicking on new **New Repository** button
- Choose a unique name within your account for new repository and add description also
- you have 3 options for working with newly created repository
  ### 1. create a new repository on the command line
      - echo "# sample-repo" >> README.md
      - git init
      - git add README.md
      - git commit -m "first commit"
      - git remote add origin https://github.com/tmk-computers/sample-repo.git
      - git push -u origin master
      
  ### 2. push an existing repository from the command line
      - git remote add origin https://github.com/tmk-computers/sample-repo.git
      - git push -u origin master
      
  ### 3. import code from another repository
  
- We can check if local repository is connected with any remote repository
  - git remote -v
  
## Using SSH to Connect with GitHub
- Command to generate ssh keys
  - ssh-keygen -t rsa -b 4096
- Goto the directory where key files are generated. Copy contents of file *id_rsa.pub* which public key file.
- Goto the github.com account, Select *Settings* -> *SSH and GPG keys* -> *New SSH key* page
- Add title, paste copied public key and click on *Add SSH key* button.
- Next you can test the SSH connection with command
  - ssh -T git@github.com
  
## Fetching and Pulling from remote repository
- With below command you can get the changes to local git database. But these changes are not affected to the project directory of local repository
  - git fetch
- To affect all the fetched changes you can run command
  - git merge
- fetch and merge all the changes can also be done with single command
  - git pull
- If there is only change present in remote repository then **git pull** does fast forword merge.
- But if changes are done at both local and remote repositories then based on **conflict** present or not git pull takes separate actions.
- If there is no conflict then git pull creates automatic merge and then performs  a new commit for merge usually called as “merge commit”
- If there is conflict then user has to do manual merge with mergetool
  - git mergetool --tool=emerge

## Archiving Repositories
- You can mark non-active repositories as read-only with github feature **Archiving Repository**
- It adds a warning message at top as "This repository has been archived by the owner. It is now read-only."
- You cannot open an issue or pull requests - because of the repository is read-only.

## Branching, Merging, and Pull Requests
- list all the branches present with command which also highlights current branch we are working now
  - git branch
- create a new branch of name **dev** with command
  - git branch dev
- switch to the newly created branch using
  - git checkout dev
- create a new branch and switch to it can be done by using single command
  - git checkout -b “new-branch”
- make some changes to new branch and commit those changes
  - git commit -m “Some changes are made in new branch”
- with below command newly created branch is pushed to remote repository where new branch is created to track our local branch
  -git push -u origin new-branch

- Newly created branch can be merged with creating a **pull request** in github.
- The changes from pull request can be merged into master branch if any collaborator who has privilege approved it.

## Working with Tags
- logs can be displayed with command
  - git  log
- list of tags can be displayed with command
  - git tag
- new tag can be added to a branch with below command which adds a new tag with name "stable" to master branch
  - git  tag stable master
- now we can list tags created with below command 
  - git tag
- Now logs can be shown pretty readable with command
  - git log --online --graph --decorate -all
- Annotated tags can be added with command to point specific commit id
  - git tag -a v0.1 -m “0.1 release” a6b446e
  - git tag -a v0.2 -m “0.2 release” c3039bf
- Tags can be pushed from local to remote repository with command
  - git push --tags



