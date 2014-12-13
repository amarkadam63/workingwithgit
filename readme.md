# Working with git

This repo has been created as example repository for 'Working with Git' workshop hosted by Kapil Sharma and Ramesh Dahiya and sponsored by GraciousSoft and GitHub.

This include list of commands we are supposed to run during workshop

# Project (Git) Initialization

## Set up repository on github.

* Go to github.com and login (We expect you already have account, if not, first create account)
* Click on `+` symbol on top right and then on `New repository`.
* Enter 'workingwithgit' as Repository name, some description.
* Ensure `Initialized this repository with a README` is unchecked. We will soon create our own readme.
* Click on 'Create repository'.
* Congratulations, your repository is created. You must also see commands to initialize repository locally. For now, we first create repository locally.

## Creating local repository

* Go to your development folder. We expect you have some dedicated folder for development. If not, make it as its good practice to keep all related projects in single folder. I personally keep all my projects in `d:\dev` under windows and `/home/kapilsharma/dev` under linux.
* Create project folder. Please make sure folder name is same as repository name you created above. Its not mandatory but good practice.
```
mkdir workingwithgit
```
* Go into folder and initialize git
```
cd workingwithgit
git init
```
* Create a `readme.md` file and edit it. It will work as project details page on git hub.
```
touch readme.md
vim readme.md
```
* Please note `.md` represent markdown files, which is easy markup for documentation and unlike documents created in office softwares, can be in version control system. For now, just add few simple lines as follow:
```
 # Working with Git workshop

 Added sample readme during `Working with Git` workshop.
```

## Commit files and check on github

We have our first file so lets commit it

```
 -- Its good to check status initially
 git status

 -- Mark file to commit
 git add readme.md

 -- Check status again
 git status

 -- Now we are ready to commit
 git commit -m "First commit"
```

Great, we have our first commit. However if you remember from presentation, Git
