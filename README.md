# Github Introduction
>This repo contains sample files and an introduction on how to use Github for beginners.

## Table of contents
* [Setting up GitHub](#set-up-github)
* [Creating a Repository](#create-repo)
* [Cloning/Adding to a Repository](#git-repo)
* [Branching and Merging](#branch-and-merge)
* [Fork a Repository](#fork-repo)
* [Basic/Other git commands](#git-commands)


---
#### <ins>Set Up Github</ins>
##### Creating a github account
1. Go to [GitHub.com](https://github.com/)
2. Enter your info to “Sign up for GitHub”
3. Select a username and password (your username is your github id)
   - ex: firstname-lastname
   - your github username is public and you will be using it in the future for classes/interviews/etc. so be mindful of what you choose
   - Use an email address that you use often - school or personal email (you can change this in the future/when you graduate)

##### Installing Git
>*Mac*
- Type in `git` into the command line
  - if it's not installed you will be prompted to install it
    
>*Windows*
- Use this [link](https://git-scm.com/download/win) to install git
- OR using Windows Subsystem Linux (WSL, which was probably set up in a previous class) do the following:
  - run linux/ubuntu
  - type `sudo apt install git` in the command line


---
#### <ins>Create Repo</ins>
##### Create repo in Github
1. Log into github
2. Click on the icon in the top right
3. Click on "Your Repositories"
4. Click on the green "New" button to create a new repository
5. Create a repository name and give the repo a short description if you want
6. Make it Public/Private depending on the project and personal preference (can change this later)
7. You can add a ReadMe file (What this is) now, or create it later ([What is a README](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes), [Basic writing and formatting syntax for README](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax))
8. Press the green "Create repository" button

##### Add Collaborators
1. Navigate to the repository you want to add a collaborator to
2. Click on "Settings" at the tob of the page
3. Click on Collaborators (it may ask you to confirm your github password)
4. Click the green "Add people" button
5. Type in the github id of the person you want to collaborate with
   - They can then view your repository and collaborate on it
6. The invite will be sent to your collaborators, they have to accept within a week or it expires


---
#### <ins>Git Repo</ins>
##### Clone Repo onto computer: This will make a local copy of the repo on your computer
1. Go to the repository you want to clone
2. Click on the green "<> Code" tab
3. Copy the URL displayed
4. Go to your terminal and navigate to a folder that you would like this project to sit in
5. Type `git clone <URL LINK>` into the command line

##### Create and Upload files to repository (Using github)
1. Click on the "+" button and either create or upload a new file
2. Once the files are uploaded/created you need to commit your changes with a commit message (usually describes what changes were made)
3. When you want to update/edit a file click on the file, then click on the pen/pencil icon and make your edits, then commit your changes with a new commit message

##### Create and Upload files to repository (Using terminal)
1. Find/create a file that you want to add to your repository and put/save it to the cloned repo folder on your computer
2. In the terminal navigate to the folder of the repository where the new file is
3. Follow these 3 steps in this order to add the file to the repo:
   - `git add <filename>`: adds files that are pushed to github
   - `git commit -m "<commit message>"`
   - `git push`: this pushes files to github
4. To update an existing file in the repository on git repeat step 3 again (Ex: Each time you add more code to a file thats in the repo folder, using VS Code or another text editor, repeat step 3)
5. If a collaborator adds to the repository and pushes their changes, in order to get the updated version on your computer use the command `git pull`
   - if you're working on a repository with collaborators it's good habit to use `git pull` before making changes and push whenever you make changes to avoid conflicts


---
#### <ins>Branch and Merge</ins>
>If multiple people are working with the same project on the same repository they can't all make changes to the file at the same time on their individual accounts, this will cause a conflict. This is where branching and merging comes in handy.

>Multiple people can create separate branches to work on their code and then they can merge their changes onto the main branch. Branches are made to be temporary. Changes made in a particular branch don't affect other branches until branches are merged.

>Branching/merging is also useful when you want to create/try multiple different versions of the same code with some variations (useful for comparing outputs/finding what works best)

>To branch and merge make sure you are navigated to the folder of your repository in your terminal

*(Note: the main branch is always called "main", so don't name other branches "main")*

##### BRANCHING
>Branching creates a copy of the code from the `main` branch onto the new branch. Changes made directly in the branches don't affect the code of the main branch until you merge.
- create a branch: `git branch <branch name>`
- move to a branch `git checkout <branch name>`
- view available branches: `git branch`
   - Git uses an asterisk to identify what branch you're in
- When you make changes on your branch push them using the [steps above](#create-and-upload-files-to-repository-using-terminal)

##### MERGING
>Combines branches so that the 2 branches have the same content/code
- 1st use `git checkout` and switch to the branch you want to merge into,
   - Say you want to merge "branch1" into "main" `git checkout main` (this means you want to copy the contents from branch1 and paste it into main)
   - Merge branch1 into main (you're on the main branch): `git merge branch1`
- If you have multiple collaborators that each create their own branch everything needs to be merged to the main first then you're individual branch
   - Say user1 creates a branch called "user1" and user2 creates a branch called "user2".
      - If user1 makes a change and pushes it onto their branch (user1), they then need to merge "user1" into "main" and push the changes
        ```
        - git checkout main
        - git merge user1
        - git push
        ```
      - Then user2 needs to pull from "main" and merge those changes onto their branch (user2)
        ```
        - git checkout main
        - git pull
        - git checkout user2
        - git merge main
        - git push
        ```


---
#### <ins>Fork Repo</ins>
> A fork is a new repository that shares code and visibility settings with the original “upstream” repo.

> Forks are used to propose changes to the main repository.

You can use forks to propose changes related to fixing a bug, you can:
- Fork the repository
- Make the fix
- Submit a pull request to the project owner

##### How to fork a repo ([More on Forking](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/fork-a-repo?platform=windows&tool=webui))
1. In the top-right corner of the repo's page, click "Fork"
2. You can then change the name, owner, and description to your desire of this "forked" repo
3. Click the green "Create a fork" button at the bottom
4. After you fork a repo, in order for it to exist locally on your computer you can go through the steps of cloning it

##### Creating a pull request (for the main repo to get your changes made on the forked repo)
> Create a pull request to propose changes to a repo. These changes are proposed in a branch, which can then be chosen to merge with.

*ON the Forked repo:*
1. On the forked repository click on "Pull requests" button at the top
2. Click on the Green "Compare & pull request" button (then make sure the base and compare branches are correct)
3. Write a title and description (optional) for your pull request
4. Click on the green "Create pull request" button at the bottom

*ON the Main repo:*
1. On the main repository click on the "Pull requests" button at the top
2. It will show you the number of pull requests submitted, click on the one you want to merge with
3. In the specific pull request you can see what was changed in "Files changed"
4. Then to merge click on the green "Merge pull request" button
5. Then click on the green "Confirm merge" button
6. The main repo should now be updated with the contents/changed files of the forked repo


---
#### <ins>Git Commands</ins>
>Here are some other basic/helpful git commands for terminal (includes commands from above too)
- `git init`: creates local git repo
- `git clone <URL>`: clone repository
- `git status`: checks status
- `git add <filename>`: add file to staging (to be pushed)
   - `git add .`: add all files in the current/sub folders 
- `git commit -m "<commit message>"`: commit changes
- `git branch`: list all branches ("*" denotes current branch)
- `git branch <branch name>`: creates a new branch
- `git branch  -d <branch name>`: deletes a branch
- `git checkout <branch name>`: switch to a branch
- `git merge <branch name>`: merge a branch into the active branch (the branch you're in)
   - `git merge <source branch> <target branch>`: merge source branch into target branch
- `git push`: push changes to repo
   - `git push origin <branch name>`: push a branch to your remote repo
- `git pull`: update local repo
   - `git pull origin <branch name>`: pull changes from remote repo
  
---
[GitHub Docs](https://docs.github.com/en): To read and learn more about github
