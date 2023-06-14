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
- **Third-party modules** are stored in the [Python Package Index (PyPI)](https://pypi.org/) and can be installed using the pip tool.

## Package Management orodja
- https://realpython.com/effective-python-environment/#package-management


## Uvod v orodje pip
- https://realpython.com/what-is-pip/

## Namestitev zunanjih knjižnic s pomočjo orodja pip
- Nameščanje knjižnic s pomočjo requirements.txt datoteke


## Kvaliteta Python knjižnic
- https://realpython.com/python-package-quality/

## Uvod v Python Wheels
- https://realpython.com/python-wheels/


## Problem nameščanja knjižnic brez virtualnega okolja

