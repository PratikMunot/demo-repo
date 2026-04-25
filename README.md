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
Go to Github Profile -> Settings -> SSH and GPG Keys -> Add key -> Then add your public key there

