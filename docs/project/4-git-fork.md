![Untitled](images/4-git-fork.png)

# Git workflow: Forks

## **👀 Overview**

This tutorial is designed to help you learn the GitHub workflow for contributing to an open-source project. 

The tutorial covers topics such as creating a fork of a project, adding a new remote to your Git repository, adding a .gitignore file, making a data directory visible in GitHub, and creating a Merge Request.

## **🎯 Goals**

By the end of this module, you will be able to:

- Create a fork of an open-source project on GitHub.
- Add a new remote to your Git repository to track the forked project.
- Add a .gitignore file to exclude files and directories from version control.
- Make a data directory visible in GitHub.
- Create a Merge Request to submit your changes to the original project.

## **⚒️ Tutorial: Work with Repository Fork**

Sometimes to contribute other project we need to use Forks. 

Forking allows you to create a copy of an existing repository, including all its branches, commits, and history. This is useful if you want to experiment with the project, make changes, or add features without risking the original code.

A typical workflow of using forks include following steps:

1. Fork an open-source project to create a copy of an existing project
2. Clone the forked project to download and connect the files from the remote repository to your computer
3. Create a branch for your changes 
4. Add your changes, commit and push to the fork
5. Create a Merge Request (MR) from your fork to the parent (original) project

Let’s do it step by step.

### **1. Fork a project**

!!! note "Note"
    REPO_URL : https://github.com/mlrepa/project-1-git

Create a fork for the REPO_URL by following steps:

- in the GitHub docs: [Fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- in the GitLab docs: [Creating a fork](https://docs.gitlab.com/ee/user/project/repository/forking_workflow.html#creating-a-fork)

### **2. Clone a repo from your fork**

```bash
# Set a new remote
git clone FORK-REPO-URL
```

### **3. Create a new `4-git-fork` branch**

```bash
# Creat a new branch
git branch -b 4-git-fork
```

### **4. Add `.gitignore` and `data/` directory**

When working on a project, you may generate files or folders that are not necessary to include in version control, such as temporary files or log files. These files can clutter your repository and make it harder to manage.

So, `.gitignore` file allows you to specify files and directories that Git should ignore when committing changes.

Add `.gitignore` (use with VScode IDE)

- press `CTRL + Shift + P` (`CMD + Shift + P` on macOS) to open the command palette.
- type in `Add gitignore` in the command palette.
- Update code & commit

Example shows how to create an empty data/ directory, add file.txt to it, ignore `data/` in the `.gitignore`, and commit & push the 4-git-fork branch to GitHub.
Let’s dive in!

1. `mkdir data` creates a new empty directory called `data`.

```bash
# Create an empty `data/` directory
mkdir data
```
2. `touch data/file.txt` creates a new file called `file.txt` in the `data` directory.

```bash
# Create a `file.txt` in `data` dir
touch data/file.txt
```
3. `echo "data" >> .gitignore` adds the `data/` directory to the `.gitignore` file.

```bash
# Add to `.gitignore` but make it visible in the Git repo
echo "data" >> .gitignore
```
4. `git add .gitignore && commit -m "Add .gitignore and data/ directory"` stages the `.gitignore` file and commits the changes with the message "Add .gitignore and data/ directory".

`git push myfork 4-git-fork` pushes the changes to the `4-git-fork` branch on the user fork on GitHub.

```bash
# Commit & push `4-git-fork` branch to GitHub (to user fork)
git add .gitignore && commit -m "Add `.gitignore` and `data/` directory"
git push myfork 4-git-fork
```

Expected results:

- there is no `file.txt` added to Git history
- there is no `data` directory in GitHub (forked repo)

### **5. Update: make `data/` directory visible in GitHub**

If you have a data directory that contains large files, such as datasets or trained models, Git may not show them by default. This can cause issues if you need to share or collaborate on the project.

Making the data directory visible in GitHub ensures that the files are accessible to other team members.

The next stage is to make the previously ignored `data/` directory visible in GitHub. 
Look closer!

1. First, create a `.gitignore` file in the `data/` directory,

```bash
# Create `data/.gititnore`
touch data/.gititnore
```
2. add it to Git using force mode, 

```bash
# Add `data/.gititnore` to Git (force mode)
git add data/.gitignore -f
```
3. then commit and push the updates to the user's fork. 

```bash
# Commit & push updates
git add .gitignore && commit -m "Make `data/` empty but visible"
git push myfork 4-git-fork
```
4. Finally, delete the `4-git-fork`
 branch in the local repository.

```bash
# Delete `4-git-fork` branch in the local repo
git branch -d 4-git-fork
```

### **6. Create a Merge Request**

- Create a Merge Request (via GitHub UI) to the `main` branch in the parent repository (REPO_URL)

## **🏁 Conclusion**

Congratulations on completing this tutorial! 🥳 

In this tutorial, you learned the GitHub workflow for contributing to an open-source project. The topics covered included creating a fork of a project, adding a new remote to your Git repository, adding a .gitignore file, making a data directory visible in GitHub, and creating a Merge Request.

## **🎓 Additional Resources**

- [GitHub's documentation on creating a Merge Request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)
- [GitLab's documentation on creating a Merge Request](https://docs.gitlab.com/ee/user/project/merge_requests/)

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could

    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub 
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍    

![Untitled](images/footer.png)