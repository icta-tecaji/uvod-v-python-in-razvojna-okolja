# Priprava razvojnega okolja

## Pregled integriranih razvojnih okolji

- [Python IDEs and Code Editors (Guide)](https://realpython.com/python-ides-code-editors-guide/)

An **IDE (or Integrated Development Environment)** is a program dedicated to software development. As the name implies, IDEs integrate several tools specifically designed for software development. These tools usually include:

- An editor designed to handle code (with, for example, syntax highlighting and auto-completion)
- Build, execution, and debugging tools
- Some form of source control

Most IDEs support many different programming languages and contain many more features. They can, therefore, be large and take time to download and install. You may also need advanced knowledge to use them properly.

In contrast, a dedicated **code editor** can be as simple as a text editor with syntax highlighting and code formatting capabilities. Most good code editors can execute code and control a debugger. The very best ones interact with source control systems as well. Compared to an IDE, a good dedicated code editor is usually smaller and quicker, but often less feature rich.

**Requirements for a Good Python Coding Environment**:

- **Save and reload code files**: If an IDE or editor won’t let you save your work and reopen everything later, in the same state it was in when you left, it’s not much of an IDE.
- **Run code from within the environment**: Similarly, if you have to drop out of the editor to run your Python code, then it’s not much more than a simple text editor.
- **Debugging support**: Being able to step through your code as it runs is a core feature of all IDEs and most good code editors.
- **Syntax highlighting**: Being able to quickly spot keywords, variables, and symbols in your code makes reading and understanding code much easier.
- **Automatic code formatting**: Any editor or IDE worth it’s salt will recognize the colon at the end of a while or for statement, and know the next line should be indented.

**General Editors and IDEs with Python Support**:

- [Visual Studio Code](https://code.visualstudio.com/): Not to be confused with full Visual Studio, Visual Studio Code (aka VS Code) is a full-featured code editor available for Linux, Mac OS X, and Windows platforms. Small and light-weight, but full-featured, VS Code is open-source, extensible, and configurable for almost any task.
- [PyCharm](https://www.jetbrains.com/pycharm/): One of the best (and only) full-featured, dedicated IDEs for Python is PyCharm. Available in both paid (Professional) and free open-source (Community) editions, PyCharm installs quickly and easily on Windows, Mac OS X, and Linux platforms.
- [Sublime Text](http://www.sublimetext.com/): Written by a Google engineer with a dream for a better text editor, Sublime Text is an extremely popular code editor. Supported on all platforms, Sublime Text has built-in support for Python code editing and a rich set of extensions (called packages) that extend the syntax and editing features.
- [Atom](https://atom.io/): Available on all platforms, Atom is billed as the “hackable text editor for the 21st Century.” With a sleek interface, file system browser, and marketplace for extensions, open-source Atom is built using Electron, a framework for creating desktop applications using JavaScript, HTML, and CSS. Python language support is provided by an extension that can be installed when Atom is running.

## Namestitev VSCode in uporaba

- [Python Development in Visual Studio Code](https://realpython.com/python-development-visual-studio-code/)
- [Setting Up VS Code](https://realpython.com/python-coding-setup-windows/#setting-up-vs-code)
- [Advanced Visual Studio Code for Python Developers](https://realpython.com/advanced-visual-studio-code-python/)
- [Setting Up VSCode For Python: A Complete Guide](https://www.datacamp.com/tutorial/setting-up-vscode-python)
- [Getting Started with Python in VS Code](https://code.visualstudio.com/docs/python/python-tutorial)

Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux. It comes with built-in support for JavaScript, TypeScript and Node.js and has a rich ecosystem of extensions for other languages and runtimes (such as C++, C#, Java, Python, PHP, Go, .NET).

[Download Visual Studio Code](https://code.visualstudio.com/Download) and install it on your computer.

At its heart, Visual Studio Code is a code editor. Like many other code editors, VS Code adopts a common user interface and layout of an explorer on the left, showing all of the files and folders you have access to, and an editor on the right, showing the content of the files you have opened.

![VSCode User Interface](https://code.visualstudio.com/assets/docs/getstarted/userinterface/hero.png)

By starting VS Code in a folder, that folder becomes your "workspace".

Using a command prompt or terminal, create an empty folder called "hello", navigate into it, and open VS Code (`code`) in that folder (`.`) by entering the following commands:

```
mkdir hello
cd hello
code .
```

> Alternately, you can create a folder through the operating system UI, then use VS Code's File > Open Folder to open the project folder.

Install the **Python extension for Visual Studio Code** from the [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-python.python).

A best practice among Python developers is to use a project-specific virtual environment.

- Be sure you are in the "hello" folder you created above.
- Create a virtual environment: `python -m venv .venv`
- Activate the virtual environment: `.venv\Scripts\activate`
- Upgrade pip in the virtual environment: 
    - `python -m pip install --upgrade pip`
    - `pip install --upgrade setuptools`

Open the Command Palette (`Ctrl+Shift+P`), start typing `Python: Select Interpreter` command from the Command Palette. Select the Python interpreter associated with the virtual environment you created above (ex. `Python 3.11.3 ('.venv':'.venv')`).

> If you don't see the virtual environment you created above, you may need to restart VS Code.

From the File Explorer toolbar, select the New File button on the hello folder. Name the file `hello.py`, and VS Code will automatically open it in the editor.

Now that you have a code file in your Workspace, enter the following source code in `hello.py`:

```python
msg = "Roll a dice"
print(msg)
```

When you start typing print, notice how IntelliSense presents auto-completion options.

Click the **Run Python File in Terminal** play button in the top-right side of the editor.

Return to the Explorer view (the top-most icon on the left side, which shows files), open `hello.py`, and paste in the following source code:

```python
import numpy as np

msg = "Roll a dice"
print(msg)

print(np.random.randint(1,9))
```

Create the `requirements.txt` file in the root of the project folder (`hello`) and add the following content:

```
numpy==1.25.0
```

Install the dependencies: `pip install -r requirements.txt`

Click the **Run Python File in Terminal** play button in the top-right side of the editor.

> [Keyboard shortcuts for Windows](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)

Install the following extensions for VS Code:

- [Pylance](https://marketplace.visualstudio.com/items?itemName=ms-python.vscode-pylance)
- [isort](https://marketplace.visualstudio.com/items?itemName=ms-python.isort)
- [Flake8](https://marketplace.visualstudio.com/items?itemName=ms-python.flake8)
- [Black Formatter](https://marketplace.visualstudio.com/items?itemName=ms-python.black-formatter)
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)

Not all packages that you install during the development of your applications will be production dependencies. For example, you’ll probably want to test your application, so you need a test framework. A popular framework for testing is pytest. You want to install it in your development environment, but you don’t want it in your production environment, because it isn’t a production dependency.

You create a second requirements file, `requirements_dev.txt`, to list additional tools to set up a development environment:
```
wheel

-r requirements.txt

flake8
black
isort
```

Install the dependencies: `pip install -r requirements_dev.txt`

Create a `.vscode` folder in the project root. In the new folder create a file `settings.json`:

```json
{
  "python.analysis.typeCheckingMode": "basic",
  "python.analysis.diagnosticMode": "workspace",
  "python.linting.pylintEnabled": false,
  "python.linting.enabled": true,
  "python.linting.flake8Enabled": true,
  "python.linting.flake8Args": ["--max-line-length=160"],
  "python.formatting.provider": "none",
  "python.linting.lintOnSave": true,
  "editor.codeActionsOnSave": {
    "source.organizeImports": true
  },
  "[python]": {
    "editor.defaultFormatter": "ms-python.black-formatter",
    "editor.formatOnSave": true
  }
}
```

Try to save the file `hello.py` and see what happens.

## Namestitev in uporaba Jupyter Notebook
- [The Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/stable/)
- [Jupyter Notebook: An Introduction](https://realpython.com/jupyter-notebook-introduction/)
- [Installing Jupyter](https://jupyter.org/install)
- [How to Use Jupyter Notebooks: The Ultimate Guide](https://www.datacamp.com/tutorial/tutorial-jupyter-notebook)
- [How to Use Jupyter Notebook: A Beginner’s Tutorial](https://www.dataquest.io/blog/jupyter-notebook-tutorial/)
- [Tutorial: Advanced Jupyter Notebooks](https://www.dataquest.io/blog/advanced-jupyter-notebooks-tutorial/)
- [28 Jupyter Notebook Tips, Tricks, and Shortcuts](https://www.dataquest.io/blog/jupyter-notebook-tips-tricks-shortcuts/)

The Jupyter Notebook is an open source web application that you can use to create and share documents that contain live code, equations, visualizations, and text. Jupyter Notebook is maintained by the people at Project Jupyter.

Jupyter Notebooks are a spin-off project from the IPython project, which used to have an IPython Notebook project itself. The name, Jupyter, comes from the core supported programming languages that it supports: Julia, Python, and R. Jupyter ships with the IPython kernel, which allows you to write your programs in Python, but there are currently over 100 other kernels that you can also use.

> A [major upgrade to the Jupyter Notebook](https://jupyter-notebook.readthedocs.io/en/latest/migrate_to_notebook7.html) interface is coming with Notebook 7! This upgrade will bring a heap of new features, but will also break backwards compatibility with many classic Notebook features and customizations.

Install the classic Jupyter Notebook with: `pip install notebook`. You can also add it to the `requirements.txt` file.

For starting the Jupyter Notebook Server just go to that location in your terminal and run the following command:
- `jupyter notebook`

This will start up Jupyter and your default browser should start (or open a new tab) to the following URL: `http://localhost:8888/tree`

We will learn the following:
- Creating a Notebook
- Running Cells
- The Menus
- Starting Terminals and Other Things
- Viewing What’s Running
- Adding Rich Content
- Exporting Notebooks

### Jupyter Notebooks in VS Code
- [Jupyter Notebooks in VS Code](https://code.visualstudio.com/docs/datascience/jupyter-notebooks)

Visual Studio Code supports working with Jupyter Notebooks natively, and through Python code files. 

> If not already installed, install the [Jupyter](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter) extension for VS Code.

To work with Python in Jupyter Notebooks, you must activate an Anaconda environment in VS Code, or another Python environment in which you've installed the Jupyter package.

Once the appropriate environment is activated, you can create and open a Jupyter Notebook, connect to a remote Jupyter server for running code cells, and export a Jupyter Notebook as a Python file.

### Google Colab
- [Pozdravljeni v storitvi Colab!](https://colab.research.google.com/?utm_source=scs-index#scrollTo=Nma_JWh-W-IF)
