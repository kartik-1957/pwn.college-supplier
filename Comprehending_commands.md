# Module 3: ***Comprehending Commands*** (Linux Luminarium)
---

# Challenge 1: ***cat: not the pet, but the command***
> read a file

## Solve:
- Reading the instructions, found out the flag is copied in my home directory
- used the `cat` command to read the file containing the flag
- got the flag\
\
The command used for the challenge is-
```
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
{flag captured}
```

## Flag:
`pwn.college{g0w2QUFvib5vHzASNlYtSkdreGx.QXxcTN0wiM3EzNwIzW}`

## Concepts Learnt:
- Using the `cat` command to read a file
- we can also concatenate or read  multiple files at once.

## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---
# Challenge 2: ***catting absolute paths***
> Same as title- reading a file by its absolute path


## Solve:
- instead of the file being directly in the home directory, it had a seperate directory
- Used the `cat /flag` command to open the file
- Captured the flagg

The command used for the challenge is:
```
hacker@commands~catting-absolute-paths:~$ cat /flag
{flag captured}
```
 ## Flag:
 `pwn.college{0_GWWXnqfTjdshEN9Ri6pXhvjRO.QX5ETO0wiM3EzNwIzW}`

 ## Concept Learnt:
 - Using the absolute file path with the `cat` command
 - Found out some files cannot be opened directly unless path mentioned
 - flag will always be found in the `/flag` directory unless stated otherwise..

## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---
# Challenge 3: ***more catting practice***
> catting on more complex paths


## Solve:
- The instructions clearly told the absolute path of the flag
- Used the `cat` command with the argument of the absolute path
- captured the flag :P

The command for the challenge is:
```
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/include/netipx/flag. Go cat it out without using cd!
hacker@commands~more-catting-practice:~$ cat /usr/include/netipx/flag
{flag captured}
```

## Flag:
`pwn.college{4Dt2UTo6hFjMWY74Zs2Qwr7N3su.QXwITO0wiM3EzNwIzW}`

## Concepts learnt:
- The concept of using complex file paths with the `cat` command
- reading a file without changing the current working directory

## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---
 # Challenge 4: ***grepping for a needle in a haystack***
 > searching (grepping) a particular content from a file

## Solve:
- Tried catting the file directly, but a string of many words was read
- Used the `grep` command and searched the keyword `pwn.college` to find the key amongst the text file
- Captured the flag..
The code for the challenge is-
```
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ cat /challenge/data.txt
{a list of random words was displayed}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
{flag captured}
```

## Flag:

`pwn.college{o2U_CHTrF42k5dn_5GIjrBQq6XD.QX3EDO0wiM3EzNwIzW}`


## Concepts learnt:
- Grepping a specific keyword in a file
- Useful when we need to find a specific item in a file
- grep prints all the items in a file containing the specific keyword


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 5: ***Comparing files***
> Finding changes between similar files


## Solve:
- First used the `cat` command to check what the files contained
- First file had all fake flags and second one had one real amongst fake
- Then used the `diff` command to find the difference between the files
- This showed the real flag as the difference between the files
The command for the challenge is-
```
hacker@commands~comparing-files:~$ cat /challenge/decoys_only.txt
{a list of fake flags displayed}
hacker@commands~comparing-files:~$ cat /challenge/decoys_and_real.txt
{a list of fake and a real flag was displayed}
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
19a20
{flag captured}
```
## Flag:

`pwn.college{QeH2FeHK-fa-OF7zoKfkPwHKre6.01MwMDOxwiM3EzNwIzW}`

## Concepts learnt:
- Learnt how to find the differences between files
- `diff` command lists all the changes or differences between the files
- It also displays the line where the change was observed, and also the type of change (like insertion or deletion)


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 6: ***listing files***
> listing all files in a directory


## Solve:
-


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 7: ***Touching files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 8: ***Removing files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 9: ***Moving files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 10: ***Copying files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 11: ***Hidden files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 12: ***An EPIC filesystem quest***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 13: ***Making directories***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 14: ***Finding files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 15: ***Linking files***
> ......


## Solve:


## Flag:



## Concepts learnt:



## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

