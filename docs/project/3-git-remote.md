![Untitled](images/3-git-remote.png)


# Git workflow: Remote

## 👀 Overview
In this module, you will learn how to work with a remote repository using GitHub and GitLab (look at the tutorial). 

You will clone a remote repository, update your local repository and push changes to the remote. 

Additionally, you will learn how to create a Merge Request to propose changes to the original repository.

## 🎯 Goals
- Clone an existing repository from the remote.
- Update the local repository with changes made on the remote repo.
- Push changes from the local repository to the remote.
- Create a Merge Request to propose changes to the original repository.

## **⚒️ Tutorial: Work with the remote repository (GitLab)**

### **1. Create and clone a repository**

For working with the remote repository, you need to clone a repo.

!!! Note
    To clone a repository means to download the files from the remote repository to your computer and create a connection between them.

1. Create an empty repository in your GitHub or GitLab account
2. Copy the SSH URL of the created repository.

GitHub:

![Untitled](images/3-git-remote-clone_repo-GitHub.gif)

GitLab:

![Untitled](images/3-git-remote-clone_repo-GitHub.gif)
3. Clone the repository using the command `git clone` in the CLI.

```bash
git clone REPO_URL
```

!!! Note
        Git automatically creates a folder with the repository name and downloads the files there.

### **2. Create and Update `dev` branch, push it to the remote**

Now let’s see how to work with a remote repository using GitHub. 

1. First, we navigate to our **3-git-remote** directory using the command `cd 3-git-remote`.

```bash
# Go to the repository 
cd 3-git-remote
```
2. Then, we need to create a new branch called `dev`. In this way, you can make changes without affecting the main codebase.
And we immediately switch to a new branch with the command `git checkout -b dev`.

```bash
# Create `dev` branch and checkout to it (-b flag)
git checkout -b dev
```
3. Next, we create a new file called `config.yaml` using the `touch` command and add a line to it using `echo "repo: project-1-git" >> config.yaml`. 
We confirm the changes using `cat config.yaml`.  This command will print the file’s content.

```bash
# Create a config file, make changes, confirm them
touch config.yaml 
echo "repo: project-1-git" >> config.yaml
cat config.yaml
```
4. Also, we add and commit the changes to the local repository using
 `git add config.yaml && git commit -m "Add config.yaml"`.

```bash
# Add and commit changes
git add config.yaml && git commit -m "Add config.yaml"
```
5. Finally, we push our changes to the remote repository (named origin) in the ‘dev’ branch using the `git push origin dev` command. 

```bash
# Push changes to the remote repository
git push origin dev
```

### **3. Create a Merge Request: `dev` → `main`**

Create a Merge Request via GitHub or GitLab  UI to the `main` branch

![Untitled](images/3-git-remote-MR-GitHub.gif)

![Untitled](images/3-git-remote-MR-GitHub.gif)

## **🏁 Conclusion**

Congratulations on completing this tutorial! 🥳

You have learned how to work with a remote repository. You set up SSH to connect to GitHub / GitLab, cloned a remote repository, updated your local repository, and pushed changes to the remote.

Furthermore, you learned how to create a Merge Request to propose changes to the original repository.

## **🎓 Additional Resources:**

- [Git Security SSH](https://www.w3schools.com/git/git_security_ssh.asp?remote=github)
- [GitLab documentation](https://docs.gitlab.com/)
- [GitLab tutorials](https://docs.gitlab.com/ee/gitlab-basics/)
- [Git documentation](https://git-scm.com/doc)
- [GitHub Git cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet/)
- [Using Git source control in VS Code](https://code.visualstudio.com/docs/sourcecontrol/overview)

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could

    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub 
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍

![Untitled](images/footer.png)