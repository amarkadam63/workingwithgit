# Setup Project and development

## Step 1

As discussed during presentation and shown in the image below, lets first create tag 'v0.1.0' on master branch.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (master)
$ git tag v0.1.0
```

Confirm tag is created successfully

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (master)
$ git tag
v0.1.0
```

Also not forget to push tag.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (master)
$ git push origin tag v0.1.0
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new tag]         v0.1.0 -> v0.1.0
```

Quick diagram of gitflow workflow
![Gitflow Workflow](https://github.com/kapilsharma/workingwithgit/blob/master/images/GitWorkflow.png)

## Step 2

Now lets create `develop` branch and go there.

However before that, lets check existing branches:

```
$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

Above output show we have only one branch `master` and we are, obviously, on only available branch. `*` before `master' show we are on that branch. Branch name starting with `remote` show remote branches.

Now lets create branch and check branches again.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (master)
$ git checkout -b develop
Switched to a new branch 'develop'

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git branch -a
* develop
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
```

So we created and checkout `develop` branch. However please note, that branch is not available on remote. So lets remote know about that.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git push origin develop
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new branch]      develop -> develop

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git branch -a
* develop
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/develop
  remotes/origin/master
```

Please note, `develop` branch is now available on remote too.

## Step 3

Like step 2, lets create `feature_m1` branch.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git checkout -b feature_m1
Switched to a new branch 'feature_m1'

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git branch -a
  develop
* feature_m1
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/develop
  remotes/origin/master

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git push origin feature_m1
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new branch]      feature_m1 -> feature_m1

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git branch -a
  develop
* feature_m1
  master
  remotes/origin/HEAD -> origin/master
  remotes/origin/develop
  remotes/origin/feature_m1
  remotes/origin/master
```

## Step 4

Now its development time. Lets create a dummy project. For that, lets create a folder `dummyfiles` and two files `file1.php` and `file2.php`. Put some dummy single line code in both files.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ mkdir dummyfiles

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ cd dummyfiles

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit/dummyfiles (feature_m1)
$ touch file1.php

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit/dummyfiles (feature_m1)
$ touch file2.php

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit/dummyfiles (feature_m1)
$ vim file1.php

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit/dummyfiles (feature_m1)
$ vim file2.php
```

Lets commit these files and push.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit/dummyfiles (feature_m1)
$ cd ..

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git status
On branch feature_m1
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   setupproject.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        dummyfiles/

no changes added to commit (use "git add" and/or "git commit -a")

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git add dummyfiles/

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git status
On branch feature_m1
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        new file:   dummyfiles/file1.php
        new file:   dummyfiles/file2.php

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   setupproject.md

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git commit -m "feature_m1 development finished"
[feature_m1 7bca319] feature_m1 development finished
 2 files changed, 2 insertions(+)
 create mode 100644 dummyfiles/file1.php
 create mode 100644 dummyfiles/file2.php

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git push origin feature_m1
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Counting objects: 6, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (5/5), 508 bytes | 0 bytes/s, done.
Total 5 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
   364f25a..7bca319  feature_m1 -> feature_m1
```

## Step 5: Merge feature_m1 to develop

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m1)
$ git checkout develop
M       setupproject.md
Switched to branch 'develop'

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git pull origin develop
From https://github.com/kapilsharma/workingwithgit
 * branch            develop    -> FETCH_HEAD
Already up-to-date.

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git merge origin feature_m1
Updating 364f25a..7bca319
Fast-forward
 dummyfiles/file1.php | 1 +
 dummyfiles/file2.php | 1 +
 2 files changed, 2 insertions(+)
 create mode 100644 dummyfiles/file1.php
 create mode 100644 dummyfiles/file2.php

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git push origin develop
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
   364f25a..7bca319  develop -> develop
```

## Step 6: feature_m2 branch

Now developers finished `feature_m1` branch but they can't sit idle. So lets create `feature_m2` branch so that they can work on further features.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git checkout -b feature_m2
M       setupproject.md
Switched to a new branch 'feature_m2'

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m2)
$ git push origin feature_m2
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new branch]      feature_m2 -> feature_m2
```

## Step 7: Merge feature_m1 changes to release branch

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (feature_m2)
$ git checkout develop
M       setupproject.md
Switched to branch 'develop'

kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (develop)
$ git checkout -b release
M       setupproject.md
Switched to a new branch 'release'
```

Since release branch just created from develop branch, we need not to merge. lets directly push it.

```
kapils@KAPILSHARMA /d/dev/phpreboot/workingwithgit (release)
$ git push origin release
Username for 'https://github.com': kapilsharma
Password for 'https://kapilsharma@github.com':
Total 0 (delta 0), reused 0 (delta 0)
To https://github.com/kapilsharma/workingwithgit.git
 * [new branch]      release -> release
```

## Further steps

Now with proposed workflow and [cheatsheet] handy, try finishing remaining steps. Please raise your hand in case of any doubt and someone will come to you to help.

[cheatsheet]: https://github.com/kapilsharma/workingwithgit/blob/master/cheatsheer/getcheatsheet.pdf
