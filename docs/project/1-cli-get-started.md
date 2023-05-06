![Untitled](static/banner.png)
<!-- 1-cli-get-started -->

# Command Line Interface (CLI): Get Started

## 👀 **Overview:**

This module will introduce you to how to use CLI to manage files and directories. 

We will cover the basic commands for navigating your file system, creating, editing, copying, renaming, moving, and deleting files and directories using the CLI.

## 🎯 **Tasks and Goals**

By the end of this module, you should be able to:

- Understand the importance of using the CLI
- Navigate your file system using the CLI
- Create, edit, and delete files and directories using the CLI3

## ⚒️ **Tutorial: CLI - Get started**

### **1. Show files and directories**

Let's show the current working directory with **`pwd`** command, 

``` bash
# Show the current working directory 
pwd
```

``` bash
# List the dir content 
ls
```

To show the hidden files (files whose names begin with a dot **`.`**), use the option **`-a`** with the **`ls`** command. 

```bash
# Show `hidden` files (whose names begin with a dot ‘.’)
ls -a 
```

To get help on **`ls`** command, let's use the command **`man ls`**. Same works for other CLI commands. 

``` bash
# Show the command `Help`  (quit with `q` + Enter)
man ls
```

To list files in the long format, use the option **`-l`**with the **`ls`** command. 

```bash
# List files in the long format
ls -l 
```

To combine options, use **`-la`**. 

```bash
# Combine options: list all files in the long format 
ls -la 
```

Finally, to show the content of a file, use the **`cat`** command followed by the filename, such as **`.hidden-file`**.

```bash
# Show the content of the file
cat .hidden-file
```

### **2. Create files and directories**

To create a new **`demo-cli`** directory, you should use the **`mkdir`** command followed by the directory name. 

```bash
# Create a new `demo-cli` directory 
mkdir demo-cli
```

Once the directory is created, you can navigate it using the **`cd`** command. 

```bash
# Navigate to the `demo-cli` dir
cd demo-cli
```

After navigating to the **`demo-cli`** directory, you can create a new file named **`file.txt`** using the **`vi`** editor. 

```bash
# Create a file with `vi/vim` or `touch` 
touch file1.txt
vi file2.txt
```

!!! note "Note"

    You may have another default editor on your system (like `nano` ). In this case, you may use it, and skip the next section.



### 3. **Edit files with the `vi` / `vim` editor**

1. Create a file with `vim file.txt`
2. (in vim editor) Press `i` to switch to insert mode and add the text:
`This is the first line`
3. (in vim editor) Close the file without saving: press `Esc`...
    - type `:q` and press `Enter` , you get an expected error:
    `E37: No write since last change (add ! to override)`
    - type `:q!` and press [Enter], close the file without saving changes
4. Open file with `vim file.txt` again and add the text:
`This is the first line`
5. Save results and close the file: press ++esc++, type `:wq`, press ++enter++


### 4. **Copy, rename, move, and delete files**

These code lines demonstrate how to copy, move, and delete files and directories using the command-line interface. Here are the steps:

1. Navigate to the **`demo-cli`** directory using **`cd demo-cli`**.

``` bash
# Navigate to the `demo-cli` dir
cd demo-cli
```

2. Create a copy of the **`file.txt`** using **`cp file.txt file2.txt`**.

``` bash
# Create a copy of the `file.txt` 
cp file.txt file2.txt
```

3. Move the copy to the parent directory (use **`..`**) with **`mv file2.txt ..`**.

```bash
# Move the copy to the parent directory (us `..`)
mv file2.txt ..
```

4. Navigate to the parent directory with **`cd ..`** command.

```bash
# Navigate to the parent dir
cd .. 
```

1. Remove **`file2.txt`** using the command **`rm`** and the file’s name such as **`file2.txt`**

```bash
# Remove `file2.txt` 
rm file2.txt
```

5. Remove the **`demo-cli`** directory and all its contents using **`rm -rf demo-cli`**.

```bash
# Remove `demo-cli` dir
rm -rf demo-cli
```

## 🏁 **Conclusion**

Congratulations on completing this module! 🥳 
By now, you should have a solid understanding of the importance of using the CLI in machine learning development and should be able to navigate your file system using CLI commands. You have also learned how to create, edit, and delete files and directories using the CLI.

Keep practicing and honing your skills with the CLI, and don't hesitate to explore new commands and techniques. With time and practice, you will become a CLI expert! 🙌🏻

## 🎓 **Additional Resources**

- [TODO: add the link] Machine Learning REPA School: extended materials with practice, assessment, and feedback 
- [Unix Tutorial for Beginners](https://www.ee.surrey.ac.uk/Teaching/Unix/)
- [Learn Enough Command Line to Be Dangerous](https://www.learnenough.com/command-line-tutorial)
- [Introduction to the Unix Shell](https://swcarpentry.github.io/shell-novice/)

!!! info " Share Your Feedback! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques. We would like to hear from you about your experience with this tutorial. Your feedback is important and helps us improve and create better learning experiences for the whole community. 

    Please take a moment to fill out our feedback form and let us know what you think about the module. We would appreciate any suggestions or comments you may have on how we can improve our tutorials.

    Link to feedback form: **[Feedback Form](insert link here)**

    Thank you for taking the time to share your thoughts with us! 👍

![Untitled](static/footer.png)