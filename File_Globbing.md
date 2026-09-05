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

# Challenge 4: ***matching paths with []***
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

# Challenge 5: ***Multiple globs***
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

# Challenge 6: ***Mixing globs***
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

