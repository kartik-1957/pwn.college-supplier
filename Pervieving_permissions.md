# Module 7: ***Perceiving permissions***
---

# Challenge 1: ***Changing file ownership***
> changing the ownership of a file


## Solve:
- The challenge gave us access to use the `chown` command even if we are not the root user
- Used the command on the `/flag` file to change user ownership
- catted the file to get the flag

The commands for the challenge is-
```
hacker@permissions~changing-file-ownership:~$ cat /flag
cat: /flag: Permission denied
hacker@permissions~changing-file-ownership:~$ chown hacker /flag
hacker@permissions~changing-file-ownership:~$ /challenge/run
I have given you access to use the 'chown' command. Use it to enable the flag 
to be read!
hacker@permissions~changing-file-ownership:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{QXLyblONmb14EhXEas1K5ZqPK-O.QXxEjN0wiM3EzNwIzW}`


## Concepts learnt:
- Using the `chown` command to change ownership of a file
- Some files and commands can only be accessed via the root user


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc

---

# Challenge 2: ***groups and files***
> Using groups


## Solve:
- The challenge gave us access to use the `chgrp` command
- used the command on `/flag` and made it a part of the hacker group
- catted the file and got the flag

The command for the challenge is-
```
hacker@permissions~groups-and-files:~$ /challenge/run
I have given you access to use the 'chgrp' command. Use it to enable the flag 
to be read!
hacker@permissions~groups-and-files:~$ chgrp hacker /flag
hacker@permissions~groups-and-files:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{Yj0D-6RuRKgfr9ucPF13pmtE3tk.QXxcjM1wiM3EzNwIzW}`


## Concepts learnt:
- Using the `chgrp` command to change groups of files
- some files are such that they can only be executed by the users whose member the files are


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 3: ***fun with group names***
> Using group names different than the user name


## Solve:
- The instructions told us that the  group name is randomized
- used the `id` command to get group name
- used the `chgrp` command to change ownership to that group and get the flag

The commands for the challenge are-
```
hacker@permissions~fun-with-groups-names:~$ id
uid=1000(hacker) gid=1000(grp29625) groups=1000(grp29625)
hacker@permissions~fun-with-groups-names:~$ chgrp grp29625 /flag
hacker@permissions~fun-with-groups-names:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{Mdv6wVHdmUnM3bisGn1D4gvuBN_.QXycjM1wiM3EzNwIzW}`


## Concepts learnt:
- Concept of different group names
- useful when more than one system are connected via each other (eg- computer labs)


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 4: ***changing permissions***
> Changing permissions related to a file


## Solve:
- The challenge gave us access to use the `chmod` command
- Used the command to change permissions for `/flag` file and made it readable by hacker
- catted the file and got the flag

The commands for the challenge is-
```
hacker@permissions~changing-permissions:~$ ls -l /flag
-r-------- 1 root root 60 Sep  9 17:16 /flag
hacker@permissions~changing-permissions:~$ /challenge/run
I have given you access to use the 'chmod' command. Use it to enable the flag 
to be read!
hacker@permissions~changing-permissions:~$ chmod go+rwx /flag
hacker@permissions~changing-permissions:~$ ls -l /flag
-r--rwxrwx 1 root root 60 Sep  9 17:16 /flag
hacker@permissions~changing-permissions:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{UCxIDP8WMGoAL83xlJyvqco9zdf.QXzcjM1wiM3EzNwIzW}`


## Concepts learnt:
- Using the `chmod` command to change file permissions
- there are 3 types of permissions for a file- read(r), write(w) and execute(x)
- permissions of a file are also divided among 3 parts- for owner, for groups and for other users


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 5: ***executable files***
> Making a file executable


## Solve:
- The challenge also gave us permissions to use `chmod` command
- used it to give the file `/challenge/run` execute permissions
- executed and got the flag

The commands for the challenge are-
```
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r--r--r-- 1 hacker hacker 32 Jul 24 06:05 /challenge/run
hacker@permissions~executable-files:~$ chmod a+x /challenge/run
hacker@permissions~executable-files:~$ ls -l /challenge/run
-r-xr-xr-x 1 hacker hacker 32 Jul 24 06:05 /challenge/run
hacker@permissions~executable-files:~$ /challenge/run
Successful execution! Here is your flag:
{flag cptured}
```

## Flag:
`pwn.college{UKVLyKAHbWUOGkqrm1feMG_n0LQ.QXyEjN0wiM3EzNwIzW}`


## Concepts learnt:
- Changing file permissions to make it executable
- same as above challenge..


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 6: ***permission tweaking practice***
> Practicing `chmod` command


## Solve:
- The instructions told to run the `/challenge/run` command to get further instructions
- got instructed to change file permissions. did it correctly.
- got asked to do again with some other conditions
- did it again and again till it allowed us to `chmod` the `/flag` file.
- changed permissions of flag file, catted it and got the flag.

The command for the challenge is-
```
hacker@permissions~permission-tweaking-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rwxrwxr--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod ug+rwx /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": rwxrwxr--
* the user does have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --x--x---
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a-rw /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": --x--x---
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --x------
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod g-x /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": --x------
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a-rwx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --x------
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod u+x /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": --x------
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-w--w-
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a+w /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": -wx-w--w-
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx-w-rw-
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod o+r /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": -wx-w-rw-
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
* the world does have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wx------
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod go-rwx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permission-tweaking-practice:~$ chmod a+rwx /flag
hacker@permissions~permission-tweaking-practice:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{gspr7ppYTLAkgx4ieEwxUDklT5n.QXwEjN0wiM3EzNwIzW}`


## Concepts learnt:
- Comprehensive practice regarding changing ownership of a file
- using `chmod` command


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 7: ***permissions setting practice***
> setting permissions for a file


## Solve:
- The instructions told to run the `/challenge/run` command to get further instructions
- got instructed to change file permissions. did it correctly.
- got asked to do again with some other conditions
- did it again and again till it allowed us to `chmod` the `/flag` file.
- changed permissions of flag file, catted it and got the flag.

The command for the challenge is-
```
hacker@permissions~permissions-setting-practice:~$ /challenge/run
Round 1 of 8!

Current permissions of "/challenge/pwn": rw-r--r--
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxr-----
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=wx,g=r,o=- /challenge/pwn
You set the correct permissions!
Round 2 of 8!

Current permissions of "/challenge/pwn": -wxr-----
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": -wxrw----
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod g+w /challenge/pwn
You set the correct permissions!
Round 3 of 8!

Current permissions of "/challenge/pwn": -wxrw----
- the user doesn't have read permissions
* the user does have write permissions
* the user does have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": r--r-x--x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=r,g=rx,o=x /challenge/pwn
You set the correct permissions!
Round 4 of 8!

Current permissions of "/challenge/pwn": r--r-x--x
* the user does have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": --xr-xr-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=rx,o=rx /challenge/pwn
You set the correct permissions!
Round 5 of 8!

Current permissions of "/challenge/pwn": --xr-xr-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
* the group does have read permissions
- the group doesn't have write permissions
* the group does have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w-rw----
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=rw,o=- /challenge/pwn
You set the correct permissions!
Round 6 of 8!

Current permissions of "/challenge/pwn": -w-rw----
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": rw-rw----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u+r /challenge/pwn
You set the correct permissions!
Round 7 of 8!

Current permissions of "/challenge/pwn": rw-rw----
* the user does have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
* the group does have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions

Needed permissions of "/challenge/pwn": --x-w-r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=x,g=w,o=rx /challenge/pwn
You set the correct permissions!
Round 8 of 8!

Current permissions of "/challenge/pwn": --x-w-r-x
- the user doesn't have read permissions
- the user doesn't have write permissions
* the user does have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions

Needed permissions of "/challenge/pwn": -w--w-r-x
- the user doesn't have read permissions
* the user does have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
* the group does have write permissions
- the group doesn't have execute permissions
* the world does have read permissions
- the world doesn't have write permissions
* the world does have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod u=w,g=w,o=rx /challenge/pwn
You set the correct permissions!
You've solved all 8 rounds! I have changed the ownership
of the /flag file so that you can 'chmod' it. You won't be able to read
it until you make it readable with chmod!

Current permissions of "/flag": ---------
- the user doesn't have read permissions
- the user doesn't have write permissions
- the user doesn't have execute permissions
- the group doesn't have read permissions
- the group doesn't have write permissions
- the group doesn't have execute permissions
- the world doesn't have read permissions
- the world doesn't have write permissions
- the world doesn't have execute permissions
hacker@permissions~permissions-setting-practice:~$ chmod a+rwx /flag
hacker@permissions~permissions-setting-practice:~$ cat /flag
{flag captured}
```

## Flag:
`pwn.college{QrTAMqsdCYCoZIFQApNtDnHqOM3.QXzETO0wiM3EzNwIzW}`


## Concepts learnt:
- comprehensive practice on `chmod` command
- setting absolute permissions instead of appending for files


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---


# Challenge 8: ***the SUID bit***
> Setting up SUID and using shell inside a program


## Solve:
- Instructions told to add SUID permissions to `/challenge/getroot`
- did so. then executed the program.
- we got root permissions. catted the flag file and captured the flag.

The commands for the challenge are-
```
hacker@permissions~the-suid-bit:~$ /challenge/run
Set the SUID bit on /challenge/getroot, then run it and read /flag from the 
root shell.
hacker@permissions~the-suid-bit:~$ chmod u+s /challenge/getroot
hacker@permissions~the-suid-bit:~$ cat /challenge/getroot
#!/usr/bin/exec-suid --real -- /bin/bash -p

fold -s <<< "SUCCESS! You have set the suid bit on this program, and it is running as root! Here is your shell..."
exec /bin/bash
hacker@permissions~the-suid-bit:~$ /challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root! 
Here is your shell...
root@permissions~the-suid-bit:/home/hacker# cat /flag
{flag captured}
```

## Flag:
`pwn.college{Ebp2jNcjgA9smezlTZDZH-FLLvM.QXzEjN0wiM3EzNwIzW}`


## Concepts learnt:
- Concept of SUID
- setting up SUID for a program
- using shell within a program to get root permissions


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://nettools.club/chmod_calc
---





