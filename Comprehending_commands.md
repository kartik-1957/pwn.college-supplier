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
- The instruction told that the file containing the flag is renamed
- used the `ls` command with the argument `/challenge` to list all files in it
- found the name of file. Executed it and got the flag
The commands used for the challenge is-
```
hacker@commands~listing-files:~$ ls /challenge
105-renamed-run-4995  Dockerfile
hacker@commands~listing-files:~$ /challenge/105-renamed-run-4995
Yahaha, you found me! Here is your flag:
{flag given}
```


## Flag:

`pwn.college{APnHsYTAqD27xuY5DvsmujvjFdb.QX4IDO0wiM3EzNwIzW}`

## Concepts learnt:
- Listing all the files in a directory
- Useful when we forgot the name of a file

### Caution: Dont use the `cat` command here because they are executable files not readable files (It took me some time to figure out since catting was showing a permission denied error :( )


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 7: ***Touching files***
> generating a new file


## Solve:
- Instructions asked me to create 2 files
- created files using touch command
- Run the file containing the flag
The commands used for the challenge is:
```
hacker@commands~touching-files:~$ /challenge/run
Uh oh! /tmp/pwn does not exist. Please use the 'touch' command to create it!
hacker@commands~touching-files:~$ touch /tmp/pwn
hacker@commands~touching-files:~$ touch /tmp/college
hacker@commands~touching-files:~$ ls /tmp
college  pwn
hacker@commands~touching-files:~$ /challenge/run
Success! Here is your flag:
```
## Flag:

`pwn.college{UGVAg0thXL8R3aPVqYq3_AmE90M.QXwMDO0wiM3EzNwIzW}`

## Concepts learnt:
- Creating file using the touch command
- The file created will be a blank file

### Caution: Same as above challenge.. do NOT use `cat` command to read the files.. execute them directly..


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 8: ***Removing files***
> removing/deleting files using `rm` command


## Solve:
- Instrcutions told that we have a file named `delete_me` created in our home directory
- Deleted the file using `rm` command
- ran the command `/challenge/check` to check and obtain the flag
The command used for the challenge is-
```
hacker@commands~removing-files:~$ ls /home
hacker
hacker@commands~removing-files:~$ ls /home/hacker
delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ ls /home/hacker
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
{Flag given}
```

## Flag:

`pwn.college{wP8cMGD7ynK8YMKY4KqafXozRhL.QX2kDM1wiM3EzNwIzW}`

## Concepts learnt:
- Removing/deletion of files using the `rm` command
- we can remove more than one file at once too using this command

### Caution: Write the file name directly without its absolute path ( ie without using `/`) else error will be shown


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 9: ***Moving files***
> Moving files from one location to another


## Solve:
- Used the `mv` command to move the flag file to another directory
- ran `/challenge/check` to check and obtain the flag

The command used for the challenge is:
```
hacker@commands~moving-files:~$ /flag
bash: /flag: Permission denied
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
{flag captured}
```

## Flag:
`pwn.college{IVLOjvJZ4KiBurc5U_R5jFfZUC7.0VOxEzNxwiM3EzNwIzW}`


## Concepts learnt:
- Using the `mv` command to move files from one directory to another
- We can also use the same command to rename the file
- We can move multiple files at once


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 10: ***Copying files***
> make a copy of a file


## Solve:
- Used the `cp` command as instructe
- copied the file containing flag to destination
- ran `/challenge/check` to verify and give the flag
The command for the challenge is-
```
hacker@commands~copying-files:~$ cp /flag /tmp/hack-the-planet
Correct! Performing 'cp /flag /tmp/hack-the-planet'.
hacker@commands~copying-files:~$ /challenge/check
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
{flag captured}
```
## Flag:
`pwn.college{YxYGKOWKVUXkXrYnbaqxsh-HxMk.0lNxQTMywiM3EzNwIzW}`


## Concepts learnt:
- Copying a file to another location
- Keeps a copy of file in original position intact
- When a `cp` destination is a directory, it places the copy inside it using the source file's name


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 11: ***Hidden files***
> listing hidden files


## Solve:
- as instructed, used the `ls` command with the `-a` flag to the `/` directory
- got a list of all files including hidden files
- catted the hidden flag file and captured the flag
The command used for the challenge is-
```
hacker@commands~hidden-files:~$ ls / -a
.   .dockerenv            bin   challenge  etc   lib    media  nix  proc  run   srv  tmp  var
..  .flag-67131144829405  boot  dev        home  lib64  mnt    opt  root  sbin  sys  usr
hacker@commands~hidden-files:~$ /.flag-67131144829405
bash: /.flag-67131144829405: Permission denied
hacker@commands~hidden-files:~$ cat /.flag-67131144829405
{flag captured}
```
## Flag:
`pwn.college{s0ypYbZrjc0PQwGfhlMb8I7R4EC.QXwUDO0wiM3EzNwIzW}`


## Concepts learnt:
- We can provide additional flags to a command
- `-a` flag is used to display hidden files if used with `ls` command

### Note: We cannot run the flag file and can only cat it because it is not an executable file.. (I tried executing it first but it showed permission denied)

## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 12: ***An EPIC filesystem quest***
> As the name says its epic and related to filesystem-


## Solve:
- Change the directory to `/`. Then use the `ls` command to list all files
- `cat` the file containing hint
- it gave a new location of hint and another additional info (This one was that the hint is *delayed* and cant be opened unless directory is changed)
- `cd` to go to the new directory, then list all files, and then `cat` the file having hint. This gave info that the next hint is *trapped* and should be opened without changing the directory
- list all the items in directory using the absolute path with `ls` command, and then cat it using the absolute path again
- This gave new location along with info that the file is *hidden*. Next list all the files in that directory using `ls` with the flag`-a` to list hidden files
- `cat` the file to get new hint..this hint was *delayed* so repeat second step
- next hint was trapped, next was hidden, and so on... (took a lot of time just going here and there...)
- Keep on doing this until found the file containing the flag :P
The commmand for the challenge is- (very long)
```
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
HINT  bin  boot  challenge  dev  etc  flag  home  lib  lib64  media  mnt  nix  opt  proc  root  run  sbin  srv  sys  tmp  usr  var
hacker@commands~an-epic-filesystem-quest:/$ cat HINT
Yahaha, you found me!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ ls
DOSSIER  Y.pl
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ cat DOSSIER
Congratulations, you found the clue!
The next clue is in: /usr/share/perl/5.38.2/Test2/Formatter

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ ls /usr/share/perl/5.38.2/Test2/Formatter
MESSAGE-TRAPPED  TAP.pm
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ cat /usr/share/perl/5.38.2/Test2/Formatter/MESSAGE-TRAPPED
Congratulations, you found the clue!
The next clue is in: /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Scx

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ ls /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Scx -a
.        Armn.pl  Cham.pl  Diak.pl  Gong.pl  Guru.pl  Hmng.pl  Khoj.pl  Latn.pl  Mong.pl  Orya.pl  Sinh.pl  Taml.pl  Tirh.pl  Zinh.pl
..       Beng.pl  Copt.pl  Dupl.pl  Gonm.pl  Han.pl   Hmnp.pl  Knda.pl  Limb.pl  Mult.pl  Phlp.pl  Syrc.pl  Tang.pl  Vith.pl  Zyyy.pl
.TRACE   Bhks.pl  Cprt.pl  Ethi.pl  Gran.pl  Hang.pl  Kana.pl  Kthi.pl  Lina.pl  Mymr.pl  Rohg.pl  Tagb.pl  Telu.pl  Xsux.pl  Zzzz.pl
Adlm.pl  Bopo.pl  Cyrl.pl  Geor.pl  Grek.pl  Hebr.pl  Khar.pl  Lana.pl  Linb.pl  Nand.pl  Shrd.pl  Takr.pl  Thaa.pl  Yezi.pl
Arab.pl  Cakm.pl  Deva.pl  Glag.pl  Gujr.pl  Hira.pl  Khmr.pl  Lao.pl   Mlym.pl  Nko.pl   Sind.pl  Talu.pl  Tibt.pl  Yi.pl
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ cat /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Scx/.TRACE
Tubular find!
The next clue is in: /usr/lib/python3.12/lib-dynload

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/IDS$ cd /usr/lib/python3.12/lib-dynload
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ ls
CUE                                               _queue.cpython-312-x86_64-linux-gnu.so
_asyncio.cpython-312-x86_64-linux-gnu.so          _sqlite3.cpython-312-x86_64-linux-gnu.so
_bz2.cpython-312-x86_64-linux-gnu.so              _ssl.cpython-312-x86_64-linux-gnu.so
_codecs_cn.cpython-312-x86_64-linux-gnu.so        _testbuffer.cpython-312-x86_64-linux-gnu.so
_codecs_hk.cpython-312-x86_64-linux-gnu.so        _testcapi.cpython-312-x86_64-linux-gnu.so
_codecs_iso2022.cpython-312-x86_64-linux-gnu.so   _testclinic.cpython-312-x86_64-linux-gnu.so
_codecs_jp.cpython-312-x86_64-linux-gnu.so        _testimportmultiple.cpython-312-x86_64-linux-gnu.so
_codecs_kr.cpython-312-x86_64-linux-gnu.so        _testinternalcapi.cpython-312-x86_64-linux-gnu.so
_codecs_tw.cpython-312-x86_64-linux-gnu.so        _testmultiphase.cpython-312-x86_64-linux-gnu.so
_contextvars.cpython-312-x86_64-linux-gnu.so      _testsinglephase.cpython-312-x86_64-linux-gnu.so
_crypt.cpython-312-x86_64-linux-gnu.so            _xxinterpchannels.cpython-312-x86_64-linux-gnu.so
_ctypes.cpython-312-x86_64-linux-gnu.so           _xxsubinterpreters.cpython-312-x86_64-linux-gnu.so
_ctypes_test.cpython-312-x86_64-linux-gnu.so      _xxtestfuzz.cpython-312-x86_64-linux-gnu.so
_curses.cpython-312-x86_64-linux-gnu.so           _zoneinfo.cpython-312-x86_64-linux-gnu.so
_curses_panel.cpython-312-x86_64-linux-gnu.so     audioop.cpython-312-x86_64-linux-gnu.so
_dbm.cpython-312-x86_64-linux-gnu.so              mmap.cpython-312-x86_64-linux-gnu.so
_decimal.cpython-312-x86_64-linux-gnu.so          ossaudiodev.cpython-312-x86_64-linux-gnu.so
_hashlib.cpython-312-x86_64-linux-gnu.so          readline.cpython-312-x86_64-linux-gnu.so
_json.cpython-312-x86_64-linux-gnu.so             resource.cpython-312-x86_64-linux-gnu.so
_lsprof.cpython-312-x86_64-linux-gnu.so           termios.cpython-312-x86_64-linux-gnu.so
_lzma.cpython-312-x86_64-linux-gnu.so             xxlimited.cpython-312-x86_64-linux-gnu.so
_multibytecodec.cpython-312-x86_64-linux-gnu.so   xxlimited_35.cpython-312-x86_64-linux-gnu.so
_multiprocessing.cpython-312-x86_64-linux-gnu.so  xxsubtype.cpython-312-x86_64-linux-gnu.so
_posixshmem.cpython-312-x86_64-linux-gnu.so
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ cat CUE
Tubular find!
The next clue is in: /var/lib/dpkg/triggers

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ ls /var/lib/dpkg/triggers -a
.  ..  .BLUEPRINT  File  Lock  Unincorp  ldconfig  lib32  libo32  libx32  update-ca-certificates  update-ca-certificates-fresh
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ cat /var/lib/dpkg/triggers/.BLUEPRINT
Congratulations, you found the clue!
The next clue is in: /usr/share/python3/debpython/__pycache__
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ ls /usr/share/python3/debpython/__pycache__
POINTER  __init__.cpython-312.pyc  files.cpython-312.pyc  interpreter.cpython-312.pyc  option.cpython-312.pyc  version.cpython-312.pyc
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ cat /usr/share/python3/debpython/__pycache__/POINTER
Yahaha, you found me!
The next clue is in: /usr/share/perl/5.38.2/Config/Perl

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/usr/lib/python3.12/lib-dynload$ cd /usr/share/perl/5.38.2/Config/Perl
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config/Perl$ ls
GIST  V.pm
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config/Perl$ cat GIST
Congratulations, you found the clue!
The next clue is in: /usr/lib/python3/dist-packages/elftools

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config/Perl$ ls /usr/lib/python3/dist-packages/elftools
BRIEF-TRAPPED  __init__.py  __pycache__  common  construct  dwarf  ehabi  elf
hacker@commands~an-epic-filesystem-quest:/usr/share/perl/5.38.2/Config/Perl$ cat /usr/lib/python3/dist-packages/elftools/BRIEF-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: {flag captured}
```

## Flag:
`pwn.college{AzBfnwYG2plKcn7o5kY6zdCGTJv.QX5IDO0wiM3EzNwIzW}`


## Concepts learnt:
- Changing directories, catting, reading hidden files etc..
-  Perseverance pays off :3


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 13: ***Making directories***
> making new directories ofc...


## Solve:
- use `mkdir` to create a directory as instructed
- create a file in it using `touch` command
- run the `/challenge/run` to get the flag
The command for the challenge is-
```
hacker@commands~making-directories:~$ mkdir /tmp/pwn
hacker@commands~making-directories:~$ touch /tmp/pwn/college
hacker@commands~making-directories:~$ ls /tmp/pwn
college
hacker@commands~making-directories:~$ /challenge/run
Success! Here is your flag:
{flag captured}
```
## Flag:
`pwn.college{k8vw2zVXGe3SsI9V0_3z2-nd1Rd.QXxMDO0wiM3EzNwIzW}`


## Concepts learnt:
- Making a new directory using `mkdir` command
- Using touch command to make a file
- The directory created will be an empty directory


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 14: ***Finding files***
> finding files using `find` command


## Solve:
- use `find` command by specifying `-name` with it in the `/` directory (here the argument is flag after `-name`)
- This will displays manyyyy files and directories
- Start checking them manually.. luckily i got it in my second try :P
The command for the challenge is-
```
hacker@commands~finding-files:~$ find / -name flag
find: ‘/etc/ssl/private’: Permission denied
/usr/lib/python3/dist-packages/pwnlib/flag
/usr/share/man/da/man8/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/root’: Permission denied
cat /usr/lib/python3/dist-packages/pwnlib/flag
cat /usr/share/man/da/man8/flag
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/nix/store/ka6xbd6z6wj5d6frl7ym4nzfc6p2wkdx-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/f31j0igg7ms3yrj5gm3cm76bjcmdl8w5-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/n6vb30rd7kkwjj595pgm0dmsmfaqi6i5-rizin-0.7.3/share/rizin/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/8qvj9mzdq2qxgjigw4ysqgbkcx1zi80y-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
/nix/store/c07wba3nrck81kdh0yg5h8rx22di35xi-radare2-6.0.4/share/radare2/6.0.4/flag
/nix/store/gfyhjlxav9nczmnanb3jxr73kb22yp42-rizin-0.8.1/share/rizin/flag
/nix/store/61dd247b72i7xnm0mw9qaxgfx3gs2lyy-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/sh1s72wwgvcq50kp830nlhm5cjpxmyh7-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/1wn496frzskd2drjwyyskk3g50rd1nbd-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/rszkfmr2mp5r4dyvhwqcj3521nyqfyzc-rizin-0.8.2/share/rizin/flag
/nix/store/kdlmh9h9hmq225jarh6rk927lb7jsxsv-radare2-6.1.8/share/radare2/6.1.8/flag
/nix/store/p9vjrnqyl7hy1k0ik9dw0lb9ib3c4582-python3.13-pwntools-4.15.0/lib/python3.13/site-packages/pwnlib/flag
/nix/store/f42x3k5mrk3qq79ixwy991p6g6a5l9f6-python3.13-pwntools-4.15.0/lib/python3.13/site-packages/pwnlib/flag
/nix/store/hss94rqc4ha0y229f8fwcy304wnzdsq7-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/4ckl0p6mafmm242c9qv3sln5dbd9rr9j-source/packages/core/src/flag
hacker@commands~finding-files:~$ cat /usr/lib/python3/dist-packages/pwnlib/flag
cat: /usr/lib/python3/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ cat /usr/share/man/da/man8/flag
{flag captured}
```
## Flag:
`pwn.college{kL6BkgD0-9_FntNcFiY_j5pIh-m.QXyMDO0wiM3EzNwIzW}`


## Concepts learnt:
- finding files using `find` command. by default searches current working directory
- we can give the flag `-name` to find by name. If not defined find all files in current directory
- It can take a long time to load as lots of files can have similar names


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 15: ***Linking files***
> using symbolic links


## Solve:
- 

## Flag:



## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

