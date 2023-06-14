# Python knjižnice

## Kaj so Python knjižnice
- [Python Modules and Packages – An Introduction](https://realpython.com/python-modules-packages/)

**Modular programming** refers to the process of breaking a large, unwieldy programming task into **separate, smaller, more manageable subtasks or modules**. Individual modules can then be cobbled together like building blocks to create a larger application.

There are several advantages to modularizing code in a large application:
- **Simplicity**: Rather than focusing on the entire problem at hand, a module typically focuses on one relatively small portion of the problem. If you’re working on a single module, you’ll have a smaller problem domain to wrap your head around. This makes development easier and less error-prone.
- **Maintainability**: Modules are typically designed so that they enforce logical boundaries between different problem domains. If modules are written in a way that minimizes interdependency, there is decreased likelihood that modifications to a single module will have an impact on other parts of the program. This makes it more viable for a team of many programmers to work collaboratively on a large application.
- **Reusability**: Functionality defined in a single module can be easily reused (through an appropriately defined interface) by other parts of the application. This eliminates the need to duplicate code.
- **Scoping**: Modules typically define a separate namespace, which helps avoid collisions between identifiers in different areas of a program.

## Kakšni tipi knjižnic obstajajo

There are three basic kinds of modules in Python:
- **[Python Standard Library](https://docs.python.org/3/library/)** is very extensive, offering a wide range of facilities.
    - The library contains **built-in modules** (written in C) that provide access to system functionality such as file I/O that would otherwise be inaccessible to Python programmers.
    - As well as **modules written in Python** that provide standardized solutions for many problems that occur in everyday programming. They are available through the and are therefore installed with your Python installation.
- **User-defined modules** are written in Python and typically stored in files with a .py extension. The Python interpreter can import these modules from any location on the file system.
- **Third-party modules** are stored in the [Python Package Index (PyPI)](https://pypi.org/) (pronounced Pie Pea Eye) and can be installed using the pip tool.

## Package Management orodja
- [Package Management](https://realpython.com/effective-python-environment/#package-management)

For many of the projects you work on, you’ll probably need some number of third-party packages. Those packages may have their own dependencies in turn. In the early days of Python, using packages involved manually downloading files and pointing Python at them. Today, we’re fortunate to have a variety of **package management tools** available to us.

Some of the most popular package management tools are:
- [pip](https://pip.pypa.io/en/stable/) has been the de facto standard for package management in Python for several years. It’s included by default with modern distributions of Python.
- [conda](https://docs.conda.io/en/latest/) is a package manager that’s popular in the data science community. It’s included with the [Anaconda](https://www.anaconda.com/) and [Miniconda](https://docs.conda.io/en/latest/miniconda.html) Python distributions.
- [poetry](https://python-poetry.org/) is a relative newcomer to the Python package management scene. It’s a tool for managing Python dependencies and packaging Python applications.
- [pipenv](https://pipenv.pypa.io/en/latest/) has most of the same basic operations as pip but thinks about packages a bit differently. When you install a package, pipenv adds that package to Pipfile and also adds more detailed information to a new lock file called Pipfile.lock. Lock files act as a snapshot of the precise set of packages installed, including direct dependencies as well as their sub-dependencies.

## Uvod v orodje pip
- [Using Python's pip to Manage Your Projects' Dependencies](https://realpython.com/what-is-pip/)
- [Why you should use `python -m pip`](https://snarky.ca/why-you-should-use-python-m-pip/)

**[pip](https://pip.pypa.io/en/stable/) (pip installs packages) is a package manager for Python.** That means it’s a tool that allows you to install and manage libraries and dependencies that aren’t distributed as part of the standard library. The name pip was introduced by Ian Bicking in 2008. 

Package management is so important that Python’s installers have included pip since versions 3.4 and 2.7.9, for Python 3 and Python 2, respectively. Many Python projects use pip, which makes it an essential tool for every Pythonista.

You can verify that pip is available by looking for the pip executable on your system. 
- `pip --version`

> **Running pip as a Module**: When you run your system pip directly, the command itself doesn’t reveal which Python version pip belongs to. This unfortunately means that you could use pip to install a package into the site-packages of an old Python version without noticing. To prevent this from happening, you can run pip as a Python module: `python3 -m pip --version`

Upgrading pip to the latest version is very easy: `python -m pip install --upgrade pip`

## Namestitev zunanjih knjižnic s pomočjo orodja pip
One of the many packages that PyPI hosts is called [requests](https://pypi.org/project/requests/). The requests library helps you to interact with web services by abstracting the complexities of HTTP requests.

You can use the list command to **display the packages installed** in your environment, along with their version numbers:
- `pip list`

The pip list command renders a table that shows all installed packages in your current environment.

To install packages, pip provides an install command. You can run it to install the requests package: `pip install requests`

The pip command **looks for the package in PyPI, resolves its dependencies, and installs everything in your current Python environment** to ensure that requests will work. The `pip install <package>` command always looks for the **latest version of the package** and installs it. It also searches for dependencies listed in the package metadata and installs them to ensure that the package has all the requirements that it needs.
- `pip list`

The output above shows the version of the packages using an `x.y.z` placeholder format. When you run the pip list command in your environment, pip displays the specific version number that you’ve installed for each package.

To get **more information about a specific package**, you can look at the package’s metadata by using the show command in pip:
- `pip show requests`

The output of this command on your system will list the package’s metadata. The Requires line lists packages, such as certifi, idna, charset-normalizer, and urllib3. These were installed because requests depends on them to work correctly.

> By default, pip uses PyPI to look for packages. But pip also gives you the option to define a custom package index. This is useful if you have a private package index that you want to use. You can specify a custom package index by using the `--index-url` option: `pip install --index-url <URL> <package>`

You’re not limited to packages hosted on PyPI or other package indexes. pip also **provides the option to install packages from a GitHub repository**. With the `git+https` scheme, you can point to a Git repository that contains an installable package.
- `pip install git+https://github.com/realpython/rptree`

### Using Requirements Files
The pip install command always installs the latest published version of a package, but sometimes your code requires a specific package version to work correctly.

You want to create a specification of the dependencies and versions that you used to develop and test your application so that there are no surprises when you use the application in production.

These external dependencies are also called requirements. You’ll often find Python projects that pin their requirements in a file called `requirements.txt` or similar. The **requirements file format allows you to specify precisely which packages and versions should be installed.**

Create a file called `requirements.txt` and add the following content:
```
requests==2.31.0
```

When you want to replicate the environment in another system, you can run `pip install`, using the `-r` switch to specify the requirements file:
- `pip install -r requirements.txt`

Try to change the version number in the requirements file to a version `2.30.0`. Then run the `pip install -r requirements.txt` command again. You’ll see that pip installs the version that you specified in the requirements file.

You can change the comparison operator to `>=` to tell pip to install an exact or greater version that has been published. Next, you can upgrade the packages in your requirements file by running the install command with the `--upgrade` switch or the `-U` shorthand:
- `pip install -U -r requirements.txt`

If a new version is available for a listed package, then the package will be upgraded.

> In an ideal world, new versions of packages would be backward compatible and would never introduce new bugs. Unfortunately, new versions can introduce changes that’ll break your application. To fine-tune your requirements, the requirements file syntax supports additional [version specifiers](https://peps.python.org/pep-0440/#version-specifiers).

### Uninstalling Packages With pip
Notice that when you installed requests, you got pip to install other dependencies too. The more packages you install, the bigger the chance that multiple packages depend on the same dependency. This is where the show command in pip comes in handy.

Before you uninstall a package, make sure to run the show command for that package: `pip show requests`

Notice the last two fields, Requires and Required-by. The show command tells you that requests requires certifi, idna, charset-normalizer, and urllib3. You probably want to uninstall those too. Notice that requests isn’t required by any other package. So it’s safe to uninstall it.

You should run the show command against all of the requests dependencies to ensure that no other libraries also depend on them. Once you understand the dependency order of the packages that you want to uninstall, then you can remove them using the uninstall command:
- `pip uninstall certifi`
- `pip uninstall urllib3 -y` (Using the `-y` switch, you suppress the confirmation dialog asking you if you want to uninstall this package.)
- In a single command: `pip uninstall -y charset-normalizer idna requests rptree urllib3`

Use the list command to verify that the packages have been uninstalled: `pip list`.

## Kvaliteta Python knjižnic
- [How to Evaluate the Quality of Python Packages](https://realpython.com/python-package-quality/)

## Uvod v Python Wheels
- https://realpython.com/python-wheels/


## Problem nameščanja knjižnic brez virtualnega okolja
The problem with installing packages globally is that you might end up with a system that behaves differently than you expect. For example, you might have a project that depends on a specific version of a package, but another project that requires a different version. If you install both versions globally, then you’ll run into problems.

**It's not possible to install different versions of the same package globally.**

The solution to this problem is to use a virtual environment. A virtual environment is a self-contained directory tree that contains a Python installation for a particular version of Python, plus a number of additional packages.