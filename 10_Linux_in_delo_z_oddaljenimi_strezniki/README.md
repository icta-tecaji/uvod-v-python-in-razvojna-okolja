# Linux in delo z oddaljenimi strežniki

## WSL
- [Windows Subsystem for Linux Documentation](https://learn.microsoft.com/en-us/windows/wsl/)
- [Get started using Python for web development on Windows](https://learn.microsoft.com/en-us/windows/python/web-frameworks)

Windows Subsystem for Linux (WSL) lets developers run a GNU/Linux environment -- including most command-line tools, utilities, and applications -- directly on Windows, unmodified, without the overhead of a traditional virtual machine or dual-boot setup.

## Docker
- [Docker Documentation](https://docs.docker.com/)
- [What is a Container?](https://biocontainers-edu.readthedocs.io/en/latest/what_is_container.html)

Simply put, a container is a sandboxed process on your machine that is isolated from all other processes on the host machine. That isolation leverages kernel namespaces and cgroups, features that have been in Linux for a long time. Docker has worked to make these capabilities approachable and easy to use. To summarize, a container:
- Is a runnable instance of an image. You can create, start, stop, move, or delete a container using the DockerAPI or CLI.
- Can be run on local machines, virtual machines or deployed to the cloud.
- Is portable (can be run on any OS).
- Is isolated from other containers and runs its own software, binaries, and configurations.

When running a container, it uses an isolated filesystem. This custom filesystem is provided by a container image. Since the image contains the container’s filesystem, it must contain everything needed to run an application - all dependencies, configurations, scripts, binaries, etc. The image also contains other configuration for the container, such as environment variables, a default command to run, and other metadata.

- [Install Docker Desktop on Windows](https://docs.docker.com/desktop/install/windows-install/)

### Running anvi'o in Docker
- [Docker image for anvi'o](https://merenlab.org/2015/08/22/docker-image-for-anvio/): Docker will help you run anvi’o quickly on a server or a desktop system with zero pain and no installation.

## Linux (Ubuntu)
- Local virtual machine using [VirtualBox](https://www.virtualbox.org/) and [Ubuntu](https://ubuntu.com/download/desktop)
- Remote server

## Povezava na oddaljeni strežnik
- Connect to a remote Linux VM from Windows using SSH:
    - [PuTTY](https://www.putty.org/): PuTTY is an SSH and telnet client, developed originally by Simon Tatham for the Windows platform. PuTTY is open source software that is available with source code and is developed and supported by a group of volunteers.
    - Built in SSH client in [Windows Terminal](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_overview): OpenSSH is the open-source version of the Secure Shell (SSH) tools used by administrators of Linux and other non-Windows for cross-platform management of remote systems. OpenSSH has been added to Windows (as of autumn 2018), and is included in Windows Server and Windows client.
        - SSH is based on a client-server architecture where the system the user is working on is the client and the remote system being managed is the server. OpenSSH includes a range of components and tools designed to provide a secure and straightforward approach to remote system administration.

To connect to a remote Linux computer from Windows, you need the following information about the remote Linux computer:
    - IP address or hostname of the remote Linux computer
    - Username and password to login to the remote Linux computer

Run: `ssh username@ip_address` and enter password.
- [Add SSH key to the server](https://learn.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation) (optional)

Copying files from Windows to Linux:
- [SCP](https://www.ssh.com/ssh/scp/): SCP is a means of securely transferring computer files between a local host and a remote host or between two remote hosts. It is based on the Secure Shell (SSH) protocol. "SCP" commonly refers to both the Secure Copy Protocol and the program itself.
- [WinSCP](https://winscp.net/eng/index.php): WinSCP is a popular free SFTP and FTP client for Windows, a powerful file manager that will improve your productivity. It supports also Amazon S3, FTPS, SCP and WebDAV protocols. Power users can automate WinSCP using .NET assembly.
- Run: `scp -r \desktop\myfolder\deployments\ user@host:/path/to/whereyouwant/thefile`

## Osnove dela z Linux terminalom
- [Linux Commands](https://www.hostinger.com/tutorials/linux-commands)

## Zagon Python programa na oddaljenem strežniku
- [Install Pyenv](https://github.com/pyenv/pyenv#automatic-installer)
- Create a new environment for a project.
- Copy the project to the server.
- Activate the environment.
- Install the requirements.
- Run the program.

## Crontab za avtomatsko zaganjanje
- [How To Use Cron to Automate Tasks](https://www.digitalocean.com/community/tutorials/how-to-use-cron-to-automate-tasks-ubuntu-1804)
- [crontab guru](https://crontab.guru/)
- [Schedule a Python Script by Cron Job in Linux](https://bktapan.medium.com/how-to-schedule-a-python-script-crontab-with-virtualenv-96bd6fcaa56a)

Cron is a time-based job scheduling daemon found in Unix-like operating systems, including Linux distributions. Cron runs in the background and operations scheduled with cron, referred to as “cron jobs,” are executed automatically, making cron useful for automating maintenance-related tasks.

## Remote Development using SSH (Visual Studio Code)
- [Remote Development using SSH](https://code.visualstudio.com/docs/remote/ssh)

The Visual Studio Code Remote - SSH extension allows you to open a remote folder on any remote machine, virtual machine, or container with a running SSH server and take full advantage of VS Code's feature set. Once connected to a server, you can interact with files and folders anywhere on the remote filesystem.

## Namestitev projekta iz GitHub repozitorija
- [How to Install Git on Ubuntu 20.04](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) 
- Choose a location for the cloned directory.
- Clone the repository.
- Install the requirements.
- Run the program.

## Namestitev Dockerja
- [Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)
- Run: `sudo docker run hello-world`
- Run a container: `sudo docker run -it ubuntu bash`

## Install JuyperLab
- [Install JupyterLab](https://jupyter.org/install)
- [Docs](https://jupyterlab.readthedocs.io/en/stable/getting_started/installation.html)

## Install Miniconda
- [Install Miniconda](https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html)
- [Prevent conda from activating the base environment by default](https://stackoverflow.com/questions/57640272/how-can-i-install-anaconda-aside-an-existing-pyenv-installation-on-osx)

## Installing programs on Linux
- [Installing anvi'o on Ubuntu](https://anvio.org/install/#3-install-anvio)
- [The Artemis Software](http://sanger-pathogens.github.io/Artemis/ACT/)
- [UNAFold](http://www.unafold.org/Dinamelt/software/obtaining-unafold.php)
- [rucs_analysis](https://github.com/bogemad/rucs_analysis)

