## Descripción
```
Someone's commits seems to be preventing the  
program from working. Who is it?

You can download the challenge files here:

- challenge.zip
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c_titan/73/challenge.zip
--2026-18-02  15:25:19--  https://artifacts.picoctf.net/c_titan/73/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.11, 3.161.225.60, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293493 (287K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip               100%[=========================================>] 286.61K  1.61MB/s    in 0.2s

2026-18-02 15:25:19 (1.61 MB/s) - ‘challenge.zip’ saved [293493/293493]

porti_04@DESKTOP-8HT902T:~$ unzip challenge.zip
porti_04@DESKTOP-8HT902T:~$ cd drop-in
porti_04@DESKTOP-8HT902T:~/drop-in$ ls
message.py
porti_04@DESKTOP-8HT902T:~/drop-in$ git log message.py
commit fadeca9476b6713ec8cdda633aca9e9aebffc698
Author: picoCTF{@sk_th3_1nt3rn_e9957ce1} <ops@picoctf.com>
Date:   Sat Mar 9 21:09:11 2024 +0000

    optimize file size of prod code

commit 2dd46769e2d65656bb14aed0ff5d3237daaa7d9d
Author: picoCTF <ops@picoctf.com>
Date:   Wed Feb 18 21:09:11 2026 +0000

    create top secret project
porti_04@DESKTOP-8HT902T:~/drop-in$
```

## Notas 
```
`git log` es un comando que muestra el historial de confirmaciones (commits) en un repositorio de Git. Cada entrada incluye información como el identificador del commit, el autor, la fecha y el mensaje del commit. Puedes usar opciones como `--oneline` para un resumen corto o `--graph` para ver un gráfico del historial.
```

## Referencias
````

```