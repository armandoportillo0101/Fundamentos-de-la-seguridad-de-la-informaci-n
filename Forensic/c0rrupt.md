## Descripción
```
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd corrupt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ cp mystery flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ hexeditor flg.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ exiftool flag.png
ExifTool Version Number         : 12.40
File Name                       : flag.png
Directory                       : .
File Size                       : 198 KiB
File Modification Date/Time     : 2026:10:07 11:06:59-06:00
File Access Date/Time           : 2026:10:07 11:08:58-06:00
File Inode Change Date/Time     : 2026:10:07 11:06:59-06:00
File Permissions                : -rw-r--r--
Error                           : File format error
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ file mystery
mystery: data
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ sudo apt install pngcheck
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ pngcheck -v flag.png
File: flag.png (202940 bytes)
  File is CORRUPTED.  It seems to have suffered EOL conversion.
ERRORS DETECTED in flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ hexeditor flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ file mystery
mystery: data
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ pngcheck flag.png
flag.png:  CORRUPTED by text conversion
ERROR: flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ hexeditor flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ pngcheck flag.png
flag.png:  CORRUPTED by text conversion
ERROR: flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ hexeditor flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ pngcheck flag.png
flag.png:  CORRUPTED by text conversion
ERROR: flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/corrupt$ eog flag.png

flag: picoCTF{c0rrupt10n_1847995}
```

## Notas 
```

```

## Referencias
````

```
