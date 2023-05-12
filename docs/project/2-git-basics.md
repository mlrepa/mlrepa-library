![Untitled](images/2-git-basics.png)


# Basic Git commands

## 👀 **Overview**

In this tutorial, we will cover the basic Git commands that are essential for managing your machine learning project. 

We will learn how to create a new Git repository, how to check the status of the repository, stage changes for commit, commit changes to the repository, and how to view the commit history.

## 🎯**Goals**

By the end of this tutorial, you will be able to:

- Create a new Git repository for your machine learning project
- Check the status of your repository using `git status`
- Stage changes for commit using `git add`
- Commit changes to the repository using `git commit`
- View the commit history using `git log`


## **⚒️ Tutorial: Basic Git commands**

## **1. Git - Basics**

This example demonstrates the basics of using Git to create a repository and make changes to the code.

  1. First, a new directory is created with the `mkdir` command, and the user navigates into the directory with `cd`. 

    ```bash
    # Create a Git repo
    mkdir git-demo && cd git-demo
    ```
2. Then, Git is initiated in the directory with the `git init` command.

    ```bash
    # Initiate Git repo
    git init 
    ```
3. Next, a new file called `file.txt` is created using the `touch` command, and the string "Hello Git!" is added to the file using the `echo` command. 
The contents of the file are then printed to the console using the `cat` command.

    ```bash
    # Update code: update 
    touch file.txt 
    echo "Hello Git!" >> file.txt
    cat file.txt 
    ```
4. After making changes to the code, check the status of the Git repository with `git status`. Git recognises that a new file has been created and prompts the user to add the file to the staging area. 
The file is added to the staging area with `git add`, and a commit message is added with `git commit -m` to save the changes to the repository.

    ```bash
    # Check Git status and save updates
    git status 
    git add file.txt 
    git commit -m "My first Git commit"
    ```
5. Finally, the user can view the Git history with **`git log`**, which displays a list of all the commits made to the repository, including the most recent commit with the commit message "My first Git commit".

    ```bash
    # View git history with `git log` 
    git log
    ```

## **2.  Branching and merging**

Follow step by step tutorial to practice branching and merging

1. `git branch dev`: This command creates a new branch called "dev" within your Git repository. A branch in Git is essentially a snapshot of your code at a certain point in time that you can work on independently from other branches.

    ```bash
    # Create a branch
    git branch dev
    ```
2. `git checkout dev`: 
   This command switches you to the "dev" branch that you just created. Now any changes you make will be made to this branch instead of the main branch.

    ```bash
    # Checkout to a new branch
    git checkout dev
    ```
3. `echo "My second commit" >> file.txt`: This command appends the string "My second commit" to the end of the file "file.txt". This is just an example change to demonstrate the concept of making changes to a branch.
    
    `cat file.txt`: This command simply prints out the contents of the file "file.txt" to the terminal.

    `git add . && git commit -m "Update file.txt: add a new line"`: These two commands add any changes you've made to the "dev" branch to the staging area and then commit those changes to the branch with a message that describes the changes you made. 

        ```bash
        # Update and commit
        echo "My second commit" >> file.txt
        cat file.txt 
        git add . && git commit -m "Update file.txt: add a new line"
        ```
4 - `git checkout main`: This command switches you    back to the "main" branch.

    `cat file.txt`: This command prints out the contents of the file "file.txt" on the main branch. Notice that the changes you made on the "dev" branch are not reflected here yet.

    `git merge dev`: This command merges the changes you made on the "dev" branch into the "main" branch. Git will automatically attempt to merge the changes together, but if there are conflicts (e.g. you made changes to the same line of code on both branches), you'll need to manually resolve them. After the merge is complete, you'll see the changes you made on the "dev" branch reflected on the "main" branch.

    `cat file.txt`: This command prints out the contents of the file "file.txt" on the main branch again, now with the changes from the "dev" branch merged in.

        ```bash
        # Merge a `dev` branch to `main`
        git checkout main 
        cat file.txt

        git merge dev
        cat file.txt
        ```
<br>

If you still have questions about basic Git commands we can recommend you this video:

<br>

<figure class="video_container">
  <iframe src="https://www.youtube.com/embed/8JJ101D3knE" frameborder="0" width="600" height="300" allowfullscreen="true" "Image Title" > </iframe>
  <figcaption>
    Git Tutorial for Beginners: Learn Git in 1 Hour
    </figcaption>
</figure> 


## **🏁 Conclusion**

Congratulations on completing this tutorial! 🥳 

You have learned how to create a new Git repository, how to check the status of the repository, stage changes for commit, commit changes to the repository, and how to view the commit history. 

See you soon!

## 🎓 **Additional Resources**

- **[Git Tutorial for Beginners: Learn Git in 1 Hour](https://www.youtube.com/watch?v=8JJ101D3knE&list=RDLV2ReR1YJrNOM&index=4)** 
- **[Git documentation](https://git-scm.com/doc)**
- **[Git cheat sheet](https://education.github.com/git-cheat-sheet-education.pdf)**

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could

    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub 
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍

![Untitled](images/footer.png)