![Untitled](images/1-cli-get-started.png)

# Command Line Interface (CLI): Get Started

## 👀 **Overview:**

This tutorial will introduce you to how to use CLI to manage files and directories. 

We will cover the basic commands for navigating your file system, creating, editing, copying, renaming, moving, and deleting files and directories using the CLI.

## 🎯 **Goals**

By the end of this tutorial, you should be able to:

- Understand the importance of using the CLI
- Navigate your file system using the CLI: create, edit, copy, rename, move, and delete files and directories

## ⚒️ **Tutorial: CLI - Get started**

### **1. Show files and directories**

Let's start with `pwd` command. It stands for “print working directory”

```bash
# Show the current working directory 
pwd
```

…and then list the directory contents with `ls` command.

```bash
# List the dir content 
ls
```

The directory may have some hidden files. They are typically used to store configuration settings, preferences, etc. And hidden files aren’t intended to be directly accessed or modified by the user on a regular basis.

With the command `ls -a`, you can list all files in a directory, including hidden files.

```bash
# Show all files including ‘hidden’ (whose names begin with a dot ‘.’) 
ls -a 
```

To list files in the long format, use the `ls` command with the `-l` argument.  This command's output will include information about permissions, ownership, file size, date and time of last modification, and the file or directory name.

```bash
# List files in the long format
ls -l 
```

To combine options, use `-la`. 

```bash
# Combine options: list all files in the long format 
ls -la 
```

To get help on `ls` command, let's use the command `man ls`. Same works for other CLI commands. 

If you need any clarification on the functionalities and options available for the `ls` command, use the command `man ls`. It stands for manual page. Same works for other CLI commands.

To come back to the CLI, press the `q` button on the keyboard.

```bash
# Show the command `Help`  (quit with `q` key)
man ls
```

### **2. Create directories and files**

To make a new directory in the current working directory, you should use the `mkdir` command followed by the directory name. For example, let’s create `demo-cli` directory.

```bash
# Make a new `demo-cli` directory 
mkdir demo-cli
```

Once the directory is created, you can move into it using the `cd` command. It stands for “change directory”

```bash
# Move into the `demo-cli` dir
cd demo-cli
```

Sometimes you might need to create a new empty file.
Let’s create a file named `file.txt` in the current directory with `touch file.txt` command.

```bash
# Create a new empty file in the working directory 
touch file.txt
```

### **3. Edit files with the `vi` / `vim` editor**

!!! Note
     For this learning part, you need to use a text editor. You can use Vi or Vim text editors, which are built-in CLI.
     
     Also, you may use another default editor on your system (like `nano`). In this case, skip this section.

Create a file

```bash
# Open a file for editing with `vi` 
vi file.txt

# Open a file for editing with `vim` 
vim file.txt
```

To edit a file in vi /vim editor: 

- Press `i` to switch to insert mode and add the text: `This is the first line`

In case you want to close the file without saving it: 

- Press `Esc` button
- Type a string `:q` (stands for ‘quit’) and press `Enter`, you will get an expected error:
`E37: No write since last change (add ! to override)`
- Add `!` mark, type a string `:q!` and press `Enter`, to close the file without saving changes

If you want to save changes made in vi / vim editor:  

- Open the file with `vi file.txt` again and add the text: `This is the first line`
- Press `Esc` button
- Type a string `:wq`
- Press `Enter`

Finally, to show the content of a file in CLI use the `cat` command with the file name, such as `file.txt`. This command stands for "concatenate." It means that `cat` command can read and display the contents of one or multiple files to the terminal.

```bash
# Show the content of the file in CLI
cat file.txt
```

### **4. Copy, rename, move, and delete files**

These code lines demonstrate how to copy, move, and delete files and directories using the command-line interface. Here are the steps:

1. Navigate to the `demo-cli` directory using `cd demo-cli`.

``` bash
# Navigate to the `demo-cli` dir
cd demo-cli
```
2. Create a copy of the `file.txt` using `cp file.txt file2.txt`.

``` bash
# Create a copy of the `file.txt` 
cp file.txt file2.txt
```
3. Move the copy to the parent directory (use **`..`**) with `mv file2.txt ..`

```bash
# Move the copy to the parent directory (us `..`)
mv file2.txt ..
```
4. Navigate to the parent directory with `cd ..` command.

```bash
# Navigate to the parent dir
cd .. 
```
5. Remove `file2.txt` using the command `rm` and the file’s name such as `file2.txt`

```bash
# Remove `file2.txt` 
rm file2.txt
```
6. Remove the `demo-cli` directory and all its contents using `rm -rf demo-cli`.

```bash
# Remove `demo-cli` dir
rm -rf demo-cli
```
### **5. Сheat sheet with commands**

**CLI commands**

| Command | Action |
| --- | --- |
| mkdir | Creates a new folder |
| rm | Removes a file or directory |
| cd | Changes to another location in your filesystem |
| ls | Lists the files in the current directory |
| pwd | Prints working directory |
| cat | Prints in the current screen the content of a file |
| mv | Moves or rename files |

**Vi/Vim editor commands**

| Command | Action |
| --- | --- |
| :i | Press i to switch to insert mode |
| :w | After making changes to a file, press [Esc] to shift to the command mode and press :w and hit [Enter] to save a file. |
| :q | To exit Vi/Vim, use the :q command and hit [Enter] |
| :wq / :x | To save a file and exit Vi/Vim simultaneously, use the :wq command and hit [Enter] or :x command |
| :q! | To force this action, use ESC and :q! |

## 🏁 **Conclusion**

Congratulations on completing this tutorial! 🥳 
By now, you should have a solid understanding of the importance of using the CLI in machine learning development and should be able to navigate your file system using CLI commands. You have also learned how to create, edit, and delete files and directories using the CLI.

Keep practicing and honing your skills with the CLI, and don't hesitate to explore new commands and techniques. With time and practice, you will become a CLI expert! 🙌🏻

## 🎓 **Additional Resources**

- [Machine Learning REPA Library](https://mlrepa.github.io/mlrepa-library/)
- [Unix Tutorial for Beginners](https://www.ee.surrey.ac.uk/Teaching/Unix/)
- [Learn Enough Command Line to Be Dangerous](https://www.learnenough.com/command-line-tutorial)
- [Introduction to the Unix Shell](https://swcarpentry.github.io/shell-novice/)

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could

    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub 
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍

![Untitled](images/footer.png)