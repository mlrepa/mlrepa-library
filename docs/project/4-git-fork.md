![Untitled](images/4-git-fork.png)

# Git workflow: Forks

## **👀 Overview**

In this tutorial, we will explore the concept of repository forks and how they are used for contributing to open-source projects.

In addition, you will practise forking, cloning, making changes and pushing them to your remote, creating Merge Requests. Also, you will have an opportunity to understand how to handle merge conflicts

## **🎯 Goals**

By the end of this module, you will be able to:

- Understand the purpose and benefits of using repository forks in collaborative projects.
- Learn the step-by-step workflow for using forks in open-source projects.
- Practice forking a project and cloning the forked repository to your local machine.
- Add your contributions to the forked project and create a Merge Request to propose changes to the original project.
- Understand how to handle merge conflicts that may arise when collaborating with Git.

## **⚒️ Tutorial: Work with Repository Fork**

Sometimes to contribute to other projects we need to use Forks. 

Forking allows you to create a copy of an existing repository, including all its branches, commits, and history. This is useful if you want to experiment with the project, make changes, or add features without risking the original code.

A typical workflow for using forks in open-source projects includes the following steps:

1. Fork an open-source project to create a copy of an existing project
2. Clone the forked project to download and connect the files from the remote repository to your computer
3. Create a branch for your changes 
4. Add your changes, commit and push them to the fork
5. Create a Merge Request (MR) from your fork to the parent (original) project 

Let’s practise it step by step.

### **1. Fork a project**

For learning purposes in this tutorial, we will use the following remote repository:

!!! Note
    [https://github.com/mlrepa/mlrepa-library](https://github.com/mlrepa/mlrepa-library)

First, you need to create a fork for the training repository by following the steps:

- in the GitHub docs: [Fork a repo](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
- in the GitLab docs: [Creating a fork](https://docs.gitlab.com/ee/user/project/repository/forking_workflow.html#creating-a-fork)

### **2. Clone a repo from your fork**

```bash
# Set a new remote
git clone FORK-REPO-URL
```

### **3. Add your contribution**

For this exercise, you may choose one of the options below: 

1. Vote for the next tutorial topics in the Roadmap or suggest your own (section **[Roadmap](https://mlrepa.github.io/mlrepa-library/repa/roadmap/)**)
2. Share the links to interesting open-source repositories of ML and AI projects that apply good engineering practices, meet [REPA principles](https://mlrepa.github.io/mlrepa-library/#repa-principles), and could be interesting to the ML REPA Community (section **[Projects](https://mlrepa.github.io/mlrepa-library/resources/projects/))**.
3. Share the links to useful resources such as tutorials, posts, or papers (section [**Resources**](https://mlrepa.github.io/mlrepa-library/resources/resources/))

<br>

**Guide:**

To add your contributon you need to

1. Create and switch to the branch `4-git-fork`
2. Add your updates to
      - Roadmap: docs/repa/roadmap.md
      - Project: docs/resources/projects.md
      - Resources: docs/resources/resources.md
3. Push updates to your fork 

### **4. Create a Merge Request**

- Create a Merge Request (via GitHub UI) to the `main` branch in the parent repository

### **5. Resolving Conflicts**

When you collaborate with Git, you may often run into merge conflicts. Conflicts can arise when multiple contributors make conflicting changes to the same file. 

Fortunately, tools like VS Code can help you identify and resolve these conflicts by highlighting the differences and providing options to accept specific changes. Once resolved, you can stag the conflicting file and commit it to ensure a smooth collaboration process.

Please, take a look at the **"Helpful Guide to Merge Conflicts”** video by the VSCode team. The video:

- explains why you may get merge conflicts
- shows an approach how to resolve conflicts in VSCode IDE

<figure class="video_container">
  <iframe src="https://www.youtube.com/embed/HosPml1qkrg" frameborder="0" width="600" height="300" allowfullscreen="true" "Image Title" > </iframe>
  <figcaption>
    Helpful Guide to Merge Conflicts
    </figcaption>
</figure> 

## **🏁 Conclusion**

Congratulations on completing this tutorial! 🥳 

You learned about the importance of repository forks for contributing to open-source projects. You explored the step-by-step process of forking a project, cloning the forked repository to your local machine, making changes, pushing them to the remote fork, and making Merge Requests.

You also have known how to handle merge conflicts. Good job!

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