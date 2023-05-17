![Untitled](images/dvc-2.png)

# Data Versioning with DVC

## **👀 Overview**

This tutorial provides a detailed demonstration of approaches to data and model versioning.

🧑‍💻 [Repository for this tutorial](https://github.com/mlrepa/dvc-2-data-versioning)

!!! note "Important"
    - Instructions for setting up the environment are in the repository's README.

## **🎯 Goals**

- Overview Data Versioning features and use cases of DVC

## **Tutorial: Data Versioning with DVC**

### **Installation**

To conveniently view the structure of files and directories in the terminal, the `tree` utility can be useful. Here's how to install it on Linux:

1. Open the terminal.
2. Ensure that your system has internet access.
3. Enter the following command to install `tree`:
    
    ```bash
    # for Linux 
    sudo apt-get install tree
    
    # for Mac
    brew install tree
    ```

4. When prompted, enter the administrator (root) password.

5. Wait for the installation to complete.

    Once the installation is finished, you can use the `tree` command to view the structure of files and directories in the terminal. Here's an example usage:

        tree <directory_path>
        
    Replace `<directory_path>` with the path to the directory you want to view.

### **Prepare repository**

To clone the example repository "dvc-2-data-versioning," you can follow these steps:

```bash
git clone https://github.com/mlrepa/dvc-2-data-versioning.git
```

Checkout branch `tutorial`

```bash
git checkout -b tutorial
```

Initialize DVC

```bash
dvc init
git add .dvc
git commit -m "DVC init"
```

### **How data versioning works?**

To understand how data versioning works in DVC, let's perform the following steps:

1. Check the status of the DVC project by running the following command:
    
    ```bash
    dvc status
    ```
2. Add a file under DVC control:
    
    Download a file and add it under DVC control using the `dvc add` command. The `-v` flag will display more detailed logs, allowing you to peek under the hood of what's happening.
    
    ```bash
    # Download the data file
    get https://github.com/iterative/dataset-registry	get-started/data.xml -o data/data.xml
    
    # Add the data file under DVC control
    dvc add data/data.xml -v
    ```    
3. Commit the changes to Git:
    
    After adding the file under DVC control, we need to commit the changes to Git.
    
    ```bash
    git add data/.gitignore data/data.xml.dvc
    git commit -m "Add raw data"
    ```
4. Explore the DVC cache:
    
    You can examine the DVC cache directory and observe the cached file.
    
    ```bash
    # Examine the DVC cache directory
    ls .dvc/cache
    
    # Check the disk usage of the cached file
    du -sh .dvc/cache/*/*
    ```    
5. Examine the `.dvc` file:

    ```bash
    cat data/data.xml.dvc
    ```

### **Add a directory under version control**

Adding directories under version control in DVC follows a similar process as adding files. The main difference lies in how the metadata is stored, but we don't need to worry about those details as DVC takes care of it.

Let's go through an example:

```bash
git checkout -b cats-dogs-v1
```

For this example, let's test the concept of a Data Registry. DVC allows us to use Git repositories for centralized data management. We can fetch the required version of the data by specifying a Git revision (`--rev`), such as a branch name, commit hash, or tag.

```bash
# Download the cats-dogs dataset
dvc get --rev cats-dogs-v1 \\
    <https://github.com/iterative/dataset-registry> \\
    use-cases/cats-dogs -o datadir

```

You can explore the downloaded dataset:

```bash
ls datadir/data/train/cats
```

Now let's add the `datadir` directory under DVC control:

```bash
dvc add datadir
```

You can examine the `.dvc` file associated with the `datadir` directory:

```bash
cat datadir.dvc
```

Ensure that the changes are reflected in Git:

```bash
git status
```

To preserve the metadata in the Git history, it's crucial to make a commit:

```bash
git add .gitignore datadir.dvc
git commit -m "Add datadir"
git tag -a cats-dogs-v1 -m "Create data version v1"
```

By following these steps, you can add a directory to DVC, track its metadata, and associate it with a specific version of the data in Git.

### **Tracking changes**

**Track data status changes**

To track the status of the data, you can use the following command:

```bash
dvc status
```

**Updating Tracking Files**

Let's switch to another branch and update the data by fetching the `cats-dogs-v2` version from the Data Registry:

```bash
git checkout -b cats-dogs-v2

```

For the sake of the experiment, let's remove the current version of the data:

```bash
rm -rf datadir/cats-dogs

```

Now, let's fetch the new data:

```bash
dvc get --rev cats-dogs-v2 \\
    <https://github.com/iterative/dataset-registry> \\
    use-cases/cats-dogs -o datadir
```

Check the status of the tracked data:

```bash
dvc status
```

Add the updated data directory under DVC control and make a commit:

```bash
dvc add datadir
```

Check the Git status:

```bash
git status
```

Add the `.dvc` file and make a commit:

```bash
git add datadir.dvc
git commit -m "Change data"
git tag -a cats-dogs-v2 -m "Create data version v2"
```

### **Switching versions**

Now, let's explore how to switch between different versions of the data:

- `git checkout` switches to the desired Git branch.
- `dvc checkout` fetches the desired version of the data.

**Checkout to the initial branch `tutorial`**

```bash
git checkout tutorial
dvc checkout
```

```bash
# The `datadir` directory is not presented here!
ls
```

**Switch to the first version of the Cats&Dogs data (branch cats-dogs-v1)**

```bash
# Checkout to the cats-dogs-v1 branch
git checkout cats-dogs-v1
```

```bash
# Still, there is no `datadir` directory. Why?
ls
```

```bash
# DVC can show the status and why the 'datadir' directory is missing
dvc status
```

```bash
# To bring back the 'datadir' directory, we need to execute `dvc checkout`
dvc checkout
```

```bash
ls
dvc status
```

By following these steps, you can track changes to your data, update the tracked files, and switch between different versions of the data using Git and DVC.

### **Store and share data with Remote Storage**

**Setup your remote storage (local)**

!!! note "Important"
    - We are using the `/tmp` directory in the examples of this tutorial for simplicity purposes only.
    - DO NOT use the `/tmp` directory for long-term storage of files. Your system frequently clears this directory.

Create new remote

```bash
mkdir -p /tmp/dvc
dvc remote add -d local /tmp/dvc
```

Note: The `-d` flag makes the local remote the default choice. 

As you can see, .dvc/config is changed

```bash
git status -s
```

```bash
# Check config file

cat .dvc/config
```

Commit changes to Git

```bash
git add .
git commit -m "Add remote storage"
```

Now, you have set up a local remote storage in DVC. This allows you to push and pull data and models to and from the specified directory. 


!!! note "Remember"
    This is a local setup, and you should consider using remote storage solutions for real-world scenarios to ensure data durability and accessibility.

### **Push data to remote storage**

To push your data to the remote storage, use the following command:

```
dvc push -v
```

This command pushes the data to the remote storage specified in the DVC configuration. You can verify the changes by examining the `.dvc` file associated with the data:

```
cat datadir.dvc
```

Additionally, you can check the contents of the remote storage directory, `/tmp/dvc/42` in this example:

```
ls /tmp/dvc/42
```

### **Retrieve data from remote storage**

To retrieve the data from the remote storage, follow these steps:

1. Remove the locally cached file and data directory:
    
    ```bash
    rm -rf .dvc/cache
    rm -rf datadir
    ```    
2. Verify that the data directory is no longer present:
    
    ```bash
    ls
    ```   
3. Pull the data from the remote storage:
    
    ```bash
    dvc pull -v
    ```    
4. Verify that the data directory has been retrieved:
    
    ```bash
    ls
    ```
    

By performing these steps, you can push your data to a remote storage location and retrieve it whenever needed using DVC commands.

### **Data Access**

**Find a dataset**

You can use the `dvc list` command to explore the DVC registry hosted on any Git server. 

For example, let's see what is available in the `use-cases/` directory of the `https://github.com/iterative/dataset-registry` repository:

```bash
dvc list <https://github.com/iterative/dataset-registry> use-cases
```

**Download a dataset with `dvc get`**

The `dvc get` command allows you to download a dataset to your working area without DVC control. It fetches the dataset from the specified location:

```
dvc get <https://github.com/iterative/dataset-registry> use-cases/cats-dogs
```

After running this command, you will see the downloaded `cats-dogs/` folder, but it is not under DVC control. There won't be a `cats-dogs.dvc` file.

**Download and track dataset `dvc import`**

The `dvc import` command downloads a dataset and automatically starts tracking its version with DVC. It allows you to easily update the dataset in your project when changes are made in the Data Registry. Note that the `dvc import` command first clones the repository using SSH. Make sure to follow the [instructions to set up SSH keys for your repository](https://docs.github.com/en/authentication/connecting-to-github-with-ssh).

```
dvc import git@github.com:iterative/example-get-started data/data.xml
```

After running this command, you will see the newly downloaded `data.xml` file, and a corresponding `data.xml.dvc` file is created, indicating that DVC is tracking the data file.

By using these commands, you can find datasets available in the DVC registry, download datasets to your working area, and add them under DVC control for versioning and management.

## **🏁 Conclusion**

In this tutorial, we explored the concept of data versioning using DVC (Data Version Control). We learned how to initialize DVC in a project, add files and directories under version control, track changes to the data, and switch between different versions of the data. We also saw how to set up a local remote storage and push data to it, as well as retrieve data from the remote storage. Additionally, we discovered how to access datasets from the DVC registry using commands like `dvc get` and `dvc import`.

Data versioning with DVC provides several benefits for data scientists and machine learning engineers. It allows for easy tracking of data changes, collaboration among team members, reproducibility of experiments, and efficient management of large datasets. By combining Git and DVC, you can have a comprehensive version control system for both your code and data.

Start using DVC in your data science projects to keep track of your data, manage different versions, and collaborate effectively with your team.

## **🎓 Additional Resources**

To further enhance your understanding of data versioning with DVC, consider exploring the following resources:

1. [DVC Documentation](https://dvc.org/doc/start): The official documentation provides comprehensive information on using DVC and its various features.
2. [DVC YouTube Channel](https://www.youtube.com/c/DVCorg): The official DVC YouTube channel hosts a collection of video tutorials and demos to deepen your knowledge of DVC.
3. [DVC Community Forum](https://discuss.dvc.org/): Join the DVC community forum to engage with other users, ask questions, and share your experiences with DVC.

By leveraging these additional resources, you can continue to build your expertise in data versioning with DVC and unlock its full potential for your data science projects.

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could
 
    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍

![Untitled](../assets/images/Footer.png)