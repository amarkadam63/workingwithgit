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

Its good to check status initially

 ```
 git status
 # On branch master
 #
 # Initial commit
 #
 # Untracked files:
 #   (use "git add <file>..." to include in what will be committed)
 #
 #       readme.md
 nothing added to commit but untracked files present (use "git add" to track)
```

Mark file to commit

```
 git add readme.md
```

Check status again.

```
 git status
 # On branch master
 #
 # Initial commit
 #
 # Changes to be committed:
 #   (use "git rm --cached <file>..." to unstage)
 #
 #       new file:   readme.md
 #
```

Files listed under `Changes to be committed` means files are staged and ready to be committed.

Now we are ready to commit

```
 git commit -m "First commit"
```

Great, we have our first commit. Check status again and there will be no thing to commit.

```
git status
# On branch master
nothing to commit, working directory clean
```

If you remember from presentation, Git manage everything locally so even after commit, our files are not present on the server. To send them on the server, we must push local changes.

However there is another problem, our local git do not know about server. For this, we have to add remote. This is one time process. Check the repository url on github. It must be like `https://github.com/<username>/workingwithgit.git`. So lets add remote:

```
git remote add origin https://github.com/kapilsharma/workingwithgit.git
```

Here `origin` in default server.

Now lets push our commit to the server

```
git push origin master
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 1.19 KiB, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new branch]      master -> master
```

Great, your readme.md file sent on the server. Please go to github.com and confirm.
