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
  
