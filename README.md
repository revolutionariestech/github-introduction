# Github Introduction
This repo contains sample files and an introduction on how to use Github for beginners.

## Table of contents
* [Setting up github](https://github.com/revolutionariestech/github-introduction/edit/main/README.md#set-up-github)
* [Creating a repository](https://github.com/revolutionariestech/github-introduction/edit/main/README.md#create-repo)
* [Cloning/Adding to a repository](#git-repository)
* [Branching and Merging](#install-git)
* [Contributing](#contributing)
* [Basic git commands](#install-git)
---
#### Set Up Github
##### Creating a github account
1. Go to [GitHub.com](https://github.com/)
2. Enter your info to “Sign up for GitHub”
3. Select a username and password (your username is your github id)
   - ex: firstname-lastname
   - your github username is public and you will be using it in the future for classes/interviews/etc. so be mindful of what you choose
   - Use an email address that you use often - school or personal email (you can change this in the future/when you graduate)

##### **Installing Git**
*Mac*
- Type in `git` into the command line
  - if it's not installed you will be prompted to install it
    
*Windows*
- Use this [link](https://git-scm.com/download/win) to install git
- OR using Windows Subsystem Linux (WSL, which was probably set up in a previous class) do the following:
  - run linux/ubuntu
  - type `sudo apt install git` in the command line

---
#### Create Repo
##### Create repo in Github
1. Log into github
2. Click on the icon in the top right
3. Click on "Your Repositories"
4. Click on the green "New" button to create a new repository
5. Create a repository name and give the repo a short description if you want
6. Make it Public/Private depending on the project and personal preference (can change this later)
7. You can add a ReadMe file now, or create it later ([What is a README](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes))
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
#### Git Repository
##### Clone Repo onto computer: This will make a local copy of the repo on your computer
1. Go to the repository you want to clone
2. Click on the green "<> Code" tab
3. Copy the URL displayed
4. Go to your terminal and navigate to a folder that you would like this project to sit in
5. Type `git clone <URL LINK>` into the command line

##### Create and Upload files to repository in github
1. Click on the "+" button and either create or upload a new file
2. Once the files are uploaded/created you need to commit your changes with a commit message (usually describes what changes were made)
3. When you want to update/edit a file click on the file, then click on the pen/pencil icon and make your edits, then commit your changes with a new commit message

##### Create and Upload files to repository from computer
1. Find/create a file that you want to add to your repository and put/save it to the cloned repo folder on your computer
2. In the terminal navigate to the folder of the repository where the new file is
3. Follow these 3 steps in order to add the file to the repo:
   - `git add <filename>`: adds files that are pushed to github
   - `git commit -m "<commit message>"`
   - `git push`: this pushes files to github
4. To update an existing file in the repository on git repeat step 3 again (Ex: Each time you add more code to a file thats in the repo folder, using VS Code or another text editor, repeat step 3)

