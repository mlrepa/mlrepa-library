![Untitled](/docs/assets/images/3-git-remote.png)


# GitLab workflow: Git Remote

## 👀 Overview
In this module, you will learn how to work with a remote repository using GitLab.

You will clone a remote repository, update your local repository and push changes to the remote.

Additionally, you will learn how to create a Merge Request to propose changes to the original repository.

## 🎯 Tasks and Goals
- Clone an existing repository from GitLab.
- Update the local repository with changes made on GitLab.
- Push changes from the local repository to GitLab.
- Create a Merge Request to propose changes to the original repository.

## ⚒️ Tutorial: Work with the remote repository (GitLab)

## **1. Clone a repository**

To clone a repository means to download the files from the remote repository to your computer and to create a connection between them.

To clone a repository:

1. Open a terminal and go to the directory where you want to clone the files.
2. Copy the Git SSH URL of the repository (REPO_URL)
Untitled

3. Сlone the repo using the command:

```bash 
git clone REPO_URL 
```

!!! note "Note"

    Git automatically creates a folder with the repository name and downloads the files there.



## **2. Update and push to remote**

Let’s see how to work with a remote repository using GitLab.

1. First, we navigate to our project-1-git directory using the command **`cd project-1-git`**.
   
```bash 
# Go to the repository 
cd project-1-git 
```
2. Then, we create a new branch called **`dev`** . By this way you can make changes without affecting the main codebase. And we switch to new branch with the command **`git checkout -b dev`**.
   
```bash 
# Create `dev` branch and checkout to it
git checkout -b dev
```
3. Next, we create a new file called **`config.yaml`** using the **`touch`** command and add a line to it using **`echo "repo: project-1-git" >> config.yaml`**. We confirm the changes using **`cat config.yaml`**.
 
```bash 
#Create a config file 
touch config.yaml 
echo "repo: project-1-git" >> config.yaml
cat config.yaml
```
4. Also, we add and commit the changes to the local repository using **`git add config.yaml && git commit -m "Add config.yaml"`**.
```bash 
# Commit changes
git add config.yaml && git commit -m "Add config.yaml"
```
5. Finally, we push our changes to the remote repository on GitLab using **`git push origin dev**`. This will create a new branch on the remote repository with the changes we've made in our local repository.
```bash 
# Push to GitLab 
git push origin dev
``` 

## **3. Create a Merge Request**

1. Create a Merge Request (via GitLab UI) to the main branch
2. Wait...
3. Check the test assignment report

## 🏁 Conclusion

Congratulations on completing this tutorial! 🥳

You have learned how to work with a remote repository using GitLab. You cloned a remote repository, updated your local repository, and pushed changes to the remote.

Furthermore, you learned how to create a Merge Request to propose changes to the original repository.

## 🎓 Additional Resources and Links for Self-learning:

- [Git Security SSH](https://www.w3schools.com/git/git_security_ssh.asp?remote=github)
- [GitLab documentation](https://docs.gitlab.com/)
- [GitLab tutorials](https://docs.gitlab.com/ee/gitlab-basics/)
- [Git documentation](https://git-scm.com/doc)
- [GitHub Git cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet/)

## **🚀 Your Feedback is Important to the Community!**

Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥

Please 🙏🏻  take a moment to fill out feedback form. We would appreciate any suggestions or comments you may have on how we can improve our tutorials and create better learning experiences for the whole community. 

[Feedback Form :fontawesome-solid-paper-plane:](https://forms.gle/Yc9DmampbwFpEzo58){ primary: #7f56c0 accent: #7f56c0; .md-button }

Thank you for taking the time to share your thoughts with us! 👍

![Untitled](images/footer.png)