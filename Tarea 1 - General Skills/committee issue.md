## Descripción
```
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/77/challenge.zip)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c_titan/77/challenge.zip
porti_04@DESKTOP-8HT902T:~$ unzip challenge.zip
porti_04@DESKTOP-8HT902T:~$ cd drop-in
porti_04@DESKTOP-8HT902T:~/drop-in$ ls
message.txt
porti_04@DESKTOP-8HT902T:~/drop-in$ ls -la
total 16
drwxr-xr-x 3 porti_04 porti_04 4096 Mar  9  2024 .
drwxr-x--- 5 porti_04 porti_04 4096 Sep 14 15:50 ..
drwxr-xr-x 8 porti_04 porti_04 4096 Mar  9  2024 .git
-rw-r--r-- 1 porti_04 porti_04   11 Mar  9  2024 message.txt
porti_04@DESKTOP-8HT902T:~/drop-in$ cat message.txt
TOP SECRET
porti_04@DESKTOP-8HT902T:~/drop-in$ git log
commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    remove sensitive info

commit 3d5ec8a26ee7b092a1760fea18f384c35e435139
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    create flag
porti_04@DESKTOP-8HT902T:~/drop-in$ git show HEAD
commit e1237df82d2e69f62dd53279abc1c8aeb66f6d64 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Sat Mar 9 21:10:14 2024 +0000

    remove sensitive info

diff --git a/message.txt b/message.txt
index 96f7309..d552d1e 100644
--- a/message.txt
+++ b/message.txt
@@ -1 +1 @@
-picoCTF{s@n1t1z3_30e86d36}
+TOP SECRET
porti_04@DESKTOP-8HT902T:~/drop-in$

```

## Notas 
```
El comando `git show HEAD` muestra los detalles del último commit (el commit apuntado por `HEAD`). Esto incluye el mensaje del commit, los cambios realizados (diferencias entre archivos) y la información del autor y la fecha. Es útil para revisar rápidamente qué cambios se hicieron en la última confirmación.
```

## Referencias
````

```