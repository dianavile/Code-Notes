# Git Cheat Sheet
- Source: [Git Cheat Sheet](http://rogerdudler.github.io/git-guide/files/git_cheat_sheet.pdf)

### Create & Clone
- __create new__ repository    = _`git init`_
- __clone local__ repository   = _`git init`_
- __clone remote__ repository  = _`git clone username@host:/path/to/repository`_

### Add & Remove
- __add__ changes to INDEX     = _`git add <filename>`_
- __add all__ changes to INDEX = _`git add*`_
- __remove/delete__            = _`git rm <filename>`_

### Commit & Synchronize
- commit changes                    = _`git commit -m *Commit message*`_
- push changes to remote repo       = _`git push origin master`_
- __connect__ local to remote repo  = _`git remote add origin <server>`_
- __update__ local with remote repo = _`git pull`_

### Branches
- __Create__ new branch          = _`git checkout -b <branch>`_
- __Switch to__ master branch    = _`git checkout master`_
- __Delete__ branch              = _`git branch -d <branch>`_
- __Push__ branch to remote repo = _`git branch -d <branch>`_

### Merge
- __Merge changes__ from another branch = _`git merge <branch>`_
- __View__ changes between two branches = _`git diff <source_branch> <target_branch>`_ e.g. git diff feature_x feature_y
   
### Tagging
- __Create__ tag                 = _`git <tag> <commit ID>`_ e.g git tag 1.o.o 1b2e1d63ff
- __Get commit IDs_              = _`git log`_

### Restore
- __Replace__ working copy with latest from HEAD = _`git checkout --<filename>`_

#### Resources
-  [Learn Git](https://www.atlassian.com/git/tutorials/learn-git-with-bitbucket-cloud)
-  [Version Control for Beginners](https://www.atlassian.com/git/tutorials/what-is-version-control)
-  [Git Get Started](https://www.atlassian.com/git/tutorials/setting-up-a-repository)
-  [Git Collaboration](https://www.atlassian.com/git/tutorials/syncing)
-  [Git Migration](https://www.atlassian.com/git/tutorials/svn-to-git-prepping-your-team-migration)
-  [Advanced Git Tutorials](https://www.atlassian.com/git/tutorials/advanced-overview)


