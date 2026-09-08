# Challenge 1: ***Listing Processes***
> Displaying all currently running processes


## Solve:
- The flag was renamed and moved to currently running processes
- Used the `ps` command with the argument `aux` or `-ef` to list all processes
- Found the running flag file
- executed it directly and got the flag

The command for the challenge is-
```
hacker@processes~listing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   748 ?        Ss   06:48   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   7136  2752 ?        S    06:48   0:00 /run/dojo/bin/sleep 6h
root         110  0.0  0.0 232596  4112 ?        S    06:48   0:00 /challenge/10750-run-29467
root         113  0.0  0.0 235016  3456 ?        S    06:48   0:00 sleep 6h
hacker       124  0.0  0.0  37980 22900 ?        Sl   06:48   0:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.0 
hacker       131  0.0  0.0 232860  4956 pts/0    Ss   12:14   0:00 /run/dojo/bin/bash --login
hacker       136  0.0  0.0 235228  4428 pts/0    R+   12:18   0:00 ps aux
hacker@processes~listing-processes:~$ ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 06:48 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7       1  0 06:48 ?        00:00:00 /run/dojo/bin/sleep 6h
root         110       1  0 06:48 ?        00:00:00 /challenge/10750-run-29467
root         113     110  0 06:48 ?        00:00:00 sleep 6h
hacker       124       1  0 06:48 ?        00:00:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.0 --writable -t d
hacker       131     124  0 12:14 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       137     131  0 12:18 pts/0    00:00:00 ps -ef
hacker@processes~listing-processes:~$ /challenge/10750-run-29467
Yahaha, you found me! Here is your flag:
{flag captured}
Now I will sleep for a while (so that you could find me with 'ps').
```

## Flag:
`pwn.college{kQJ8LLc1w7GaigQsK93c9wKkkVX.QX4MDO0wiM3EzNwIzW}`


## Concepts learnt:
- Listing currently running processes using `ps` command
- we can pass arguments so that the command gives more detailed output


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 2: ***Killing processes***
> Killing a currently running process


## Solve:
- We were instructed to kill a process so as to run the command to get the flag
- listed all running processes using `ps aux` command
- found the file. Terminated it using `kill` command with the PID as argument
- the processes was terminated. ran `/challenge/run` to get the flag 

The command for the challenge is-
```
hacker@processes~killing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   752 ?        Ss   12:25   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   7136  2772 ?        S    12:25   0:00 /run/dojo/bin/sleep 6h
root         109  0.0  0.0   4332  2996 ?        S    12:25   0:00 su -c /challenge/.launcher hacker
hacker       110  0.0  0.0 232596  3992 ?        Ss   12:25   0:00 /challenge/dont_run
hacker       111  0.0  0.0 235016  3404 ?        S    12:25   0:00 sleep 6h
hacker       122  0.0  0.0  37980 22852 ?        Sl   12:25   0:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.0 
hacker       124  0.0  0.0 232860  4976 pts/0    Ss   12:25   0:00 /run/dojo/bin/bash --login
hacker       129  0.0  0.0 235228  4392 pts/0    R+   12:27   0:00 ps aux
hacker@processes~killing-processes:~$ kill 110
hacker@processes~killing-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   752 ?        Ss   12:25   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/dojo/bin/sleep 6h
root           7  0.0  0.0   7136  2772 ?        S    12:25   0:00 /run/dojo/bin/sleep 6h
hacker       111  0.0  0.0 235016  3404 ?        S    12:25   0:00 sleep 6h
hacker       122  0.0  0.0  37980 22852 ?        Sl   12:25   0:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --interface 0.0.0.0 
hacker       124  0.0  0.0 232860  4976 pts/0    Ss   12:25   0:00 /run/dojo/bin/bash --login
hacker       130  0.0  0.0 235228  4384 pts/0    R+   12:28   0:00 ps aux
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
{flag captured}
```
## Flag:
`pwn.college{AYgm90M0rzoGO8b043erdZBXtl3.QXyQDO0wiM3EzNwIzW}`


## Concepts learnt:
- Terminating a currently running process using `kill` command
- `kill` command must be used with PID of a process


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 3: ***Interrupting Processes***
> Ending a processes running in the terminal


## Solve:
- ran the `/challenge/run` program but didnt get the flag
- cleared the terminal process using `ctrl+c` hotkey
- successfully got the flag

The command for the challenge is-
```
hacker@processes~interrupting-processes:~$ ^C
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
{flag captured}
```


## Flag:
`pwn.college{ss62hkZbwZclST2-GyVdOg3zypk.QXzQDO0wiM3EzNwIzW}`


## Concepts learnt:
- Ending a currently running process in terminal
- got to know about hotkeys
- Useful when we have to clear terminal from the current process


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/
- https://catern.com/posts/terminal_quirks.html

---

# Challenge 4: ***Killing misbehaving processes***
> Killing some very very bad processes..


## Solve:
- y
- 
- m

The command for the challenge is-
```
hacker@processes~killing-misbehaving-processes:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   752 ?        Ss   12:38   0:00 /sbin/docker-init -- /nix/var/nix/profiles/dojo-workspace/bin/dojo-init /run/do
root           7  0.0  0.0   7136  2740 ?        S    12:38   0:00 /run/dojo/bin/sleep 6h
root         111  0.0  0.0   2696  1680 ?        S    12:38   0:00 sleep 6h
root         112  0.0  0.0   2696  1672 ?        S    12:38   0:00 sleep 6h
root         113  0.0  0.0   4332  2784 ?        S    12:38   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       114  0.0  0.0  16440 12176 ?        Ss   12:38   0:00 /usr/bin/python3 /challenge/decoy
hacker       125  0.0  0.0  37980 22816 ?        Sl   12:38   0:00 /nix/store/nzhm2kbnlpp13kwvk192825y8pykhiag-ttyd-1.7.7/bin/ttyd --port 7681 --i
hacker       127  0.0  0.0 232976  4948 pts/0    Ss   12:39   0:00 /run/dojo/bin/bash --login
hacker       132  0.0  0.0 235228  4400 pts/0    R+   12:42   0:00 ps aux
hacker@processes~killing-misbehaving-processes:~$ kill 114
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
pwn.college{48Gpu94FteJjn6OD.mM9XHTS8RRzfEdQl.zZXDgEpWnYych}
pwn.college{DAvIoa8vAsZYl1zveOf.5vKIdz3wq8L.Xej61KpkgI6luA7}
pwn.college{QIBj3vIS-fsqMjo7JBQyaCoY1bWGG.f.SyLMPRRgVyQEXCc}
pwn.college{M.hHopOSghyw5x2d3Mae4xYZ9zmOkSMh3Rq.jfBOC1rBsaD}
pwn.college{HhnC5U8pHq2I37MVDiFRDyJ9Gq3.gq.-3L-46ATpmwTLYtk}
pwn.college{gNzdIMaYLosWhIt375oNPeGuk3qfFYVDW-zfBKMt8HrmHbX}
pwn.college{PanwJCMVBrS3njxbrrdwb1wkeR7iqm-9k8OIEa8US6KJyuo}
pwn.college{afyq-3FRn.VH.MG1Q0pdXWLWKZaEYZcYRx-a0UaTgFkUeBD}
pwn.college{y.LMkrOBvuZcHVSM2n9uX0yQkwvxXlcn5ocvHfnHpoqLvAV}
pwn.college{B67jvCNH5wXeR.v.dLiuz5jdr4THDcbI20QSbaQPZHs1izm}
pwn.college{FHSEn2isgNpUTRA2ODZRMD7dfzHtVqqddkA5poiedCXv5.P}
pwn.college{l9GY2eCZgMB78dckSj9uILoJm2-9YRzpqBp4uoY6jGwqBwx}
pwn.college{9aq9Cuei5pylbNCYRtH011vrCtEOLMJG.EXUw.UdgNIyMM7}
pwn.college{0foKYNKK2-.Ln5jYVF2GlIwEKdw9N-69s8Q-tp03aYYGO2n}
pwn.college{a50sqzuQyVmTEGhsq6lsS9BidJIQahdPVqtDZAvyGVXOn0R}
pwn.college{DzhcuI3jNx5h1v684UirfKaUFTJ7i2Eo1o63jVFAD7YfHK6}
pwn.college{0dwwalCmb.p5SMWok63Qjl12L45KwFpq5z8taZB88WaQVnf}
pwn.college{092zCQTUPC7YZC75n5wSgzcCX9FN5gXgxDMutj7NIP9z-qS}
pwn.college{ZwjK815XYfgfThmADKGNNo5PRD1zrCku6dWyUWB7cdOHVmR}
pwn.college{.rLBFJtlKNsPnNarh27l6D4sZgXkUwF8Dd5yG59AB30zWRF}
pwn.college{u3TBmyTWmecfMebkBYKl0K3XSqTOfOg-ixvosRE-SxhlBXS}
pwn.college{9N71.xAxm2W.QW11G1mqDNpolga3FhB8A-xpfTMB0sdXVd6}
pwn.college{Z6XjlbvNQDaroEh96k7VCzDz0AjAnGX2d.SgA5tbVLC2ZN2}
pwn.college{bSjfyDnDeDXOAx1DYjppvGGmu8TPGjI9qXauVOXrK8sEKe4}
pwn.college{wTuoQaV1pvCuKiU6NXp7NU7CHk-gAQq28vdNIIW4q.YTwyv}
pwn.college{DyDs4TfVi-9Hh0K4GMEP6BOkfDe9fIdl5ESgvRQvSTQbAk0}
pwn.college{PhIMQhskLyKB3eVA7vFKhRppKilyiMZDMQZsItsxo7NKpCd}
pwn.college{TryCUhfw5DxMGPHhvK5OKvB2VMem9IZkmYSEkSP54MpMg6T}
pwn.college{JMqZiJptcUyZPavQkmMc3Aur8-n5fAMP9xHBXpJR1V9lETE}
pwn.college{B6tcslkADKoC6POnRuFsi.g5r9-mS3deGuMOAXWEculLeg-}
pwn.college{mPbITho7UK644K21e2d0BMfi8vK4Jo5XbqAzxh3D3eX5BTt}
pwn.college{TkSDTsjqojbUZh..iXS3KuqKZDbgzxysGjYbkB6Vd5AvbCX}
pwn.college{Kj-IqwSrOBEJJnRm3wlakSxtdwODY6urw9NtZ40KLefZSTd}
pwn.college{gc7G7i07SmDnQRfPaVqDTgxuJL-c84WyGq3z63DxzMVwwoD}
pwn.college{0V92rZTw9jDDI.3pQhKBA5mRXnPs8vVpS1NcD05TT.GAlPx}
pwn.college{dQ5.6AZO2RD2GAV21Eda0y7gySVr2lnHM3j2HigMD0Vnb2J}
pwn.college{0UWk0dyPI.N-bTeygDeR8MZlOjXfjM7DFegMcpngCjir9wq}
pwn.college{CuLJAfqMuuXFUKKXLAWx3faXu8BEEtFTnBO--wiVD.SfzcY}
pwn.college{73effZdGfqkQyf3309TZjOUE4REIK7bmGB4P13hVkdRlMjw}
pwn.college{OSYnnPjl2phep.8Z.wQLw34eHHUkT3w0jXrwGQnWARwl2BC}
pwn.college{xYHjZKLn.CcxdGUZJsz3Hg60kpvFKQMRUQdUId.UUu4D9Lc}
pwn.college{qBhvDZCweLn4W3kU4nKVj5XycD6hI4d0gYt-f3g.uUjIFmT}
pwn.college{R3T9Lrm5npEimnYk495InI54RXRa3q6A80W4mJCJO0wp68-}
pwn.college{W63vUSCKzqsjZoiEvX2afwFe2Dgy00KqtYU4vJWvBCLOu.i}
pwn.college{QALll3aLTcza2lU0wjLNMkGHkeSIL2-zK0dJpZJ4hdqtp9.}
pwn.college{Uku8xF59BNZpJuBd48BFF4zPg3UKelA.7vDxiId9YFdQdJE}
pwn.college{60ohgJBDyfcTM38mfutH.NJEn2NSUj9z4iVMJKky40d63sg}
pwn.college{xUQQku6qSkw7PR4VWSHPoE-17VrDjCXQkUxymR2SEOyExRh}
pwn.college{czwLG4J9.lakbV1wD2HpIXT0uFvbqJ5RUcBNt9E1bzClTXP}
pwn.college{Xhpj9ae6cjzfdGU5MLValQ1MGIr2ilcEGALNt4YMMvLSb58}
pwn.college{dTkR8BGnFgS6ZBhttPuOcSzzjjFi9H1.t049ZRsA4ycNE6o}
pwn.college{faBbdrBcPePxWVE6N7m8kceZvyp6YkTw-M2EXPyFDXvo2TY}
pwn.college{vlCPAW6-U6uEsQ.8Inpw0C9oRjmhUnMorljAnelufDR4W.t}
pwn.college{pRISVdv.EeiU3JCmXj6mZVdL.IRl.KkJDtmeEFHjsgkNfaY}
pwn.college{hATQZT.9NVV1DSI2XWbsfhRlokH00P-xzWj-i2t2Myd8QQx}
pwn.college{pRt09vTa.yv.ARJ0FA4WFbMVeqFClkDPrgXGurnZqW2Frd7}
pwn.college{IkABeb49RBZtQc.Y71Z0DtZ-PCht19gOX2ceS5-TVjjIEm3}
pwn.college{zfjCK0E0OyWBPMN6oCpv0ghtJ3REfMi0GoSpcY8QYEUuEeN}
pwn.college{Cv0fo9q0xmAHUdjKshYNvQkG4wCxsX852z3vq6j5y0yEPfT}
pwn.college{Jx.4XbmBTGOxVeqXJr2QENgrUv3sgpcfWrWDqIbfGL7KRbC}
pwn.college{yxKwjrCX1jZSaA3IfqWQ.hjYIUA4on47BeVPoMmTDpT5puQ}
pwn.college{UmcHOQVwS8AH4ZVUdertbWmnL8Ref.QToHjCLPn8u58ob2E}
pwn.college{0aQyMqkj-EwqE2KLzU.wBAhSqxQ2a45N4L3BrWV-H3KPBjC}
pwn.college{p9oZH1aUHUlZDkExsUnFtWE1wUSNHarjH9bLJEHbNzSp55m}
pwn.college{TuAuPsOEAbK58eA0FJmtwG1c3eUkKQNH7r1fZc9j6ZErmcj}
pwn.college{Enz3nT8rGxEbY4KHkb63mujBcUcIJJ.bc6QTYDLOOlFWUDk}
pwn.college{GF4ST.8j0ypW0DnyfKRgMDaZ5cuyLeaqbehjEt.GcKWUVGz}
pwn.college{6jBhIqOf8wwr3JPO4UiSBPVLFgK9viJwsR9Xm56Wot8KVEI}
pwn.college{4A3by6v.KT6jWuSKe0ybWmrGwMLV.aJHjwk8yrEjDAkvRv8}
pwn.college{qayeaDG2YhE8GkUpFjsZbIsxkV-L-Y30IDp2.903aFS7coW}
pwn.college{uAwfqlz8IAvczuwRyvZvZWI6ATGzjR1rts7iVLzW1DRSo8L}
pwn.college{9KYHdj1WY87OvlIXoblaBsLY3SUF06CF2p7rFll0XCE2jNH}
pwn.college{QipvAbi-x2G8SFnJo4L3mWamMDWH2pnCXeR.taG446wFOQa}
pwn.college{A66t6vhJMBTAOJS3ersfCF.tbUj9xpd..sj2sDec-lW3oBO}
pwn.college{xi65kKCywCY.-tqgEqSkxis.k12dvDZIkRH1rN3IU8rNJuU}
pwn.college{e3RD7y5vsuUO35Bhe5wpHtx2.eyTxRjpO8-l3ABAV9GItpX}
pwn.college{nmJCs8jC.gvI3hPZpQXDoxVHGYFudruka7B.R5RRqnPxVYD}
pwn.college{3dtTTy1BbmZl.M6L1jRKseI9eElACIE5lvLJjZIAbRvLSAK}
pwn.college{TIw5cYTmmoeap9ynqQFYz076eWqY28m0a8.wTltKWvHJfZc}
pwn.college{MyBtJz88BdrzpaFUh1ow4r-cDISZa..0owAdghLAVahTsaQ}
pwn.college{B1ngRIO7T.3ajWkXNgjz-Ti5kVXjb9pw9mF1lQh0JRvgpk4}
pwn.college{pjbNCK613qob2552YxnXCBziTs3-Ja7AvupbZ86FfDH5038}
pwn.college{Trov1P5qKN-hZvhNjAhWMg7nhecPf.THWJKwkglli50pWN9}
pwn.college{FwaBGJuQSNVg.mOujThxPMFrLmRmBNvZ1nhBH9DgimZAUwi}
pwn.college{Ov7XI-CnvNkmrpwh80mkNiYbKabJWOnvSoOthL5lzW9xu5e}
pwn.college{Yj2m7PuYF9ejzolWToTfkNIHL84wQrBbD158oa9OawG4RUk}
pwn.college{Oi.75dFaJFYxgK4NJvEWTZLbb3AOcxTh8lz6CYtYDFA0468}
pwn.college{Ni0kFi8yCf7NyRoYjCqRXiK2ecN0b8DPhLj63BxFqRIMV3A}
pwn.college{j.16iokxhTbuDYjlYOzAWLiyjOFRtpeKkbF0HTXmE8YLF0K}
pwn.college{8qaBP1MowNh8i2POpjI5dvg9-QdMiPUO26dzQZ2N7bx11be}
pwn.college{.IDyXATBWs0yWNW5u66V5EQHS6CnP5S52SfIpIvf6RBTE-x}
pwn.college{Pb4IZDfDgCreiMpwhWkq.O29WNfg27kyreGdvbeembgUVEE}
pwn.college{wNYh.rPsOYrAxmj1T2nt4VloiXTYA-37jvAYSET6vwWfSOt}
pwn.college{T2pluB0-hv5wqpRJyDn-CwQ0aORQ.KWWz-hhXhK8ZMzXMKF}
pwn.college{-ccNOo8j0pWhGtBRJ7vLtCkO8j5jJs6Zl1eqrNOqtcQPnnZ}
pwn.college{ASTDAuGC-er-gBBKJkRaDm4Foz2Q7tqX3eVuWlz4mg7iqbE}
pwn.college{8ZDT80rGjNmatTJ9UWdVEF4UA5cumbDPfqdK1oKj.zkCglo}
pwn.college{GsabAolFO9ROYezaQhHCAwtkfS4wMJnQDcaXxJOM.P3aX6p}
pwn.college{alPspFnisXuP-Cy2mt0Mg9K45Ztij1D83C6WEiEbdSkhmVm}
pwn.college{b4KJxapZNZFLVZY4MBSyguaaWjN-tnn8TndQm.Y7qetaXnO}
pwn.college{nHjnAYNcS4hniVPhwc3bwW.ZGRWuc4ZoLOWVXfeLdojycfh}
pwn.college{l1OU3A9z3mnpZrzZmmf.UCHOFYJyy9QK3ZaydIfx4Zlm.gV}
pwn.college{bfCOH-oUjDGS7djwDlqySbKzg1t0rRwYyAXlzEFp1COerCW}
pwn.college{jbbnl0p2I37QurslQbBEi.smVs0-1VC8UtMgAjaNg8HCGWe}
pwn.college{tZ-VrVrlDKm-cCZlSV9vkg5BfZd5Q1bOho7bPVEfMvwXhqw}
pwn.college{RlOG6-OxMcQgX71Xl.NHyQK6ROLIh3mHTPaBHiz-pAD-eD0}
pwn.college{8NftsMW2wZuIYS7zkg.WNmGARPn-vtr.sle.42auvJX7sig}
pwn.college{H41FxrDVGF2kbU8jbZ52SFgo--Tq0Az4YdyOh6CMBkRCFso}
pwn.college{60iUl5ai8vJGsOcEJ3TKqEix83r1dirwV2x5V1su8MhyJrQ}
pwn.college{FXpOnNLWROhEq7vnlR-UMGKCkl02Et-77HFevbcD-8JRvMt}
pwn.college{MOVqX.lXOl8aMUFW4.q9hev6KJXXN-wFehXBy617.PgPOUA}
pwn.college{aaGtjAK8gGoxbP0sVLzurrX.mWc4W8U1XyjihViZCqdMAx-}
pwn.college{AIbi.uaaV0wxJhXgA08a-koVZ-Vho-uLLKqPUUmVlCnyB5J}
pwn.college{uScAwodiEbqhyBJuPQjQEvFuv.Kk0eVppVUPQSlON49RBCs}
pwn.college{FbMimJErnoGtsEKLvtz0MO7A5fhLpOgVWxgK5V49UBPcFXl}
pwn.college{oi-XA24qRNM6.FBai24FgwMfTo2fZnYlHm4nhpIdserkE8o}
pwn.college{-1EDs0-kim-he09gHTfUAbEtuwlByaid0G4YHcfAwxJwty8}
pwn.college{cFnRJn3FDHjJDYSGlBv9Ge7IX-0GsdZrtf6eDRDgeXL5oqq}
pwn.college{KJKgzCcwSbsYxu2CprseVtYx-AmT3JRxAs0YvJqL2yxAtNM}
pwn.college{.o2jRlKZRtG.yYiHotXdJC122pu0dalPzBG-ngCDPwj.TSK}
pwn.college{yAfNnCwT1ZneYGPVqqt6LLaFM7.u3ZhI0GgyPCb4MVoV8ny}
pwn.college{0PKZmq3wCD-.bvmvMXcMIej3o7w1OD6Wovymat83.Rsle98}
pwn.college{x63tRZDm1RHKWLoGNMKxNru7vei-dV07xoGJbCHuAt3u57I}
pwn.college{YF7SchjBKI-6MIA6f4NECRv15nvZu4XUEwFAzp6.dK9iChw}
pwn.college{OnXTiPP7rHzAzRCicWsyZcupTWo054sBenydUruuVDVm6L1}
pwn.college{IxlAMsCAn77zR1fRT-9NCX7vXNXOj3uDR7CZ19Kj92wEx7s}
pwn.college{f.kMadtLg5ZcJUfLjcaRMx0Yp2.AolFd91aMpYxXe74eW1K}
pwn.college{x9vvkeRLMyf0aef4oZJHkAYBQcsQ3rita9CKM4OcjxrltHs}
pwn.college{EKkd5dsu7Yfa03haGj6Dh43LoAozYEfbPgP8kinipc9FWhn}
pwn.college{etrV0UloaOiMwalu-CN0bjL3QlAhVIUeHW1bnj3U8F5z-IX}
pwn.college{CGDDhi.7178XJ2rlmUMwYXhxzWlay.bLoHAgxWNP18xrYBf}
pwn.college{HliT1.3yK1NTmsEgRXQ5e7caHpbmRKqbC3gsxHgamdIoq1N}
pwn.college{1aoMR41Fody5LR2EfpLI7AwYW5ACqQbVGi0Hox-vRGmaLNf}
pwn.college{MNJ6GRi5esUdmOta75KqLXJKgWwjM3E1lbWzvqWv32nPcIi}
^C
hacker@processes~killing-misbehaving-processes:~$ /challenge/run
Sending the flag to /tmp/flag_fifo!
hacker@processes~killing-misbehaving-processes:~$ cat /tmp/flag_fifo
{flag captured}
```

## Flag:
`pwn.college{k1LlYHY-rNb8e46s_OCxdLSrHoi.0FNzMDOxwiM3EzNwIzW`


## Concepts learnt:
- Terminating processes that are hogging resources
- Useful when system resources are being used up 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 5: ***Suspending processes***
> Suspending processes to the background


## Solve:
- The challenge asked us to suspend the `/challenge/run` file
- This will be such that there are 2 instances of the file running at an instance
- ran `/challenge/run` and then used the hotkey `ctrl+z` to suspend it
- ran it again and got the flag

The command for the challenge is-
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         130     117  0 12:55 pts/0    00:00:00 /bin/bash -p /challenge/run
root         132     130  0 12:55 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                    /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         130     117  0 12:55 pts/0    00:00:00 /bin/bash -p /challenge/run
root         137     117  0 12:56 pts/0    00:00:00 /bin/bash -p /challenge/run
root         139     137  0 12:56 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
"{flag captured}
```

## Flag:
`pwn.college{0c0dxqp6JftMr8y_jcH-J4ztkJy.QX1QDO0wiM3EzNwIzW}`


## Concepts learnt:
- Suspending a process working currently in the terminal
- This makes it such that it is not killed rather just removed from the terminal for the time being
- It works like a 'pause' button for a process


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 6: ***Resuming processes***
> Resuming the currently suspended processes


## Solve:
- The instructions asked us to run the `/challenge/run`, then suspend it and then resume it again
- Did it using the `fg` command
- Got the flag

The command for the challenge is-
```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                    /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{wV_Jwb4YyNueSnM8EdyNu0m4FmJ.QX2QDO0wiM3EzNwIzW}
Don't forget to press Enter to quit me!

Goodbye!
```
## Flag:
`pwn.college{wV_Jwb4YyNueSnM8EdyNu0m4FmJ.QX2QDO0wiM3EzNwIzW}`


## Concepts learnt:
- Resuming currently suspended processes using `fg` command
- It works like a 'resume' button for programs


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 7: ***Backgrounding processes***
> Resuming processes (in background)


## Solve:
- The challenge asked us to start the `/challenge/run` , suspend it, background it and run again
- Did as asked using the `ctrl+z` hotkey and `bg` commands
- Ran the program and got the flag

The command for the challenge is-
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         120 S+   /bin/bash -p /challenge/run
root         122 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                    /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.

hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         120 S    /bin/bash -p /challenge/run
root         130 S    sleep 6h
root         131 S+   /bin/bash -p /challenge/run
root         133 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
{flag captured}
```
## Flag:
`pwn.college{83XhC6T4QsOqCliwrrYqMzT06Ab.QX3QDO0wiM3EzNwIzW}`


## Concepts learnt:
- Resuming a process in the background
- Extra informations such as the difference between running a process in background and foreground


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 8: ***Foregrounding processes***
> Foregrounding a suspended process    


## Solve:
- ran the `/challenge/run` command. Got asked to suspend the process
- suspended using `ctrl+z` then backgrounded with `bg`
- next ran it on foreground using `fg` and got the flag

The command for the challenge is-
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                    /challenge/run
hacker@processes~foregrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~foregrounding-processes:~$ 


Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.
fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!
{flag captured}
```
## Flag:
`pwn.college{QWsXzHOIvr77K9xQdY8gNSAdrMV.QX4QDO0wiM3EzNwIzW}`




## Concepts learnt:
- Foregrounding a background running process
- we can also foreground a suspended process 


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 9: ***Starting backgrounded process***
> Running a process in background directly


## Solve:
- ran the `/challenge/run` but got told to run it in background
- ran the command with argument `&` to start it in background
- got the flag

The command for the challenge is-
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run
You've started me in the foreground! You must start me in the background (by 
appending '&' to the command) to get the flag!
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 123
hacker@processes~starting-backgrounded-processes:~$ 


Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
{flag captured}
```

## Flag:
`pwn.college{gHdF3cKiUu-HOB467LlREElz05a.QX5QDO0wiM3EzNwIzW}`


## Concepts learnt:
- starting a process in background directly without running in foreground


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---

# Challenge 10: ***Process exit codes***
> Retrieving exit codes

## Solve:
- ran `/challenge/get-code`. the program exited with an error
- used the `?` operator with echo command to retrieve the error code
- ran the `/challenge/submit-code` and submitted the code as an argument to it and got the flag

The command for the challenge is-
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
197
hacker@processes~process-exit-codes:~$ /challenge/submit-code 197
CORRECT! Here is your flag:
{flag captured}
```

## Flag:
`pwn.college{QCkUUOgi3cKL1u_52qDGHvjoC-Y.QX5YDO1wiM3EzNwIzW}`


## Concepts learnt:
- The concept of error codes
- Retrieving error codes using `?` operator


## References:
- https://pwn.college/linux-luminarium
- https://bash.cyberciti.biz/guide/Main_Page
- https://web.archive.org/web/20220629044814/http://bencane.com:80/2012/04/16/unix-shell-the-art-of-io-redirection/

---
