<!--
Creator: <Name>
Market: SF
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

# Git, GitHub, and You!

---
### Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
---
Have your files ever looked like this?

![image](https://i.kinja-img.com/gawker-media/image/upload/t_original/ewnlzxrjli1wmiyewn3d.png)
---
...And you're just one person. 


Now imagine trying to collaborate on a project with   
  - 3 people  
  - 10 people  
  - thousands...  
---
Chaos would rapidly ensue

![chaos](https://78.media.tumblr.com/f6e31f35d88833de6f927d13b5e98b92/tumblr_o6iteqEukn1qa0v13o1_250.gif)
---
Wouldn't it be great if we had a solution? A solution to **control** all the different **versions** of all the code we write?

---
Luckily, we have a solution - and it's called a *version control system*

* Git is the industry standard tool for version control. 
* That is, when you write code, git helps you track all of the changes that you've made over time to ensure that no work is lost.   
 ![git logo](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/320px-Git-logo.svg.png)
---
* Git*Hub* is the tool that takes git and makes it collaborative. 

![github logo](https://camo.githubusercontent.com/fb782da4019ab66eeea35cc9b9ce73b2438b1688/687474703a2f2f646f632e72756c746f722e636f6d2f696d616765732f6769746875622d6c6f676f2e706e67)

Note:
  * It helps you make sure that every developer's version of the code is the same between different computers. 
  * It has also allowed sharing of code and tools through the open source movement. 
  * You can freely access any code that somebody has made public and use it in your own projects.


---

## Git and GitHub  

You'll be using git and GitHub every day throughout this course (and as a developer in the industry) for version control. 

A version control system allows us to:
* Review changes made over time
* Revert files back to a previous state
* Collaborate on a project with other developers
* Track down the origin of bugs in the code
* Back up your projects on a remote server

Note: **Git** is a version control system and **GitHub** is a social network built around git. It allows you to see and use other people's code, share your code, and gain insight into your repositories. GitHub provides great tools to track and interact with your codebase.

---

Git stores information about your project in a **repository** (often called a repo). A git repository holds the current version of your project's files, as well as the complete history of all past versions.  

Note: Your computer holds a **local repository**. It's a copy of all of the changes you've ever committed on your machine. GitHub holds a **remote repository**. It's a copy of all of the changes you've ever committed and pushed to the web.

---

***

<a name="demo"></a>
## Demo: Git Configuration and Skills

As a class, we are going to walk through key Git skills that you will need to be successful in this course. Some of the goals of this session include:  

* Checking our Git configuration.

* Developing our Git skills.
You will:
    - Create a local Git repository.
    - Add files.  
    - Make commits.  
    - Check the repo status.  
    - View history.  
    - Time travel.  

### Part 1: Set Up

Check the Git version:  
```
$ which git
$ git --version
```

If you don't have Git installed via brew, you should do so now.
```
brew install git            # use brew to install latest version of Git    
which git                   # should return "/usr/local/bin/git"
```

Check your Git config:
```
$ git config --list
$ git config user.name
```

Set your identity:
```
$ git config --global user.name "John Doe"    
$ git config --global user.email johndoe@example.com
```

Set your default editor:
```
$ git config --global core.editor "subl -n -w"
```

### Part 2: Creating a Repo
Create a new local Git repository:

```
$ cd ~/dev # Or wherever you're keeping your code
$ mkdir sample1  
$ cd sample1  
$ git init
```

* What just happened?

### Part 3: Our First Commit

Add some files:

```
$ touch README.md hello.txt  
$ git status                  # What is an untracked file?
$ git add -A                  # Now the files are in the stage
$ git status
```

Commit the changes:

Your commit messages should be brief but descriptive. Aim for fewer than 10 words, but really describe what you achieved since your last commit. If it's easy to write a commit message, you're doing a good job breaking your work into smaller tasks and committing your work often. **COMMIT EARLY, COMMIT OFTEN!**

Here is an example of some commit messages that vary from good to bad:

![](https://imgs.xkcd.com/comics/git_commit.png)

```
$ git commit -m "Added 2 files."
$ git status
$ git log
```

### Part 4: More Commits, and Viewing the Repo History

Edit `hello.txt`, and commit the following changes:

Modify a file:
```
$ echo "Hello, World" >> hello.txt
$ git status
```

We now see a "modified" file, but nothing is staged.
Let's add our changes to the stage:

```
$ git add .
$ git status
```

Now our changes are staged and we can do a commit:

```
$ git commit -m "Fixed hello.txt"
```

Let's view the repo history:

```
  $ git log
```

* Notice all of the info in the log.
* In what order are the commits displayed?

***

<a name="ind-practice"></a>
## Independent Practice: Changes and Commits
Make some very simple changes to your file and commit them. Be sure to check your status and history as you go.

* Suggested changes:
    - Hello, General Assembly
    - Hello, WDI
    - Hello, Git



<a name="demo"></a>
## Demo: Git Skills, Continued

### Part 5: Cherry Picking

```
git add file1   
git commit  
git status  
git log
```

### Part 6: Checking Out a Previous Version

To see the old version:

```
git log  
git checkout <hash_of_previous_commit>
cat hello.txt  
```

To look at the history:

```
git log  
```
* Note: By default, the `log` command only shows up to our current commit.

To see all of the commits:

```
git log --all --decorate
```
* Note: What is `HEAD` and `master`?  

To return to the most recent version (two options):

```
git checkout master  

# or

git checkout <hash_of_most_recent_commit>  
```

### Part 7: Diffing
View unstaged differences:

```
git diff  

# or  

git diff filename  
```

View staged differences:  

```
git diff --staged

# or  

git diff --staged filename
```

### Part 8: Rolling Back Changes
Un-stage changes to a file:  
```
git reset filename  
git status  
```

Discard changes (reverting to the committed version):
```
git checkout filename  
git status
```  
***

<a name="conclusion"></a>
## Conclusion
* Review Git terminology:
    - **Repository**: A collection of related commits that form a directed acyclic graph.
    - **Commit**: A snapshot of the working tree at a given time (along with a message detailing what changed).
    - **The index (stage)**: A staging area where we list changes we want to commit.
    - **Branch**: A set of commits that form a linear progression of changes.
    - **Master**: The default name for the "main" development branch.
    - **Tag**: An optional label on a commit.
    - **HEAD**: The commit that is currently checked out.
    - **Working area**: The directory and subdirectories containing the files we're currently editing.
* Review questions:  
    - Can someone tell me what a Git repository is?
    - What are some key components of a Git repo?
    - Can someone describe an important Git command? (Get several responses from students).

***

---

Once you're ready for your local commits to become available online, you need to push the code to the remote repository on GitHub, named `origin`. Start with another `git status` to see how many commits you've completed since you last pushed. Then use the command `git push origin master` to make the remote repo match your local repo.

### Visualizing the Workflow
<figure>
![Git Workflow](https://i.stack.imgur.com/5V7uJ.png)

  <br>
  <figcaption>The table below has all of the key words from this diagram bolded. </figcaption>
</figure>

### Git Basics

| Action | Command |
| :--- | :--- |
| Create new git repository | `git init` |
| Copy (**clone**) an existing repository from the internet (remote) onto your computer (local)| `git clone <repo url>`|
| Check status of git repo | `git status` |
| Check differences since last commit | `git diff <filename>` |
| Add file to git repo (**stage** for commit) | `git add <filename>` |
| Add (**stage**) all edited files in the current directory | `git add .` |
| **Commit** (save) a version into the local repository | `git commit -m "message describing changes"` |
| **Push** commits to GitHub (remote repository) | `git push <remote> <branch>` |
| **Pull** commits from the remote repository | `git pull <remote> <branch>` |
| Show version history | `git log <filename>` |
| Get help with git commands | `git help <command>` |






### Check for Understanding

<details>
  <summary>In pairs at the board, draw a diagram that shows the commands you might use over time and the impact they would have on your local and remote repositories. Label the repositories, your machine, GitHub, and a collaborator's machine.</summary>
  <p>
    <figure>
      <img src="https://camo.githubusercontent.com/d4de2fdb747fec0d3dc67b1640f37c12f3786f5b/687474703a2f2f6a6c6f72642e75732f6769742d69742f6173736574732f696d67732f72656d6f7465732e706e67" alt="Local and remote">
    </figure>
    <img src="https://cloud.githubusercontent.com/assets/6520345/17574607/8515d59a-5f17-11e6-85be-89fa8ad9962c.png" alt="Local and remote">

  </p>
</details>

## Independent Practice
Practice the skills covered in this workshop with this [training](https://github.com/sf-wdi-labs/personal-portfolio)

## More ahead
- This is just the beginning of our interactions with git and GitHub. One important additional feature that we'll explore later is the capacity to have multiple branches. On each branch, you will work on a specific feature. When you've completed that feature you will merge the branch into the `master` branch of the project. You keep the `master` branch tidy and publish it. Other development branches are the place for experimentation.
- We'll also complete another workshop on collaborating in GitHub with the specific aim of making sure versions don't have conflicts - different changes to the same piece of code.

## Closing Thoughts
- This workflow has a lot of commands and procedure and will take a some practice to internalize. It's worth getting into your muscle memory.
- after this workshop, you should have a sense of the importance of git and GitHub, understand the workflow and the meanings of the git commands. You should be able to write code and commit it with a good commit message.
- Git and GitHub will be part of your daily routine every day you code. It's important to get to know it now. Comfort with git is a baseline skill that all companies look for in developers.
- Take a moment to see if you can, without looking at any other resources, handwrite the order of commands needed to commit your work and push it to GitHub. Include `git status`.
- How'd you do? ✊-5.

## Additional Resources
- [git, a simple guide](http://rogerdudler.github.io/git-guide/)
- [GitHub help's list of resouces](https://help.github.com/articles/good-resources-for-learning-git-and-github/)
- [How to write good commit messages](https://chris.beams.io/posts/git-commit/)
- in terminal, `git help`
- [branching, which we'll cover later](https://guides.github.com/introduction/flow/)
- [another tutorial on branching](http://learngitbranching.js.org/)
- [Git Cheat Sheet](https://raw.githubusercontent.com/ATL-WDI-Curriculum/local-and-remote-git/master/images/Git-Cheat-Sheet.png)
- [GitHub Pages](https://pages.github.com/)
- [Jekyll](https://jekyllrb.com/)
- [Git Documentation](https://git-scm.com/documentation)
- [Forking on GitHub](https://help.github.com/articles/fork-a-repo/)
- [Syncing a Fork](https://help.github.com/articles/syncing-a-fork/)
- [Linus Torvalds on Git](https://www.youtube.com/watch?v=4XpnKHJAok8)
