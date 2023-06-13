![Untitled](images/2-git-basics.png)


# Basic Git commands

## 👀 **Overview**

In this tutorial, we will cover the basic Git commands that are essential for managing your machine learning project. 

We will learn how to create a new Git repository, how to check the status of the repository, stage changes for commit, commit changes to the repository, and how to view the commit history.

## 🎯**Goals**

By the end of this module, you will be able to:

- Create a new Git repository for your machine learning project
- Check the status of your repository using the `git status`
- Stage changes for commit using `git add`
- Commit changes to the repository using `git commit`
- View the commit history using `git log`

## **⚒️ Tutorial: Basic Git commands**

### **1. Create a Git repository**

This example demonstrates the basics of using Git to create a repository and make changes to the code.

First, create a new directory called `git-demo` using the `mkdir` command, and navigate into this directory using `cd`, all in one line.

```bash
# Create a Git repo
mkdir git-demo && cd git-demo
```

Then, initialize Git in the created directory using the `git init` command.

```bash
# Initiate Git repo
git init
```

This command creates a new empty Git repository in the current directory.
Additionally, `git init` automatically creates a hidden directory called `.git`. In this directory, there are:

- staging area, a file with the information about the changes that will be included in the next commit,
- metadata and object database of your project, including version snapshots.

These components allow Git to keep track of changes, manage branches, and facilitate version control throughout the development process.

### **2. Save (commit) changes**

Next, create a new file called `file.txt` using the `touch` command, and add the string "Hello Git!" using the `echo` command.
Print the file content to the console using the `cat` command.

```bash
# Create and change a file, print its content
touch file.txt 
echo "Hello Git" >> file.txt
cat file.txt 
```

After making changes to the code, check the status of the Git repository with `git status`.

Git recognizes that you created a new file and prompts you to add the file to the staging area.

To add the file to the staging area use the `git add` command.
Then, add a commit message with `git commit -m` to save the changes to the repository.

```bash
# Check Git status and save updates
git status 
git add file.txt 
git commit -m "My first Git commit"
```

Finally, you can view the Git history with the `git log`, which displays a list of all the commits made to the repository, including the most recent commit with the commit message "My first Git commit".

```bash
# View git history 
git log  
```

You may find it helpful to use the `--oneline` argument when viewing logs, as it provides a more compact representation of the commit history.

!!! Note
     To exit the `git log` viewing session, simply press the `q` key on your keyboard.

### **3.  Branching**

First, you need to create a new branch within your Git repository. A branch in Git is essentially a snapshot of your code at a certain point in time that you can work on independently from other branches. Use the `git branch dev` command to create a branch called 'dev'.

```bash
# Create a branch
git branch dev
```

Then, switch to the "dev" branch that you just created using the `git checkout dev` command. Now any changes you make will be made to this branch instead of the main branch.

Alternatively, you can create a branch and switch to it at once using the `git checkout -b dev` command.

```bash
# Checkout to a new branch
git checkout dev

# Create and checkout to a new branch
git checkout -b dev
```

After switching to a new branch, let's make some changes. For example, append the string "My second commit" to the end of the file "file.txt" using the `echo "My second commit" >> file.txt` command. This is just an example of a change to demonstrate the concept of making changes to a branch.

To check that you have made changes, use the `cat file.txt` command. This command simply prints out the contents of the 'file.txt' file to the terminal.

The next important step is to add any changes you've made to the "dev" branch to the staging area and then commit those changes to the branch with a message that describes the changes you made. For this, use the `git add . && git commit -m "Update file.txt: add a new line"` command.

```bash
# Update and commit
echo "My second commit" >> file.txt
cat file.txt 
git add . && git commit -m "Update file.txt: add a new line"
```
!!! Note
     Remember that to merge changes from another branch into the main branch in Git, you need to be in the main branch.

So, don’t forget to switch back to the "main" branch using the `git checkout main` command.

To check that you have made changes, use the `cat file.txt` command. Notice that the changes you made on the "dev" branch are not reflected here yet.

### **4. Merging**

Merge the changes you made on the "dev" branch into the "main" branch using the `git merge dev` command. Git will automatically attempt to merge the changes together, but if there are conflicts (e.g., you made changes to the same line of code on both branches), you'll need to manually resolve them. After the merge is complete, you'll see the changes you made on the "dev" branch reflected on the "main" branch.

And finally, print out the contents of the file "file.txt" on the main branch again with the `cat file.txt` command, now with the changes from the "dev" branch merged in.

```bash
# Merge a `dev` branch to `main`
git checkout main 
cat file.txt

git merge dev
cat file.txt
```

If you still have questions about basic Git commands we recommend you this video:

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

- **[Git Tutorial for Beginners: Learn Git in 1 Hour](https://www.youtube.com/watch?v=8JJ101D3knE&list=RDLV2ReR1YJrNOM&index=5)** 
- **[Git documentation](https://git-scm.com/doc)**
- **[Using Git source control in VS Code](https://code.visualstudio.com/docs/sourcecontrol/overview)**
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