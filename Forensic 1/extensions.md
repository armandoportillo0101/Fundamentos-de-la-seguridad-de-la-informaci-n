## Descripción
```
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir extensions
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd extensions
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ file flag.txt
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ mv flag.txt flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ ls
flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ xxd -l 20 flag.png
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1      
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/extensions$ file flag.png
flag.png: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced

flag: picoCTF{now_you_know_about_extensions}
```

## Notas 
```
Tienes que abrir el archivo flag.png y ahí estará la bandera
```

## Referencias
````

```
