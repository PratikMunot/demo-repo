# Demo repo

- by Pratik Munot

## Some Info

Git - Free and open source version control system
Clone - Bring a repository which is hosted somewhere like github into a folder on your local machine.
add - Track your files and changes in Git
commit - Save your files in Git
push - Upload Git commits to a remote repo, like Github
pull - Download changes from remote repo to your local machine, its the opposite of push

###########################

### 1) Set up credentials for github
```
git config --global user.name "Pratik.Munot"
git config --global user.email "pmunot11@gmail.com"
```

### 2) Create a git repo on github and clone it on your PC
```
git clone https://github.com/PratikMunot/demo-repo.git
```

### 3) Create a new file inside your git cloned folder named as file.txt and check status
```
vim file.txt
```
now we have 2 orginal files and a new one created fil.txt which is untracked.
whenever you create new files, they will be untracked by default

### Lets check status
```
git status
```

On branch main
Your branch is up to date with 'origin/main'.

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        file.txt

nothing added to commit but untracked files present (use "git add" to track)


### 4) Track files [1 file or all files at a time]
to track a single file
```
git add file.txt
```

Track all files and folders including nested ones
```
git add .
```

### Recheck status after tracking
```
git status
```
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   file.txt


### 5) Commit the changes
Once you have completed adding/tracking of all/required files, next you have to commit the changes
-m flag stands for commit message. Use a meaningful message
```
git commit -m "file.txt added"
```

### 6) Push all the files/changes

```
git push
```

it will ask for username and password which is your Personal Access Token
To generate a PAT [Go to Settings->Developer Settings->Generate new Token]

# 7) Alternate Authentication method is setup SSH key based access control
Generate new key pair
```
ssh-keygen -t rsa -b 4096 -C "pmunot11@gmail.com"
```
Enter passphrase or leave it empty
Enter key name
A pair of keys will be generated [1public key and another private key]
Go to Github Profile -> Settings -> SSH and GPG Keys -> Add key -> Finally add your public key there

---

### 8) Create repo locally and connect it to our repository
Currently we are working in folder demo-repo which is our repository as well.
Lets we create a new folder outside demo-repo with name demo-repo2
Inside demo-repo2 folder, create a file README.md and add some text in it.
Initialize a git repo via cmd
```
mkdir demo-repo2
cd demo-repo2
vim README.md
git init
```
Once you initialize, You will see a hidden folder .git created inside the folder demo-repo2
Check status and since its untracked so track it via add cmd
```
git status
git add README.md
git commit -m "added readme"
```

Now if you try to push it on, it produces error fatal
Thats because we have not cloned it from an existing repo and we are directly trying to push it on orgin master 
So git says it has no idea where to push it now.
Currently this repo is not yet connected to anything. We need to make that connection via following cmd.
Go to your new repo which is demo-repo2 which you have already created on github and copy its url.
```

git remote add origin https://github.com/PratikMunot/demo-repo2.git
```
Now you have established the connection between your local folder and remote git repo
You can start to push the changes via cmd - git push origin master. But there is a shortcut as well.
You can set a one time upstream to tell git that this will be my default location to push via cmd
```
git push -u origin master 
```
from next onwards you can simply use 
```
git push 
```
You can check how many repos are connected to this via cmd
``` 
git remote -v
> origin  https://github.com/PratikMunot/demo-repo2.git (fetch)
> origin  https://github.com/PratikMunot/demo-repo2.git (push)
```
---

### Branching 

Master Branch is the main or default branch in the repository.
If you are only working on one branch then master branch is where all your code, all your commits and changes  will live.
Lets create a new branch called feature branch. At first the master and feature branch will be exactly same. 
As you make updates to the feature branch those changes will be only seen in feature branch. Each changes or commits that are made on one branch will not be visible on the other branch. Each branch is only keeping track of changes and commits that are made on its own branch. 
