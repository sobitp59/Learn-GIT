#               💻 ***Learning Git and Github*** 💻 

# ❤️ **GIT**
## 🏄 **Making Folder and getting ready for Git** 
---
### 🐶 Currently you are in this folder
```
~/Desktop
```
### 🐶 Make a directory  

```
~/Desktop  
$ mkdir yourfoldername
```
### 🐶 Go to the folder that you created just now by typing below line
```
~/Desktop  
$ cd yourfoldername
```

### 🐶 Now you will be moved to folder `yourfoldername`
##### Previous
```
~/Desktop
```        
##### Now
```
~/Desktop/yourfoldername
```
---
### 🐶 Now we will initialize a empty git repository in this folder.We can do this by typing 
```
~/Desktop/yourfoldername 
$ git init
```
### 🐶 Now when you will type `ls` you will see nothing in the folder
```
~/Desktop/yourfoldername (master) 
$ ls
```
### but here we have some hidden files.We can see that  by 
### here '-a' refers to all the hidden files.You will see somthing like this
```
~/Desktop/yourfoldername (master) 
$ ls -a
./ ../ .git/
```
### We can even see what's inside `./git` Just type the below line and you will see
```
~/Desktop/yourfoldername (master) 
$ ls .git
HEAD  config  description  hooks/  info/  objects/  refs/

```
---
### 🐶 Now lets make a file (for eg: file.txt, file.md) inside `yourfoldername` folder. We can achieve this by
```
~/Desktop/yourfoldername (master)
$ touch yourfilename
``` 
### 🐶 Now the repository that we have initialized earlier will come into play. Till now besides us no one knows that we have created a file called `yourfilename`. So we will let them know but, before that we have to know the <mark>status of our repository</mark>. We can do this by  
```
~/Desktop/yourfoldername (master)
$ git status
```
#### You will see something like this : 
```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        sobit.txt

nothing added to commit but untracked files present (use "git add" to track)
```
### 🐶 Here ⏫, below `Untracked files:` you will see all the files (`sobit.txt`) that no one can see. Now we will update this repository, to do that type
#### this🎱 
```
~/Desktop/yourfoldername (master)
$ git add .
```
#### OR this⚾
```
~/Desktop/yourfoldername (master)
$ git add yourfilename
```
---
##### `First(🎱) one add all the files while the second(⚾) one will add only the files that you have mentioned`

---
### 🐶 Now when we will see the status again, we will see
```
~/Desktop/yourfoldername (master)
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   sobit.txt
```

### 🐶 Now we will write a message for what we have added or changed to the file.In programming we call it `commit`. We can do this by
``` 
~/Desktop/yourfoldername (master)
$ git commit -m "sobit.txt file added"

[master (root-commit) e47dd73] sobit.txt file added
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 sobit.txt
```
----
##### `Here -m stands for message`

---
### now when you will see status again , you will see
```
~/Desktop/yourfoldername (master)
$ git status
On branch master
nothing to commit, working tree clean
```
### 🐶 Add something to your file (Suppose you have added : 'I am learning Git and Github', then you will see below how it looks) and watch it here by typing
```
~/Desktop/yourfoldername (master)
$ cat yourfilename
I am learning Git and Github
```
### 🐶 Now try to check status again, you will see (our file has been modified) 
```
~/Desktop/yourfoldername (master)
$ git status

On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   sobit.txt

no changes added to commit (use "git add" and/or "git commit -a")
```
### 🐶 Now we will add it, you know how we did it earlier
```
~/Desktop/yourfoldername (master)
$ git add .
```
### 🐶 Now again try to check status, you will see
```
~/Desktop/yourfoldername (master)
$ git status

On branch master
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   sobit.txt
```
### 🐶 Now add a message for what you have changed/modified in the file
```
~/Desktop/yourfoldername (master)
$ git commit -m "this-this changes made"

[master a4929c6] this-this changes made
 1 file changed, 3 insertions(+), 0 deletions(-)
```
----
### ⚠️ Suppose the changes that we have made in our file and added by mistake and we don't want to add it, (without commiting) then we can do this by
```
~/Desktop/yourfoldername (master)
$ git restore --staged yourfilename
```
----
### 🐶 Now we may want to know where are the data of the files that we have changed/updated till now. We can do this by - 

```
~/Desktop/yourfoldername (master)
$ git log

commit a4929c641769cc3bc24d9c13e125397cab3f8fa6
Author: Your name <your email id>
Date:   Mon Jan 24 17:55:27 2022 +0530

    yourfilename file modified

commit e37dd73d28a9ecb1e9916cbb67768ebecb8406de
Author: Your name <your email id>
Date:   Mon Jan 24 17:30:08 2022 +0530

    yourfilename file added
```
### 🐶 Now suppose you want to remove the commit after `Mon Jan 24 17:30:08 2022 +0530`. To do this we need to copy the id(`e37dd73d28a9ecb1e9916cbb67768ebecb8406de`) and then
```
~/Desktop/yourfoldername (master)
$ git reset e37dd73d28a9ecb1e9916cbb67768ebecb8406de
```
### now when you will log again you will see something like this :
```
~/Desktop/yourfoldername (master)
$ git log

commit e47dd73a28a9ecb2e9916cbb67768ebecb8406ce (HEAD -> master)
Author: Your name <your email id>
Date:   Mon Jan 24 17:30:08 2022 +0530

    yourfilename file added
```
----
### **GIT STASH**
### 💜 Suppose you have made some changes but you don't want to commit also you don't want to lose those changes, then we can do this by 
```
~/Desktop/yourfoldername (master)
$ git stash
``` 
### 💜 We can get those changes again by
```
~/Desktop/yourfoldername (master)
$ git stash pop
```
### 💜 Now suppose you want to permanently remove the uncommitted files, we can do this by
```
~/Desktop/yourfoldername (master)
$ git stash clear
```
---
# ❤️ **GUTHUB**
### 😻 Till now we don't have any repository where we can put our files. So we can create a repository on [Github](https://github.com).(Suppose our repository name is : Github-Repo, then you will get URL like `https://github.com/yourusername/Github-Repo.Git`)
### Now we will connect our projects to this repository. To do this type
```
~/Desktop/yourfoldername (master)
$ git remote add origin https://github.com/yourusername/Github-Repo.Git
```
---
#### `Here 'remote' means you are working with URLs , 'add' means you are adding something, 'origin' is the name of the URL(https://github.com/yourusername/Github-Repo.Git)`
---

### 😻 Now type the below line
```
~/Desktop/yourfoldername (master)
$ git remote -v

origin https://github.com/yourusername/Github-Repo.Git (fetch)
origin https://github.com/yourusername/Github-Repo.Git (push)
```
### these are all the links related to these folders
---
### 😻 Now to show our files on Github we need to do
```
~/Desktop/yourfoldername (master)
$ git push origin master
```
### refresh your website and you will see all the files are showing there
---
## **Now we will work with  existing Files 📁**
### 😻 Find a repo, forked it and clone to your local machine by 
```
~/Desktop/yourfoldername (master)
$ git clone yourURL
```
### it will clone the project to your local machine. Now you can change or modify it which you are not able to do earlier.
---
### 😻 Now type
```
~/Desktop/yourfoldername (main)
$ git remote -v
```
### you will see this:
```
origin  https://github.com/yourusername/reponame.git (fetch)
origin  https://github.com/yourusername/reponame.git (push)
```
### `origin : ` this is our own account but now we will set the name of the url from which we have cloned earlier. To do this type :
```
~/Desktop/yourfoldername (main)
$ git remote add upstream https://github.com/forkedfromusername/reponame.git

```
### now when you type the below line you will see something like this : 
```
~/Desktop/yourfoldername (main)
$ git remote -v

origin  https://github.com/yourusername/reponame.git (fetch)
origin  https://github.com/yourusername/reponame.git (push)
https://github.com/forkedfromusername/reponame.git (fetch)
https://github.com/forkedfromusername/reponame.git (push)
```
# 🌸 **Now we will learn BRANCHING ⛓️ in GIT** 
### 🌸You have noticed that we are now in `main` branch
```
~/Desktop/yourfoldername (main)
```
### but when we try to change/modify files we must create a separate branch for that. To create a branch we need to type
```
~/Desktop/yourfoldername (main)
$ git branch branchname
```  
### now we will point the branch `branchname` to head. To do this we need to type
```
~/Desktop/yourfoldername (main)
$ git checkout branchname
```
### 🌸Now you will see we are in `branchname` branch
```
~/Desktop/yourfoldername (branchname)
```

### 🌸Now we will follow some previous steps, like :
```
~/Desktop/yourfoldername (branchname)
$ git add .
```
```
~/Desktop/yourfoldername (branchname)
$ git commit -m "your message"
```
```
~/Desktop/yourfoldername (branchname)
$ git push origin branchname
```
---

### ⚠️ We must create separate branch for each separate feature or bug we are adding or solving 
---

