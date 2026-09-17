# Module 8: ***Chaining Commands***

---

# Challenge 1: ***chaining with semicolons***
> seperating commands using `;`


## Solve:
- the challenge asked us to chain commands
- used `;` operator to chain the commands
- ran and captured the flag

The commands for the challenge is-
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
{flag captured}
```

## Flag:
`pwn.college{YBEmyMvN9H_EH8G4QYRgc6UO5IJ.QX1UDO0wiM3EzNwIzW}`


## Concepts learnt:
- chaining commands using `;` operator
- the command entered first will be executed first
- `;` is similar to pressing enter key in terminal


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 2: ***Building on success***
> chaining commands using `&&` operator


## Solve:
- The challenge asked us to chain commmands using `&&` operator
- did so correctly and chained the programs `/challenge/first success` and `/challenge/second`
- got the flag

The commands for the challenge is-
```
hacker@chaining~building-on-success:~$ /challenge/first-success && /challenge/second
Nice chaining! Flag: {flag captured}
```

## Flag:
`pwn.college{kZNzE4aFfF2wosRJ9zppC6H--YB.0lM0MDOxwiM3EzNwIzW}`


## Concepts learnt:
- uses of `&&` operator
- the second command ((after the `&&` operator) will only run if first has succeeded
- This is also known as AND operator


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---

# Challenge 3: ***Handling failures***
> Using the `||` operator to chain commands


## Solve:
- The challenge asked us to use the `||` operator
- used it to chain the commands
- Got the flag

The commands for the challenge is-
```
hacker@chaining~handling-failure:~$  /challenge/first-failure || /challenge/second
Nice chaining! Flag: {flag captured}
```

## Flag:
`pwn.college{AJ6qQejzA2qye7m0eqSRWQwb2MH.01M0MDOxwiM3EzNwIzW}`


## Concepts learnt:
- Using the `||` operator to chain commands
- It executes the next command only if first one has failed
- also called 'OR' operator


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 4: ***Your first shell script***
> Using a shell script


## Solve:
- The challenge asked us to run both commands together via chaining
- did so using `;` operator.Then we were asked to run it via script `x.sh`
- did so by bashing the script and got the flag

The commands for the challenge is-
```
hacker@chaining~your-first-shell-script:~$ /challenge/pwn ; /challenge/college
hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
{flag captured}
```

## Flag:
`pwn.college{YlT1Mljq7KPZWmlt79AxCVIjSiG.QXxcDO0wiM3EzNwIzW}`


## Concepts learnt:
- Running a shell script by bashing it
- useful to add multiple commands to same shell file so that we can execute easilyy


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 5: ***redirecting script output***
> Redirection of the output by shell script


## Solve:
- The challenge asked us the same as before.. to run 2 command at once
- then bashed the script bus this time we had to redirect it to the given file too
- did so using the `|` (pipeline) operator

The commands for the challenge is-
```
hacker@chaining~redirecting-script-output:~$ /challenge/pwn ; /challenge/college
2d76e7b586d24f18559e33334e42494e  -
5b64f664a4c8cf32b5c3b8c8ec14a2f7  -
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
{flag captured}
```

## Flag:
`pwn.college{oXJ-F95sOhInpurfgfgI_mMXX8w.QX4ETO0wiM3EzNwIzW}`


## Concepts learnt:
- The concept of redirecting script output to another file
- we can use any redirect method we learnt earlier


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 6: ***executable shell scripts***
> executing a shell script


## Solve:
- The challenge asked us to execute the script instead of bashing
- first gave executable permission to the file using `chmod` command
- then executed the file by invoking the root path of it

The commands for the challenge is-
```
hacker@chaining~executable-shell-scripts:~$ ls
COLLEGE  PWN  instructions  myfile  myflag  the-flag  win.sh  x.sh
hacker@chaining~executable-shell-scripts:~$ chmod a+x x.sh
hacker@chaining~executable-shell-scripts:~$ ls -l
total 24
-rw-r--r-- 1 hacker hacker   4 Sep  7 12:48 COLLEGE
-rw-r--r-- 1 hacker hacker   8 Sep  7 19:04 PWN
-rw-r--r-- 1 hacker hacker 829 Sep  7 13:38 instructions
-rw-r--r-- 1 hacker hacker   0 Sep  6 09:08 myfile
-rw-r--r-- 1 hacker hacker  95 Sep  7 13:38 myflag
-rw-r--r-- 1 hacker hacker 437 Sep  7 13:27 the-flag
-rwxr--r-- 1 hacker hacker   0 Sep 14 18:23 win.sh
-rwxr-xr-x 1 hacker hacker  17 Sep 17 12:05 x.sh
hacker@chaining~executable-shell-scripts:~$ echo /challenge/solve > x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
{flag captured}
```

## Flag:
`pwn.college{0RFXy1tOd2yhHWhg9W0wDjwPYve.QX0cjM1wiM3EzNwIzW}`


## Concepts learnt:
- executing a script directly without bashing
- revision of previous concepts like editing the permissions of a file using `chmod`


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 7: ***understanding shebangs***
> Understanding concepts of shebang


## Solve:
- 

The commands for the challenge is-
```
hacker@chaining~understanding-shebangs:~$ touch /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod a+x solve.sh
hacker@chaining~understanding-shebangs:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~understanding-shebangs:~$ echo 'echo hack the planet' >> solve.sh
hacker@chaining~understanding-shebangs:~$ ./solve.sh
hack the planet
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: {flag captured}
```

## Flag:
`pwn.college{wLd8oZqhN-ANQRmNNnvv5d_J7AY.0VOzMDOxwiM3EzNwIzW}`


## Concepts learnt:
- using shebangs
- shebang line must be the very first line of code


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 8: ***scripting with arguments***
> Giving arguments to a shell script


## Solve:
- first created a shell script
- then used shebangs and gave appropriate command to reverse order of argyment
- tested by giving sample argument. It was correct. invoked the command and got the flag.

The commands for the challenge is-
```
hacker@chaining~scripting-with-arguments:~$ touch /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$  echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-arguments:~$ echo 'echo $2 $1' >> solve.sh 
hacker@chaining~scripting-with-arguments:~$ bash solve.sh pwn college
college pwn
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
{flag captured}
```

## Flag:
`pwn.college{AxlX8S8mbl5iP7aVuG9WXXNgLg5.0VNzMDOxwiM3EzNwIzW}`


## Concepts learnt:
- Passing arguments to scrip
- use of special character `$`


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 9: ***scripting with conditional***
> Using conditional statements while scripting


## Solve:
- Challenge asked us to make a script such that it will give output 'college' when argument is 'pwn'
- did so using `if` statements
- ran the program and got the flag

The commands for the challenge is-
```
hacker@chaining~scripting-with-conditionals:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-conditionals:~$ echo 'if [ "$1" == "pwn" ]
> then
> echo "college"
> fi' >> solve.sh
hacker@chaining~scripting-with-conditionals:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
{flag captured}
```

## Flag:
`pwn.college{E7n0R7ebs-z9Pbr5GWOSiaaLQwY.0lNzMDOxwiM3EzNwIzW}`


## Concepts learnt:
- passing conditional arguments in scripts
- uses of if statement in scripts


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 10: ***scripting with default case***
> using else in conditioanl arguments


## Solve:
- asked the same as previous challenge, but this time with else condition too
- did so same as before and added an `else` condition
- successfully got the flag

The commands for the challenge is-
```
hacker@chaining~scripting-with-default-cases:~$ touch /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-default-cases:~$ echo 'if [ "$1" == "pwn" ]
> then
> echo "college"
> else
> echo "nope"
> fi' >> solve.sh
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-default-cases:~$ bash solve.sh hi
nope
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
{flag captured}
```

## Flag:
`pwn.college{Ugo6tY6BfBfcCQ5Zg6Vig3lbLV0.01NzMDOxwiM3EzNwIzW}`  


## Concepts learnt:
- Using `else` condition for default case in `if` conditions
- important but not necessary to always use with `if`


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---



# Challenge 11: ***scripting with multiple conditions***
> adding multiple conditions to script


## Solve:
- challenge asked us to give multiple conditions
- did it using `if`,`elif` and `else`
- successfully got the flag

The commands for the challenge is-
```
hacker@chaining~scripting-with-multiple-conditions:~$ echo '#!/bin/bash' > solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ echo 'if [ "$1" == "pwn" ]
> then
> echo "college"
> elif [ "$1" == "hack" ]
> then
> echo "the planet"
> elif [ "$1" == "learn" ]
> then
> echo "linux"
> else
> echo "unknown"
> fi' >> solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ bash solve.sh pwn
college
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
{flag captured}
```

## Flag:
`pwn.college{A7qdzu5JpOiWB-OQ8Br_vf9DcQv.0FOzMDOxwiM3EzNwIzW}`


## Concepts learnt:
- Using multiple conditional arguments
- `elif` condition


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---




# Challenge 12: ***reading shell scripts***
> reading a shell script file


## Solve:
- challenge asked us to `cat` the shell script to get the password
- did it and got the password
- ran the command and entered the password, got the flag

The commands for the challenge is-
```
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/usr/bin/exec-suid -- /bin/bash -p

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET
CORRECT! Your flag:
{flag captured}
```

## Flag:
`pwn.college{EHS_kQ3T0_YnMi5UeJvOR2CdUF8.0lMwgDOxwiM3EzNwIzW}`


## Concepts learnt:
- catting a shell script
- useful when we have to find hidden info


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- Search engines

---








