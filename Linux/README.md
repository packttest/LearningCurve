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

Default shell prompt is having four components. For example shell prompt looks like as follow:

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

There are two different methods to invoke shell prompt. One is interactive method. It reads command from the terminal `tty`. When shell executes to show terminal it also executes startup files, display prompt and enables job control by default. In this mode user can interact with the shell with giving commands and seeing output of the same. 

Bash startup files are as follow. Either of the login method (i.e. interactive shell and non-interactive shell) will deicde which startup file will be executed. Example of interactive mode is a shell prompt, where commands can be executed and communication with linux is live. Example of non-interactive login is running the shell from GUI or running a shell script.

> ### What is job control?
> In Linux, every running program is called as a process. Linux is a multi-user and multi-tasking OS. It means multiple users can loggin to the same server and can run multiple prograams at the same time during their session with the server. While running one or more processes on a server through shell prompt, the ability to retrieve information about these processes are called as job control. These jobs can run in the foreground or in background. Usually, only one process or job remains in the foreground and keyboard input goes to it. Rest of the processess may remain in the background or paused (suspended). Process management it self is a big topic.

* `/etc/profile` it is used to set system wide configuration parameters. Also will execute the scripts within `/etc/profile.d/*.sh`
* `~/.bash_profile, ~/.bash_login` or `~/.profile`these files are used to set shell environent such as `PATH`. This file overrides the `/etc/profile`.
* `~/.bash_logout`

`~/.bashrc` file is used when bash shell is opened using a GUI.
