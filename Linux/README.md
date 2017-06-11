# Linux
###### Everything is from the internet, for the internet, through the internet. :metal:
### What is the shell?
It is a program, which is responsible to take input in the form of commands from a user and pass it to the Operating System (OS) to execute. OS executes the recevied command, if it is valid than return the output. Or else relavent error. These output or error is displayd on the shell.

Things can be done with the help of shell prompt can also be done with the help of Graphical User Interface (GUI). Many times, system administration tasks are much more faster and handy using shell prompt rather than GUI.

### Shell types
In Unix/Linux shell types are broadly devided into two categories:
1. The Bourne Shell. Default prompt is `$`. Shell prompt will be `$` when logged in with non-root user and `#` when logged in with `root` user. There are various sub-categories:
  * Bourne shell (sh)
  * Korn shell (ksh)
  * Bourne Again shell (bash)
  * POSIX shell (sh) and many others.
  
 **NOTE:** In 1970, Stephen R. Bourne has devloped shell at AT&T Bell Labs. It was the first shell appeared on UNIX system, hence it is called as "the shell".
 
2. The C Shell. Default prompt is `%`. Shell prompt will be `%` when logged in with non-root user and `#` when logged in with `root` user.
  * C shell (csh)
  * TENEX/TOPS C shell (tcsh) and any others.

### Bourne Shell (Basics)

Default shell `/bin/bash` prompt is having four components. For example shell prompt looks like as follow:

`bhavin@vm1 ~ $` 
Where
 * `bhavin` indicates the logged-in user name.
 * `vm1` indicates the hostname of the machine.
 * `~` indicates the present working directory, `~` means home directory.
 * `$` indicates currently working as a non-root user.
 
 **NOTE:** Default shell prompt may defer from OS and it's version. It can also be customized.
 
Usually one command is provided on the shell prompt to execute. `&&` can be placed at the end of command to execute a consequent command. Consequent command will only execute when previous command execution is success. Syntax is as follow:

Syntax:
`$ <command 1> && <Command 2> && .... && <Command n>`

To complete advance level tasks, bunch of linux commands in a sequential order with the logical control statements such as conditional and loop can be placed in a file. Such files are called as a shell script.

**NOTE:** Shell scripts syntax would be different for the Bourne shell and the C Shell.

On a linux machine, list of available shell(s) can be found at the `/etc/shells` file. For each linux user shell can be different, it can be configured at the `/etc/passwd`.

There are two different methods to invoke shell prompt. Interactive and Non-interactive method.

Interactive method, reads command from the terminal `tty`. Usually, successful login will start interactive session. For login process, system runs `/bin/login` to ask user name and password. Password is verified with the help of the `/bin/passwd` file. User specific shell can be configured in the `/bin/passwd`, if not configured `/bin/sh` is default shell. On successful login, usually shell will read `/etc/profile` and `~/.bash_profile` to configure a shell environment.
* `/etc/profile` stores system wide environment and runs startup programs from `/etc/profile.d/*.sh`
* `~/.bash_profile` stores user or application specific environment variables. This startup file only executes when login shell, either locally or remotely. For example: `sudo su -`, `bash --login`, or `ssh user@host` methodes.

**NOTE:** If `~/.bash_profile` file is not found than interactive login shell will search `~/.bash_login` and `~/.profile`. Out of these three files `~/.bash_profile`, `~/.bash_login` or `~/.profile` only one file is going to be executed. First priority is for `~/.bash_profile`, second priority is for `~/.bash_login` and last priority is for `~/.profile`. It is not recommonded to use `~/.bash_login` or `~/.profile` on Bourne shell, as they were introduced for the compatibility with other shells such as C shell and Korn shell. But due to basic difference in the systax among these shells, it is recommonded not to use `~/.bash_login` and `~/.profile` on Bourne shell.

An interactive non-login shell, such as openning a new tab in a terminal using `ctrl + t` or runing the shell using GUI will inherit an environment from parent and execute `~/.bashrc`. From commnad line these command `sudo su`, `bash` or `ssh user@host /path/to/command` also creates interactive non-login session. These two `~/.bash_profile` and `~/.bashrc` helps to differentiate between new user session and just adding a new session from logged-in user. And to run specific commands or to adjust an shell environemnt accordingly. 

Non-interactive method does not involve human interaction with the shell such as running a shell script. Usually, running a shell script doesn't involve fa human inputs or interaction. Shell scripts can also be a interactive and they may wait for a user to provide an input. This type of shell inherits environment from parent shell only, as they do not have any startup files to set an envrionemnt.
