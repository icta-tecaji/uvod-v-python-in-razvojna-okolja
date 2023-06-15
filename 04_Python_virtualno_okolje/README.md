# Python virtualno okolje

- [Python Virtual Environments: A Primer](https://realpython.com/python-virtual-environments-a-primer/)

## Namestitev virtualnega okolja venv
Each environment can use different versions of package dependencies and Python.

[Python’s venv module](https://docs.python.org/3/library/venv.html) is part of Python’s standard library, and it’s the officially recommended way to create virtual environments since Python 3.5.

>  There are other great third-party tools for creating virtual environments, such as *conda* and *virtualenv*.

Any time you’re working on a Python project that uses external dependencies that you’re installing with pip, it’s best to first create a virtual environment:
- `python -m venv .venv`

Generally, before you start using it, you’ll first activate the environment by executing a script that comes with the installation:
- `.venv\Scripts\activate`

Once you can see the name of your virtual environment—in this case (.venv)—in your command prompt, then you know that your virtual environment is active.

After creating and activating your virtual environment, you can now install any external dependencies that you need for your project:
- `pip install requests`

Because you first created and activated the virtual environment, pip will install the packages in an isolated location.

Update the pip package manager inside the virtual environment:
- `python -m pip install --upgrade pip`

List all of the packages installed in the virtual environment:
- `pip list`

Once you’re done working with this virtual environment, you can deactivate it:
- `deactivate`

After executing the deactivate command, your command prompt returns to normal. This change means that you’ve exited your virtual environment. If you interact with Python or pip now, you’ll interact with your globally configured Python environment.

Check the list of packages installed:
- `pip list`

You can see there are no packages installed in the global environment.

If you want to go back into a virtual environment that you’ve created before, you again need to run the activate script of that virtual environment.

## Zakaj potrebujemo virtualno okolje?



## Kaj je virtualno okolje?
- pokažemo različne opcije za Python



## Uporaba in delovanje virtualnega okolja venv

- izbris venv okolja

## Praktičen primer uporabe virtualnega okolja venv
- pokažemo vse od začetka na eni novi mapi in dodamo requirements.txt datoteko in requirements-dev.txt datoteko
- https://biopython.org/wiki/Download