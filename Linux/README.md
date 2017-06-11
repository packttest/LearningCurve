# Linux
###### Everything is from the internet, for the internet, through the internet. :metal:
### What is the shell?
It is a program, which is responsible to take input in the form of commands from a user and pass it to the Operating System (OS) to execute. OS executes the recevied command, if it is valid than return the output. Or else relavent error. These output or error is displayd on the shell.

The things can be done with the help of shell prompt can also be done with the help of Graphical User Interface (GUI). Many times shell prompt is much faster than the GUI.

Usually one command is provided on the shell prompt to execute. `&&` can be placed at the end of command to execute a consequent command. Consequent command will only execute when previous command execution is success. Syntax is as follow:

Syntax:
```$ <command 1> && <Command 2> && ... && <Command n>```

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

On a linux machine, list of available shell(s) can be found at the `/etc/sheslls` file. For each linux user shell can be different, it can be configured at the `/etc/passwd`.
