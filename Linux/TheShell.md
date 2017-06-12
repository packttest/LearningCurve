# Linux
###### Everything is from the internet, for the internet, through the internet. :metal:
### What is the shell?
It is a program, which is responsible for taking user input in the form of commands and pass it to the Operating System (OS) to execute. OS executes the recevied command if it is a valid command with the valid syntax than OS returns output or relavent error. This output or error is displayd on the shell. Usual Linux command sysntax have following conventions:
* **[]** Square brackets surrounded are optional items.
* **...** means arbitary-length list of items of that type.
* **|** when multiple items are seprated by pipes, means only one of them can be specified.
* **< >** Angle brackets, means variable data.

To get detailed understanding of a command:
* `$ ls --help` will provide quick help on the screen only. Usually shows quick introduction to the command, syntax and options.
* `$ man ls` will provide help for almost every command on a system. Sometimes also provides help about configuration files, whose `man` pages are defined. With the help of `Tab` command complettion can be used. Fort hat `bash-completion` must be installed on the system. <br><br> `man` pages are grouped into sections. <br>`1` Executable programs or shell commands <br>`2` System calls (functions provided by the kernel) <br>`3` Library calls (functions within program libraries) <br>`4` Special files (usually found in /dev) <br>`5` File formats and conventions eg /etc/passwd <br>`6` Games <br>`7` Miscellaneous (including macro packages and conventions), e.g. man(7), groff(7) <br>`8` System administration commands (usually only for root) <br>`9` Kernel routines [Non standard] <br>`0` C library header files <br>`n` `Tcl/Tk` keywords <br> `x` The Xwindows System <br> Different system may have different number of sections. In general, 1 to 8 sections are available in most of the Linux OS. <br><br>To open a particular `man` page, use the following syntax:<br>`man <page number> <command> <br><br> For example:<br>`$ man 1 ls` will open section 1 for the `ls` linux command. For each linux commands all or few of these sections only may exist. When tried to retriev unavailable sections it will give an error, as follow:<br>`$ man 2 ls` <br>`No manual entry for ls in section 2`

* `$ info ls` The GNU project distributies most of its on-line manuals in the "Info format". Read by "Info reader".

Most of the system administration tasks which can be done with the help of shell prompt can also be done with the help of Graphical User Interface (GUI). Many times, performing a system administration tasks are much more faster and handy using shell prompt rather than GUI.

### Shell types
In Unix/Linux shell types are broadly divided into two categories:
1. The Bourne Shell. Default prompt is `$`. Shell prompt will be `$` when logged in as a non-root user and `#` when logged in as `root` user. There are various sub-categories:
  * Bourne shell (sh)
  * Korn shell (ksh)
  * Bourne Again shell (bash)
  * POSIX shell (sh) and many others.
  
 **NOTE:** In 1970, Stephen R. Bourne has developed shell at AT&T Bell Labs. It was the first shell appeared on a UNIX system, hence it is called as "the shell".

**NOTE:** Bash shell is accessed through a terminal. It is also called as a physical console. Physical console supports multiple virtual console. Each virtual console is a seprate terminal and supports seprate login. Pressing `Ctrl + Alt + F1` to `F7` gives access to each of these virtual access. To close the shell session either `exit` or `Ctrl + d` can be used.

2. The C Shell. The default prompt is `%`. Shell prompt will be `%` when logged in as non-root user and `#` when logged in as `root` user.
  * C shell (csh)
  * TENEX/TOPS C shell (tcsh) and any others.

### Bourne Shell (Basics)

Default shell `/bin/bash` prompt is having four components. For example default shell prompt looks like as follow:

`bhavin@vm1 ~ $` 
Where
 * `bhavin` indicates the logged-in user name.
 * `vm1` indicates the hostname of the machine.
 * `~` indicates the present working directory, `~` means home directory.
 * `$` indicates currently working as a non-root user.
 
 **NOTE:** Default shell prompt may defer from Linux varients and it's version. It can also be customized.
 
Usually one command is provided on the shell prompt to execute. `&&` can be placed at the end of command to execute a consecutive command. Consequent command will only execute when previous command execution is success. Syntax is as follow:

Syntax:
`$ <command 1> && <Command 2> && .... && <Command n>`

To automate regular system administration tasks, a bunch of linux commands can be placed in the file. This file is called as a shell script. Usually execution takes place in a sequential order. With the help of looping and conditional statements, complex program can also be written to resolve advanced problems.

**NOTE:** Shell scripts syntax would be different for the Bourne shell and the C Shell.

On a linux machine, a list of an available shell(s) can be found in the `/etc/shells` file. For each linux user shell can be different, it can be configured at the `/etc/passwd`.

There are two different methods to invoke shell prompt. Interactive and Non-interactive method.

AN **interactive shell** method, reads command from the terminal `tty`. Usually, successful login will start interactive session. For login process, system runs `/bin/login` to ask username and password. Password is verified with the help of the `/bin/passwd` file. User specific shell can be configured in the `/bin/passwd`, if not configured `/bin/sh` is default shell. On successful login, usually shell will read `/etc/profile` and `~/.bash_profile` to configure a shell environment.
* `/etc/profile` stores system wide environment and runs startup programs from `/etc/profile.d/*.sh`
* `~/.bash_profile` stores user or application specific environment variables. This startup file only executes when login shell, either locally or remotely. For example: `sudo su -`, `bash --login`, or `ssh user@host` methodes.

**NOTE:** If `~/.bash_profile` file is not found than interactive login shell will search `~/.bash_login` and `~/.profile`. Out of these three files `~/.bash_profile`, `~/.bash_login` or `~/.profile` only one file is going to be executed. First priority is for `~/.bash_profile`, second priority is for `~/.bash_login` and last priority is for `~/.profile`. It is not recommonded to use `~/.bash_login` or `~/.profile` on Bourne shell, as they were introduced for the compatibility with other shells such as C shell and Korn shell. But due to basic difference in the systax among these shells, it is recommonded not to use `~/.bash_login` and `~/.profile` on Bourne shell.

An **interactive non-login shell**, such as openning a new tab in a terminal using `ctrl + t` or runing the shell using GUI will inherit an environment from parent and execute `~/.bashrc`. From commnad line these command `sudo su`, `bash` or `ssh user@host /path/to/command` also creates interactive non-login session. These two `~/.bash_profile` and `~/.bashrc` helps to differentiate between new user session and just adding a new session from logged-in user. And to run specific commands or to adjust an shell environemnt accordingly. 

**NOTE:** In Linux, rc means run commands. Assuming, rc in a `.bashrc` file name is given to make a meaniful name, indicating a set of commands to execute at the time of creating another shell terminal for already logged in user.

**Non-interactive shell** method does not involve human interaction with the shell such as running a shell script. Usually, running a shell script doesn't involve fa human inputs or interaction. Shell scripts can also be a interactive and they may wait for a user to provide an input. This type of shell inherits environment from parent shell only, as they do not have any startup files to set an environment.

`~/.bash_logout` script is always executed before the shell is terminating.

### Shell Prompt

The shell prompt is managed by shell variables. `P1`, `P2`, `P3`, `P4` and `PROMPT_COMMAND`.

Prompt Variable | Description
----------------|------------
P1 | The value of this parameter is expanded to create a primary shell prompt. The shell prompt appears as soon as logged in (SSH) to the server, default prompt is created with the values defined in the `PS1`. `echo $PS1` displayes the current value. Usually it containes `\u@\h:\w\$`. Where `\u` represents current user name, `\h` is a host name and `\w` is a working directory. Default shell prompt can be customized by re-initializing variable at: <br> * `/etc/profile` or `/etc/bashrc` for systemwide change. <br> * `~/.bash_profile`, `~/.bash_login`, `~/.profile`, `~/bashrc` to change just for any particular system user.
P2 | The value of this variable is expanded with PS1 and used for continuation of command. It is also called as the secondary prompt string. Default value is `>`. For example while typing a long command, for ease of reading usually we split command on multiple lines with `\`. That time new line appears with `>`.
P3 | Exapanded value of `PS3`defines the prompt for a select inside a script. Default value is `#?`. `#?` will appear as a prompt where user shell prompt will be blinking and waiting for a user to provide input. it can be customized as `PS3="Provide your input:"` to appear a proper statement rather than just `#?`.
P4 | It is used to define the prompt, displayed before each command bash displays during an trace execution.  The first character of PS4 is replicated multiple times, as necessary, to indicate multiple levels of indirection. The default is `+`.
PROMT_COMMAND | Content of this varibale is executed as a regular Linux command and output is displayed just before displaying the shell prompt. <br> <br> Example:<br> `$ echo $PS1` <br>`[\u@\h \W]\$` <br> <br> Now let's configure value for `PROMPT_COMMAND`. <br> `$ PROMPT_COMMAND="date +%H:%M"`<br> `04:15` <br> `[bhavin@vm1 ~]$` <br><br> Now before displaying the shell prompt it will display current system time. Usually both appears on a seprate line. To make them appear on the same line configure `PROMPT_COMMAND` with the `echo -n` as shown in the following example: <br><br> `$ PROMPT_COMMAND="echo -n PROMPT_COMMAND="echo -n [$(date +%H::%M)]"`<br>`[04::16][ec2-user@ip-172-31-27-254 ~]$`<br><br> Now we can see output of `PROMPT_COMMAND` is appearing on the same line as the shell prompt.

**NOTE:** Linux help `man bash` provides a detailed guideline.
