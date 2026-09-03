# Module 2: ***Pondering Paths*** (Linux Luminarium)

---
 # Challenge 1: ***The root***
 > Navigating the absolute path of files

## Solve:
- Got to know about the filesystem in Linux
- using `/` to find the path of a file
- typing file/folder name after `/` to open it   (eg- `/pwn`)\
\
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
- search engines

---
# Challenge 2: ***Program and absolute paths***
> Navigating complex file paths

## Solve:
- Navigating to a directory using `/`
- Then, Navigating to another directory withing the directory by naming it
- For example in the challenge, The path was `/challenge/run`\
\
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
- search engines

---

# Challenge 3: ***Position Thy self***
> changing to a different directory to work on


## Solve:
- Firstly changed the directory using the `cd` command
- Tried to run the file, But the terminal gave instructions to change to the `/var` directory to run the program
- Changed to the `/var` directory using `cd`
- now ran the file using its absolute path to capture the flag\
\
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
- search engines

---

# Challenge 4: Position elsewhere
> Changing multiple directories


## Solve:
- Ran the program. The terminal gave a new file location.
- changed directory and ran again. Again got a new path.
- Changed path yet again.
- and again...
- Finally found the directory, opened the program and got the flag :P\
\
The command needed for the challenge is-
```
hacker@paths~position-elsewhere:~$ /challenge/run
Starting level 1.
Incorrect...
You are not currently in the /usr/include directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-elsewhere:~$ cd /usr
hacker@paths~position-elsewhere:/usr$ cd /include
bash: cd: /include: No such file or directory
hacker@paths~position-elsewhere:/usr$ cd /usr/include
hacker@paths~position-elsewhere:/usr/include$ /challenge/run
Starting level 1.
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 2
Please use the `cd` utility to change directory to /etc
hacker@paths~position-elsewhere:/usr/include$ cd /etc
hacker@paths~position-elsewhere:/etc$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 3
Please use the `cd` utility to change directory to /var
hacker@paths~position-elsewhere:/etc$ cd /var
hacker@paths~position-elsewhere:/var$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 4
Please use the `cd` utility to change directory to /tmp
hacker@paths~position-elsewhere:/var$ cd /tmp
hacker@paths~position-elsewhere:/tmp$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Moving on to level 5
Please use the `cd` utility to change directory to /
hacker@paths~position-elsewhere:/tmp$ cd /
hacker@paths~position-elsewhere:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
{flag captured}
```
## Flag:
`pwn.college{QKcdKpoJxXVU2Vje5QvL5ZrRsmj.QX3QTN0wiM3EzNwIzW}`

## Concepts learnt:
- Same as challenge 3
- Changing to more than one directories one after another

## References:
- https://pwn.college/linux-luminarium
- Search engines
---

# Challenge 5: ***implicit relative paths, from /***
> Refering a directory using relative paths

## Solve:
- First changed my current directory from root to `/`
- Tried opening the directory `/challenge/run`. Terminal asked me to use relative paths
- Used relative path to open the directory\
\
The command needed for the challenge is-
```
hacker@paths~implicit-relative-paths-from-:~$ cd /
hacker@paths~implicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~implicit-relative-paths-from-:/$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
{flag captured}
```

## Flag:
`pwn.college{I4ZHsh5YP05PGdZGPgseKtseXCQ.QX5QTN0wiM3EzNwIzW}`


## Concepts Learnt:
- Difference between relative and absolute paths
- Accessing a directory using its local path

## References:
- https://pwn.college/linux-luminarium
- Search engines

---
 # Challenge 6: ***explicit relative paths, from/***
 > navigating to relative paths explicitly

## Solve:
- changed current directory from root directory
- Tried opening the directory directly. Not able to access
- used the relative path starting from `.` to access the directory\
\
The command used for the challenge is-
```
hacker@paths~explicit-relative-paths-from-:~$ cd /
hacker@paths~explicit-relative-paths-from-:/$ /challenge/run
Incorrect...
You invoked this challenge with an absolute path. This challenge needs a relative path!
hacker@paths~explicit-relative-paths-from-:/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
{flag captured}
```

## Flag:
`pwn.college{UM8vpeslpzXFpTk8-Y40iRhrxwK.QXwUTN0wiM3EzNwIzW}`

## Concepts learnt:
- There are 2 ways types of relative paths- implicit and explicit
- We can use `.` to point right to the same directory

## References:
- https://pwn.college/linux-luminarium
- Search engines


---

# Challenge 7: ***implicit relative path***
> Learning the applications of relative path in detail

## Solve:





## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- Search engines
---

# Challenge 8: ***home sweet home***
> ...

## Solve:




## Flag:




## Concepts learnt:




## References:
- https://pwn.college/linux-luminarium
- Search engines


---
