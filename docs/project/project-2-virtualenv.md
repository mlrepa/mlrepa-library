# Virtual Environments and Package Managers

## **👀 Overview**

In this module, we will explore the concepts of virtual environments and package managers in Python. We will understand the significance of packages and modules in Python programming and learn how to leverage them effectively. Additionally, we will delve into the importance of virtual environments in software development and the benefits they offer, such as isolation, reproducibility, and version control of libraries.

We will also explore different types of package managers and virtual environments, including popular tools like Pip, Virtualenv, Conda, Pipenv, and Poetry. Understanding the features and capabilities of these tools will enable us to choose the most suitable option for managing dependencies and creating isolated development environments.

## **🎯 Goals**

- Understand the concepts of packages and modules in Python.
- Learn the benefits of using virtual environments in software development.
- Explore different package managers and virtual environment tools.
- Install and utilize Pipenv as a recommended package manager and virtual environment solution.
- Create and manage virtual environments using Pipenv.
- Install and manage packages within virtual environments.
- Fix dependencies and ensure reproducibility of project environments.
- Execute Python projects within virtual environments.
- Gain practical experience by completing the seminar and homework tasks.

## **⚒️ Tutorial**

### **Packages and Modules in Python**

- In Python, a package is a directory that includes other directories and modules, and it also contains the `__init__.py` file. Packages are used to organize namespaces, allowing us to work with modules by specifying their level of nesting (using dot notation).
- A module is a file with the `.py` extension. Modules are used to store frequently used functions, classes, constants, etc. Modules can be categorized into two types: programs, which are intended for direct execution, and modules, which are intended for importing into other programs. It's worth noting that modules can be written not only in Python but also in other languages (e.g., C).

### **Why do we need virtual environments?**

- **Isolation**: An isolated environment prevents accidental interference with the functioning of other solutions.
- **Reproducibility/Portability**: A solution developed on one computer will work the same way on another computer (without errors and producing the same results).
- **Version Control**: Virtual environments allow us to fix the versions of the installed packages. This prevents automatic updates of packages and ensures that the project remains stable, even if newer versions of the packages are released.
- **Collaboration**: Virtual environments make it easier to collaborate with other developers.

**Virtual environment** is an isolated Python environment that allows us to use specific libraries and their versions in our application. These settings are independent of the system settings and restrictions on which we run our application.

A virtual environment does not fix system and driver settings; other tools, such as Docker, are used for that purpose.

### **Types of Package Managers and Virtual Environments:**

- Pip: the most common package manager.
- Virtualenv: the foundation, the very first virtual environment.
- Conda: packages + environment + compiled images.
- Pip + Virtualenv = Pipenv (recommended option).
- Poetry: a new incarnation of Pipenv (simpler dependency management).

| Features | Pip | Virtualenv | Conda | Pipenv | Poetry |
| --- | --- | --- | --- | --- | --- |
| Package management/installation | + | - | + | + | + |
| Virtual environments | - | + | + | + | + |
| Wheel support | - | - | + | + | + |
| Smart environment fixation | - | - | - | + | + |
| Dependency management | - | - | - | + | + |

## **Lifecycle of a Virtual Environment using `pipenv` (as an example)**

1. Installation (once):
    
    ```bash
    pip install --user pipenv
    ```
    
2. Activating the virtual environment:
    
    ```bash
    cd my_project
    pipenv shell # enter the virtual environment
    exit # exit the virtual environment
    ```
    
3. Installing packages within the environment:
    
    ```bash
    pipenv install pandas
    ```
    
4. Fixing the state (automatically):
    
    ```bash
    pipenv install pandas==1.1.1
    pipenv lock # Fixing the state
    ```
    
5. Running the project within the virtual environment:
    
    ```bash
    pipenv run python your_project.py
    ```
    

### **🔒 Locking the Environment with Pipenv**

- Pipfile
!!! example
        ```toml
        [[source]]
        url = "<https://pypi.org/simple>"
        verify_ssl = true
        name = "pypi"

        [packages]
        pandas = "==1.1.1"

        [dev-packages]

        [requires]
        python_version = "3.7"
        ```

- Pipfile.lock

???+ example
        ```json
        {
            "_meta": {
                "hash": {
                    "sha256": "8d14434df45e0ef884d6c3f6e8048ba72335637a8631cc44792f52fd20b6f97a"
                },
                "host-environment-markers": {
                    "implementation_name": "cpython",
                    "implementation_version": "3.6.1",
                    "os_name": "posix",
                    "platform_machine": "x86_64",
                    "platform_python_implementation": "CPython",
                    "platform_release": "16.7.0",
                    "platform_system": "Darwin",
                    "platform_version": "Darwin Kernel Version 16.7.0: Thu Jun 15 17:36:27 PDT 2017; root:xnu-3789.70.16~2/RELEASE_X86_64",
                    "python_full_version": "3.6.1",
                    "python_version": "3.6",
                    "sys_platform": "darwin"
                },
                "pipfile-spec": 5,
                "requires": {},
                "sources": [
                    {
                        "name": "pypi",
                        "url": "<https://pypi.python.org/simple>",
                        "verify_ssl": true
                    }
                ]
            },
            "default": {
                "certifi": {
                    "hashes": [
                        "sha256:54a07c09c586b0e4c619f02a5e94e36619da8e2b053e20f594348c0611803704",
                        "sha256:40523d2efb60523e113b44602298f0960e900388cf3bb6043f645cf57ea9e3f5"
                    ],
                    "version": "==2017.7.27.1"
                },
                ...
        ```

### **🔍 Inside the Pipenv Virtual Environment**

```bash
pipenv graph  # View dependency graph
pipenv --venv
```

A virtual environment is physically a folder inside the project or in a specific location where all the environment's libraries are installed. This is why external changes on the host machine do not impact the project in the virtual environment and vice versa.

### **💻 Practice: Pipenv Workshop**

- Install pipenv: `pip install --user pipenv`
- Navigate to the project folder: `cd [my_project]`
- Specify the Python version for the project: `pipenv --python 3.10.4`
- Add/remove packages: `pipenv install/uninstall <package>`
- Specify package versions: `pipenv install <package>~=1.2|>=1.2|<=1.2|<1.2`
- Activate the virtual environment: `pipenv shell | exit`
- Lock dependencies: `pipenv lock`
- Create requirements.txt: `pipenv lock -r > requirements.txt`
- Install packages from requirements.txt: `pipenv install -r requirements.txt`
- Update dependencies: `pipenv update --outdated

## **🏁 Conclusion**

- Fixing the environment saves effort and time.
- Fixing the environment is straightforward.
- We will use this approach in our projects.

## **🎓 Additional Resources**

- [Python Packaging User Guide](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/)
This guide provides an in-depth explanation of virtual environments and package management in Python, including best practices and usage examples.
- [Conda Documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html) 
This documentation offers a comprehensive guide on creating and managing environments using Conda, a popular package manager for Python and other languages. It covers topics such as creating, activating, and sharing environments.
- [Virtualenv Documentation](https://virtualenv.pypa.io/en/latest/)
This documentation focuses on the usage and benefits of Virtualenv, a widely used tool for creating isolated Python environments. It provides instructions on installation, creating virtual environments, and activating them.
- [Pipenv Documentation](https://pipenv.pypa.io/en/latest/)
This documentation introduces Pipenv, a tool that combines package management and virtual environments in a single solution. It covers the installation process, usage instructions, and advanced features like dependency resolution.

!!! info " Contribute to the community! 🙏🏻 "

    Hey! We hope you enjoyed the tutorial and learned a lot of useful techniques 🔥 
    
    Please 🙏🏻 take a moment to improve our tutorials and create better learning experiences for the whole community. You could
 
    - ⭐ **Put a star on our [ML REPA library repository](https://github.com/mlrepa/mlrepa-library)** on GitHub
    - 📣 **Share our tutorials** with others, and
    - :fontawesome-solid-paper-plane: **Fill out the [Feedback Form](https://forms.gle/Yc9DmampbwFpEzo58)**
    We would appreciate any suggestions or comments you may have

    Thank you for taking the time to help the community! 👍

![Untitled](../assets/images/Footer.png)