# Module 2: ***Pondering Paths*** (Linux Luminarium)

---
 # Challenge 1: ***The root***
 > Navigating the absolute path of files

## Solve:
- Got to know about the filesystem in Linux
- using `/` to find the path of a file
- typing file/folder name after `/` to open it   (eg- `/pwn`)
The command needed for the challenge is-
```
hacker@paths~the-root:~$ /pwn
BOOM!!!
{flag given}
```

## Flag:
```
pwn.college{EZafTw8u34W23AODZi4b-Q-2JDl.QX4cTO0wiM3EzNwIzW}
hacker@paths~the-root:~$
```

## Concepts learnt:
- Learnt about absolute path 
- Learnt how to navigate the filesystem in a linux subsystem
- invoking the program or file from the filesystem

## References:
- https://pwn.college/linux-luminarium
- www.google.com

---
# Challenge 2: ***Program and absolute paths***
> Navigating complex file paths

## Solve:
- Navigating to a directory using `/`
- Then, Navigating to another directory withing the directory by naming it
- For example in the challenge, The path was `/challenge/run`
The command needed for the challenge is-
```
hacker@paths~program-and-absolute-paths:~$ /challenge/run
Correct!!!
/challenge/run is an absolute path!
{flag given}
```
## Flag: 
```
pwn.college{MomjmCeLOQmrioM_udHAR6uFT41.QX1QTN0wiM3EzNwIzW}
```

## Concepts Learnt:
- Navigating to a more complex file path
- Navigating to a directory within a directory

## References:
- https://pwn.college/linux-luminarium
- www.google.com

---

# Challenge 3: ***Position Thy self***
> changing to a different directory to work on


## Solve:
- Firstly changed the directory using the `cd` command
- Tried to run the file, But the terminal gave instructions to change to the `/var` directory to run the program
- Changed to the `/var` directory using `cd`
- now ran the file using its absolute path to capture the flag
The command needed for the challenge is-
```
hacker@paths~position-thy-self:~$ cd /challenge
hacker@paths~position-thy-self:/challenge$ /challenge/run
Incorrect...
You are not currently in the /var directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:/challenge$ cd /var
hacker@paths~position-thy-self:/var$ /run
bash: /run: Is a directory
hacker@paths~position-thy-self:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
{flag given}
```
## Flag:
```
pwn.college{UAg7ajfZPrcZC55Fgjb8URDW5_Y.QX2QTN0wiM3EzNwIzW}
```
## Concepts learnt:
- Changing the directory
- Found out that specific files can only be opened in a specific directory only
- Working on the new directory

## References:
- https://pwn.college/linux-luminarium
- www.google.com

---

