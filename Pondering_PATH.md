# Module 9: ***Pondering PATH***
---

# Challenge 1: ***The PATH variable***
> the `PATH` shell variable


## Solve:
- The challenge asked us to make it such that the PATH cannot be read else the flag file will be deleted
- Did so by equating the variable to blank space, ie `PATH=""`
- ran the command `/challenge/run` and got the flag

The commands for the challenge is-
```
hacker@path~the-path-variable:~$ PATH=""
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
{flag captured}
```

## Flag:
`pwn.college{UX2KUdI-v2qrtvQbqZ6QeX1Aa2N.QX2cDM1wiM3EzNwIzW}`


## Concepts learnt:
- Concept of PATH shell variable
- by default it stores the path to various directories in which the shell stores the programs corresponding to various commands
- by removing this variable, most commands that require path fails to function


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://www.linfo.org/path_env_var.html

---

# Challenge 2: ***setting PATH***
> Setting up a new file path


## Solve:
- Challenge asked us to get a new command 'win' from a given filepath
- overwritten the `PATH` variable with the given file path
- ran the command and got the flag

The commands for the challenge is-
```
hacker@path~setting-path:~$ PATH=/challenge/more_commands
hacker@path~setting-path:~$ /win
bash: /win: No such file or directory
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
{flag captured)
```

## Flag:
`pwn.college{EAK_inrLqhahzFYK2DBmukA0ec4.QX1cjM1wiM3EzNwIzW}`


## Concepts learnt:
- setting up a new location in PATH
- we can do this with any directory to set it as path


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://www.linfo.org/path_env_var.html

---

# Challenge 3: ***finding commands***
> finding where the commands are stored


## Solve:
- the challenge asked us to find the location of `win` command
- did so using `which` operator
- catted the flag file which was also in same folder as the win command got the flag

The commands for the challenge is-
```
hacker@path~finding-commands:~$ which win
/challenge/paths/29402/win
hacker@path~finding-commands:~$ cat /challenge/paths/29402/win
#!/bin/bash

/bin/fold -s <<< "Search for the flag in the same directory in which I am located!"
hacker@path~finding-commands:~$ ls /challenge/paths/29402
flag  win
hacker@path~finding-commands:~$ cat /challenge/paths/29402/flag
{flag captured}
```

## Flag:
`pwn.college{UWYGIvuG0QCEWvRdYErv7mqirqc.01NzEzNxwiM3EzNwIzW}`


## Concepts learnt:
- finding out the location where a specific command is stored using the `which` command
- It looks at each directory in `$PATH` in order and prints the first file it finds whose name matches the argument you passed


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://www.linfo.org/path_env_var.html

---

# Challenge 4: ***adding commands***
> adding a new command to path


## Solve:
- 

The commands for the challenge is-
```

```

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://www.linfo.org/path_env_var.html

---

# Challenge 5: ***Hijacking commands***
> intensive practice on PATH and commands


## Solve:
- 

The commands for the challenge is-
```

```

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://www.linfo.org/path_env_var.html

---
