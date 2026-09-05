# Module 4: ***File Globbing*** (Linux Luminarium)
---

# Challenge 1: ***Matching with ' * '***
> Learn about globbing (*)

## Solve:
- We start with the home directory and need to change to the `/challenge` directory
- The catch is, we cannot use more than 4 charectors to change directory
- use the `*` glob with `cd` to change directory. then run command and get the flag
The command for the challenge is-
```
This challenge resets your working directory to /home/hacker unless you change 
directory properly...
hacker@globbing~matching-with-:~$ cd /c*
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
{flag Captured}
```

## Flag:
`pwn.college{s5u1mfexX94e1OBnoKnY3ux8ACw.QXxIDO0wiM3EzNwIzW}`

## Concepts learnt:
- Using the `*` glob
- The `*` glob matches any part of the filename except for `/` or a leading `.`
- When zero files are matched, by default, the shell leaves the glob unchange

## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 2: ***Matching with ?***
> using glob `?`


## Solve:
- As instructed we need to change directory to `/challenge`
- Catch is that we cannot use the charectors `c`,`l` and `*` while changing directory
- replace these with the glob `?` and change directory. Then run command and get the flag.
The command for the challenge is-
```
hacker@globbing~matching-with-:~$ cd /?ha??enge
hacker@globbing~matching-with-:/challenge$ /challenge/run
You ran me with the working directory of /challenge! Here is your flag:
{flag captured}
```

## Flag:
`pwn.college{4iSp-xaYwQ5do8qLqWKRs8whrof.QXyIDO0wiM3EzNwIzW}`


## Concepts learnt:
- The usage of `?` glob
- it only matches one character unlike `*` glob


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 3: ***matching with []***
> globbing with `[]`


## Solve:
- as instructed, change the directory
- Now, run the program while giving the argument of all files at once using the `[]` glob
- this will execute it and give us the flag
The command for this challenge is-
```
hacker@globbing~matching-with-:~$ cd /challenge/files
hacker@globbing~matching-with-:/challenge/files$ ls file_[absh]
file_a  file_b  file_h  file_s 
hacker@globbing~matching-with-:/challenge/files$ /challenge/run file_[abhs]
You got it! Here is your flag!
{flag captured}
```
## Flag:
`pwn.college{gv-8prsSUne76SzfJqR5sZe4bEx.QXzIDO0wiM3EzNwIzW}`


## Concepts learnt:
- Using the `[]` glob
- It works similar to `?` glob except the fact that we can check more than one arguments at once using this


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 4: ***matching paths with []***
> using glob `[]` with filepaths


## Solve:
- The instructions told us to run the program while staying in the current directory and using a single argument
- ran the `/challenge/run` program with the argument globbing all 4 files using `[]` with their file paths
- Ran and got the flag
The command for the challenge is-
```
hacker@globbing~matching-paths-with-:~$ /challenge/run /challenge/files/file_[absh]
You got it! Here is your flag!
{flag captured}
```

## Flag:
`pwn.college{Y82PEefg0FXxw0ZUk4OQYRdyLuJ.QX0IDO0wiM3EzNwIzW}`


## Concepts learnt:
- using the glob `[]` after specifying pathways
- globbing happens on a path basis


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 5: ***Multiple globs***
> using more than one similar type of globs at once


## Solve:
- Change the current working directory to `/challenge/files`
- Now we need to run every file containing the letter p in its name.. we can do it by the glob `*p*` as it covers all the words
- This will successfully run the program and flag will be captured
The command for the challenge is-
```
hacker@globbing~multiple-globs:~$ cd /challenge/files
hacker@globbing~multiple-globs:/challenge/files$ ls
amazing    challenging  educational  great  incredible  kind      magical  optimistic  queenly  splendid   uplifting   wonderful  youthful
beautiful  delightful   fantastic    happy  jovial      laughing  nice     pwning      radiant  thrilling  victorious  xenial     zesty
hacker@globbing~multiple-globs:/challenge/files$ /challenge/run *p*
You got it! Here is your flag!
{flag captured}
```

## Flag:
`pwn.college{8p_32q7XFZ-Zp4Qk-ZtPzd-tQ53.0lM3kjNxwiM3EzNwIzW}`


## Concepts learnt:
- Using multiple similar kind of globs at once
- we can use them even in the same argument


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 6: ***Mixing globs***
> using multiple globs (same or different) at once


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 7: ***Exclusionary glob***
> 


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 8: ***Tab completion***
> 


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 9: ***Multiple options for tab completion***
> 


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 10: ***Tab completion on command***
> 


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

