# Module 5: ***Practicing Piping***
---

# Challenge 1: ***Redirecting Output***
> Redirecting output to a file


## Solve:
- The challenge asked us to redirect the `echo` command to a file
- Did it using the `>` charector
- Captured the flag

The command for the challenge is-
```
You have created the COLLEGE file, but you didn't write the correct value to 
it. Make sure to write PWN to the COLLEGE file.
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
{flag captured}
```

## Flag:
`pwn.college{4n2nQIEuevYKzMutYYWJ4km6GUA.QX0YTN0wiM3EzNwIzW}`


## Concepts learnt:
- Using the `>` character to redirect stdout to files
- This will truncate any previous data in file and add the output only as data in it
- If file does not exist, it will create a file and then redirect to it


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 2: ***Redirecting more output***
> Redirecting output of any command to a file


## Solve:
- The instructions asked us to redirect the output `/challenge/run` to the file `myflag`
- The program will verify that we have succeeded
- Now `cat` the file to get the flag

The command for the challenge is-
```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] {flag captured}
```
## Flag:
`pwn.college{kf-ITr4-xGXKoSxt-jw-wMsduYr.QX1YTN0wiM3EzNwIzW}`


## Concepts learnt:
- Redirecting the output of any command
- The command still prints on terminal even after being redirected


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---


# Challenge 3: ***Appending output***
> Redirect input in append mode


## Solve:
- The instructions told that the flag will be in 2 parts- First will be written at the file and second will be redirected via stdout
- Redirected `/challenge/run` using the append (`>>`) character
- Verified via program
- catted the file to get the flag

The command for the challenge is-
```
hacker@piping~appending-output:~$ /challenge/run >> /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{QwN7y_S5TY57YItvrI4Ah9m7HAl.QX3ATO0wiM3EzNwIzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```

## Flag:
`pwn.college{QwN7y_S5TY57YItvrI4Ah9m7HAl.QX3ATO0wiM3EzNwIzW}`


## Concepts learnt:
- Appending stdout to a file using `>>` character
- useful when we want the output to keep appending to the same file


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 4: ***Redirecting errors***
> Redirecting the error of a command


## Solve:
- The instructions told us to redirect stdout to a file and stderror to another file
- did it correctly using the correct file descriptors
- catted the file and got the flag

The command for the challenge is-
```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat instructions
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will check that error output is redirected to a specific file path : instructions
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!

[TEST] You should have redirected my stderr to instructions. Checking...

[PASS] The file at the other end of my stderr looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] {flag captured}
```

## Flag:
`pwn.college{krMPo2G1tx6c-xy_tT-sDyltprO.QX3YTN0wiM3EzNwIzW}`


## Concepts learnt:
- concept of file descriptor number
- redirecting standard errors to a file
- stdout(1) is the default or implicit file descriptor number for redirection
- You can redirect multiple file descriptor at same tine


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 5: ***Redirecting input***
> Redirecting input to a file


## Solve:
- First used the `>` operator to redirect input and make a file
- Then as instructed, Used the `<` operator to redirect input
- Ran it with the `/challenge/run` command to get the flag

The command for the challenge is-
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
{flag captured}
```

## Flag:
`pwn.college{AXB1Bc-ERlbI1tXoUK2ud8PCz3z.QXwcTN0wiM3EzNwIzW}`


## Concepts learnt:
- The concept of redirecting input to commands using `<` operator
- We can redirect more than 1 input at once


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 6: ***Grepping stored results***
> Mixing grepping and redirecting..


## Solve:
- Redirect the output of `/challenge/run` command to the given location
- Now, use the `grep` command with the keyword `pwn.college`
- This will display only the flag from the hundreds of different lines

The command for the challenge is-
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~grepping-stored-results:~$ grep pwn.college /tmp/data.txt
{flag captured}
```

## Flag:
`pwn.college{kPDAMrdEgJAbmh3fhjoJWoNe7Gh.QX4EDO0wiM3EzNwIzW}`


## Concepts learnt:
- Grepping contents from a redirected file
- Same as above challenges..


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 7: ***Grepping live output***
> grepping and redirecting files simultaneously


## Solve:
- instructions asked us to grep a program directly without storing it
- Used the `|` operator to grep and run command simultaneously
- successfully got the flag

The command for the challenge is-
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/sacz532zgiacvg7mva9v6gbfmyw427i3-gnugrep-3.12/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
{flag captured}
```

## Flag:
`pwn.college{YOVq8nEjOJocVHR4r-0E4TyXCoo.QX5EDO0wiM3EzNwIzW}`


## Concepts learnt:
- doing commands simultaneously using the `|` operator
- can help us save unnecessary time and space to create a new file
- used to connect (pipeline) different commands


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 8: ***Grepping errors***
> Grep errors directly


## Solve:
- The instructions told us that the flag is amongst the stderror of the program
- ran the program, then redirected the stderr to stdout using `>&` operator
- used the `|` operator to run command and grep the flag simultaneously

The commands for the challenge is-
```
hacker@piping~grepping-errors:~$ /challenge/run 2>& 1 | grep pwn.college
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/sacz532zgiacvg7mva9v6gbfmyw427i3-gnugrep-3.12/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
{flag captured}
```
## Flag:
`pwn.college{EowysFRbP0Edgng-Urfr7QXxj2o.QX1ATO0wiM3EzNwIzW}`


## Concepts learnt:
- Conversion of one type of file descriptor to another
- using the `>&` operator
- grepping standard errors directly without catting


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---


# Challenge 9: ***Filtering with grep -v***
> Using invert match option


## Solve:
- We were asked to invert match and filter out all decoy flags
- used the argument `-v` with the `grep` command to filter out the decoy flag
- the real flag got printed

The commands for the challenge is-
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
{flag captured}
```

## Flag:
`pwn.college{M7TLJDm-DmzruLKtbS1UID4saNB.0FOxEzNxwiM3EzNwIzW}`


## Concepts learnt:
- The concept of invert match
- using `-v` argument for invert matching
- useful when we need to filter out data


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 10: ***Filtering with sed***
> Filtering out unnecessary data using `sed` command


## Solve:
- The instructions told us that the `/challenge/run` command has garbage data in it in between the flag
- Used the `sed` command with the argument `/s/FAKEFLAG//g`
- The flag got printed as output

The command for the challenge is-
```
hacker@piping~filtering-with-sed:~$ /challenge/run | sed s/FAKEFLAG//g
{flag captured}
```

## Flag:
`pwn.college{EKwTqzYvAqfm74Bwwr9EdF6Fl55.01NxQTMywiM3EzNwIzW}`


## Concepts learnt:
- Using the `sed` command to filter out data
- It is used with the argument `/s/keyword/keyword/g`


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 11: ***Duplicating piped data with tee***
> duplicating the output to multiple files


## Solve:
- 

## Flag:
`


## Concepts learnt:
- 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 12: ***process substitution for input***
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
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 13: ***writing to multiple programs***
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
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 14: ***split piping stderr and stdout***
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
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 15: ***Named pipes***
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
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

