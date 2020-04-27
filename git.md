# Git / GitHub Cheat-Sheet

## Installation

### Ubuntu
- Update index package
  - sudo apt update
- Install git
  - sudo apt install git
- Check version
  - git --version
- More information available [here](https://linuxize.com/post/how-to-install-git-on-ubuntu-18-04/)


## Terminal Commands

- git clone https://github.com/devrichardmiller/hello-world.git
  - pulls down whole repo to current folder and creates local (.git) repo
- git config --global user.name "Richard Miller"
- git config --global user.email dev.richard.miller@gmail.com
  - sets local git repo for tracking who made what changes
  - (bit confused why this is not reflected in the remote repo, aka GitHub)
- git config --global credential.helper store
  - then enter: git pull
  - this will ask for username and password. Once entered, these credentials are then stored for all subsequent syncs with repo
- git init
  - creates a local repository in the current directory
- git add .
  - adds all of the files in the current folder to local git change-tracking
- git commit
  - commits all of the staged local files, thus marking them to be pushed during next remote sync (push)
- git remote -v
  - shows the current remote repo configuration (with the local repo of the given folder)
- git remote remove origin
  - removes linkage between the current local repo and the remote repo
- git remote add origin https://github.com/devrichardmiller/tour-of-heroes.git
  - connects the local repo in current folder with a remote (GitHub) repo
- git push -u origin master
  - syncs local committed changes to the master repo in GitHub
- git push -u origin branch1
  - syncs local committed changes to the "branch1" repo branch in GitHub