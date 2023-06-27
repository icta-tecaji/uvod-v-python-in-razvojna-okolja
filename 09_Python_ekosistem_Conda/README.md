# Ekosistem Conda

- [The definitive guide to Python virtual environments with conda](https://whiteboxml.com/blog/the-definitive-guide-to-python-virtual-environments-with-conda)
- [Getting Started with Conda](https://towardsdatascience.com/managing-project-specific-environments-with-conda-b8b50aa8be0e)
- [Getting started with conda](https://conda.io/projects/conda/en/stable/user-guide/getting-started.html)

## Predstavitev ekosistema Conda

![conda](./images/img02.png)

### Conda
The **package and environment manager program** bundled with Anaconda that installs and updates conda packages and their dependencies. Conda also lets you easily switch between conda environments on your local computer.

### Miniconda
A free **minimal installer for conda**. Miniconda is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib, and a few others.

> The available library catalog is the same for Anaconda and Miniconda, and there is no advantage of installing Anaconda over Miniconda (unless you want to lose 500 Mb of storage in your hard drive). Just **install Miniconda and let conda (remember, the virtual environment manager) download and install the last version of packages from the internet as needed.**

### Anaconda
A downloadable, free, **open-source, high-performance, and optimized Python and R** distribution. Anaconda includes `conda`, `conda-build`, `Python`, and **250+ automatically installed, open-source scientific packages** and their dependencies that have been tested to work well together, including SciPy, NumPy, and many others. 

> Because Anaconda is a Python distribution, it can make installing Python quick and easy even for new users.

![difference](./images/img01.png)

### Anaconda.org
A web-based, repository hosting service in the cloud. Packages created locally can be published to the cloud to be shared with others. `Anaconda.org` is a public version of Anaconda Repository and was formerly known as Anaconda Cloud.

### Anaconda Navigator
[Anaconda Navigator](https://docs.anaconda.com/free/navigator/) is a desktop graphical user interface (GUI) included in Anaconda® Distribution that allows you to launch applications and manage conda packages, environments, and channels without using command line interface (CLI) commands. Navigator can search for packages on Anaconda.org or in a local Anaconda Repository. It is available for Windows, macOS, and Linux.


## Namestitev ekosistema Conda
- [Installation](https://conda.io/projects/conda/en/stable/user-guide/install/index.html#)

The fastest way to obtain conda is to install Miniconda, a mini version of Anaconda that includes only conda and its dependencies.

**You do not need to uninstall other Python installations or packages in order to use conda.**

[Miniconda](https://docs.conda.io/en/latest/miniconda.html#) is a free minimal installer for conda. It is a small, bootstrap version of Anaconda that includes only conda, Python, the packages they depend on, and a small number of other useful packages, including pip, zlib and a few others. 

> [Anaconda or Miniconda?](https://docs.conda.io/projects/conda/en/stable/user-guide/install/download.html#anaconda-or-miniconda)

On Windows, macOS, and Linux, it is best to install Miniconda **for the local user, which does not require administrator permissions** and is the most robust type of installation.

- [Installing on Windows](https://docs.conda.io/projects/conda/en/stable/user-guide/install/windows.html)
- [Windows installers](https://docs.conda.io/en/latest/miniconda.html#windows-installers) -> Choose the Python 3.10 Miniconda3 Windows 64-bit installer. Download it.

[Verify your installer hashes.](https://conda.io/projects/conda/en/stable/user-guide/install/download.html#cryptographic-hash-verification)
- `Get-FileHash .\Miniconda3-py310_23.3.1-0-Windows-x86_64.exe -Algorithm SHA256`

**Install Miniconda on Windows:**
1. Click `Next`.
2. Read the licensing terms and click `I Agree`.
3. Select an install for “Just Me” and click `Next`.
4. Select a destination folder to install Miniconda (default is ok) and click `Next`.
5. Select the following and click `Install`:
![conda install](./images/img03.png)
6. Click `Next`.
7. Uncheck the boxes and click `Finish`.

When installation is finished, from the `Start menu`, open the `Anaconda PowerShell Prompt`.

Test your installation. Run the command `conda list`. A list of installed packages appears if it has been installed correctly.

> Is recommend that you always keep conda updated to the latest version.

- [Updating conda](https://docs.conda.io/projects/conda/en/stable/user-guide/install/windows.html#updating-conda)
- [Uninstalling conda](https://docs.conda.io/projects/conda/en/stable/user-guide/install/windows.html#uninstalling-conda)
    - `conda update conda`

## Uporaba ekosistema Conda
- [Command reference](https://docs.conda.io/projects/conda/en/stable/commands.html)

Verify that conda is installed and running on your system by typing: `conda --version`

The `conda` command is the **primary interface for managing installations of various packages**. It can:
- Query and search the Anaconda package index and current Anaconda installation.
- Create new conda environments.
- Install and update packages into existing conda environments.

### Managing environments
- [Conda environments](https://docs.conda.io/projects/conda/en/stable/user-guide/concepts/environments.html)
- [Managing environments](https://docs.conda.io/projects/conda/en/stable/user-guide/tasks/manage-environments.html)

Conda allows you to create separate environments containing files, packages, and their dependencies that will not interact with other environments.

When you begin using conda, you already have a default environment named `base`. **You don't want to put programs into your `base` environment**, though. Create separate environments to keep your programs isolated from each other.

A conda environment is **a directory that contains a specific collection of conda packages that you have installed.** For example, you may have one environment with NumPy 1.7 and its dependencies, and another environment with NumPy 1.6 for legacy testing. If you change one environment, your other environments are not affected. You can easily activate or deactivate environments, which is how you switch between them. You can also share your environment with someone by giving them a copy of your `environment.yaml` file.

1. Move to the directory where you want to create the environment: `cd <path to directory>`
2. Create a new environment:
    - `conda create --name test`
    - Type `y` and press Enter to proceed.
    - No packages will be installed in this environment.

> By default, environments are installed into the envs directory in your conda directory.

3. To use, or "activate" the new environment, type the following: `conda activate test`
4. Now that you are in your test environment, any conda commands you type will go to that environment until you deactivate it.
5. To see a list of all your environments, type: 
    - `conda info --envs`
6. To deactivate your environment, type: `conda deactivate`
    - When the environment is deactivated, its name is no longer shown in your prompt, and the asterisk (*) returns to base.
    - `conda info --envs`

> The active environment is the one with an asterisk (*).






### Conda vs. pip 
Install all the programs that you want in this environment at the same time. Installing 1 program at a time can lead to dependency conflicts.


When you create a new virtual environment, you can install Python libraries using both conda or pip. Most of the time there is no difference in installing them with conda or pip. The pip catalog is more complete, while the conda dependency resolver is more robust. Inside a conda virtual environment, you have access to both conda and pip to install libraries.

Most people think that conda is for Python, but the reality is that a conda virtual environment is a generic environment where you can install almost anything.

- https://towardsdatascience.com/managing-project-specific-environments-with-conda-b8b50aa8be0e
- https://docs.conda.io/projects/conda/en/stable/glossary.html


•	DAN 6: EKOSISTEM CONDA IN PRAKTIČEN ZAGON PROGRAMOV NA SISTEMU WINDOWS
o	
o	
o	Pregled komand in načina dela
o	Namestitev zuanjih knjižnic
o	Praktični primeri postavitve programov 

Namestitev
- http://sanger-pathogens.github.io/Artemis/ACT/

## Conda
- https://docs.conda.io/projects/conda/en/stable/index.html
- https://realpython.com/python-virtual-environments-a-primer/#the-conda-package-and-environment-manager
- https://docs.conda.io/projects/conda/en/stable/user-guide/install/windows.html

## Bioconda
- https://bioconda.github.io/