# Git Tutorial


### 0. Install git and create a GitHub account

Follow [these](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) instructions to install git.
This tutorial requires and covers only git command-line interface, however, there are some great git GUIs to try out after you get used to cli. 

Once you've done that, create a GitHub account [here](https://github.com/signup)


**! Difference between Git and GitHub**

Git is a version control system that lets you manage and keep track of your source code history. GitHub is a service that lets you manage Git repositories.


### 0.1. Access 34vsk organisation

After successful registration, send your nickname to the telegram channel. You will be added to the 34vsk organization, where you will commit your projects in the future. Organisation is created to let teacher and your classmates help you with a problem at any time, as well as give advice about the code. 


### 1. Create a local git repository

When creating a new project on your local machine using git, you'll first create a new repository. 

*We'll be using the terminal. If you don't have much experience with the terminal and basic commands, check out these tutorials for [windows](https://www.makeuseof.com/tag/a-beginners-guide-to-the-windows-command-line/) and [linux/macOS](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview)*

Open up a terminal and move to your projects directory. Let's assume you want to create project ```tutorial``` on your Desktop. Then you'd do something like:
```bash
> cd ~/Desktop
> mkdir tutorial
> cd tutorial
```

To initialize a git repository in the root of the folder, run the ```git init``` command:
```bash
> git init
Initialized empty Git repository in /Users/doublegrey/Desktop/tutorial/.git/
```

### 2. Add a new file to the repo

Add a new file to the project, using any text editor you like. If you are using Visual Studio Code, just open ```tutorial``` folder and create hello.py file 
```python
print("hello, git")
```

After creating the new file, you can use the ```git status``` command to see which files git knows exist
```bash
> git status
On branch master

Initial commit

Untracked files:
  (use "git add <file>..." to include in what will be committed)

	hello.py

nothing added to commit but untracked files present (use "git add" to track)
```

What this basically says is, "Hey, we noticed you created a new file called hello.py, but unless you use the ```git add``` command we aren't going to do anything with it."

> One of the most confusing parts when you're first learning git is the concept of the staging environment and how it relates to a commit.
>
> A commit is a record of what changes you have made since the last time you made a commit. Essentially, you make changes to your repo (for example, adding a file or modifying one) and then tell git to put those changes into a commit.
> 
> Commits make up the essence of your project and allow you to jump to the state of a project at any other commit.
> 
> So, how do you tell git which files to put into a commit? This is where the staging environment or index come in. As seen in Step 2, when you make changes to your repo, git notices that a file has changed but won't do anything with it (like adding it in a commit).
> 
> To add a file to a commit, you first need to add it to the staging environment. To do this, you can use the git add <filename> command (see Step 3 below). 
>
> Once you've used the git add command to add all the files you want to the staging environment, you can then tell git to package them into a commit using the git commit command.
  
  
### 3. Add a file to the staging environment

Add a file to the staging environment using the ```git add .``` command:
```bash
> git add .
```
  
If you rerun the git status command, you'll see that git has added the file to the staging environment (notice the "Changes to be committed" line). 
```bash
> git status
On branch master

Initial commit

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)

	new file:   hello.py
```
  
### 4. Create a commit

Run the command ```git commit -m "Your message about the commit"```
```bash
> git commit -m "hello.py added"
[master (root-commit) b345d9a] hello.py added
 1 file changed, 1 insertion(+)
 create mode 100644 hello.py
```

Commits live forever in a repository, so if you leave a clear explanation of your changes it can be extremely helpful for future programmers (perhaps future you!) who are trying to figure out why some change was made years later.
  
### 5. Create a new repository on GitHub
  
If you only want to keep track of your code locally, you don't need to use GitHub. But if you want to work with a team, you can use GitHub to collaboratively modify the project's code.

To create a new repo on GitHub, log in and go to the 34vsk [home page](https://github.com/34vsk). You can find the “New” option there
  
![image](https://user-images.githubusercontent.com/25150523/132661432-eaee9f66-3528-45f1-b735-9869ca91adb0.png)

After clicking the button, GitHub will ask you to name your repo and provide a brief description. When you're done filling out the information, press the 'Create repository' button to make your new repo
  
![image](https://user-images.githubusercontent.com/25150523/132661634-5e4f48ea-aa5a-4913-a4b9-75303aff3267.png)
  
Since we've already created a new repo locally, we want to push that onto GitHub:

```bash
> git remote add origin https://github.com/34vsk/doublegrey-tutorial.git
> git push -u origin master
Counting objects: 3, done.
Writing objects: 100% (3/3), 263 bytes | 0 bytes/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/34vsk/doublegrey-tutorial.git
 * [new branch]      master -> master
Branch master set up to track remote branch master from origin.
```

Just update GitHub page and you will see hello.py file!
![image](https://user-images.githubusercontent.com/25150523/132662747-27fe04ba-f80d-4d6d-b017-83a0696a3847.png)
  
  
### 6. Edit file

Let's imagine you decided to change your program. To do so, just change hello.py and run these git commands:

Add changes
```bash
> git add .
```
  
Create a commit
```bash
> git commit - "change description"
```

Push changes
```bash
> git push
```

Changes will immediately appear in GitHub repo
  
![image](https://user-images.githubusercontent.com/25150523/132663941-10a8d009-4f6a-4db2-a12d-e324385ac8fe.png)



