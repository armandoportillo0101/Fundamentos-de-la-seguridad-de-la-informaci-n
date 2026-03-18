## Descripción
```
We found this [file](https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n). Recover the flag.

```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd tunnelvision
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ wget https://mercury.picoctf.net/static/7b2d7c26630e977197022d0af09e3aeb/tunn3l_v1s10n
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ ls
tunn3l_v1s10n
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ file tunn3l_vision
tunn3l_vision: cannot open `tunn3l_vision' (No such file or directory)
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ exiftool tunn3l_vision
Error: File not found - tunn3l_vision
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ exiftool tunn3l_v1s10n
ExifTool Version Number         : 12.40
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.8 MiB
File Modification Date/Time     : 2021:03:15 12:24:47-06:00
File Access Date/Time           : 2024:10:09 10:27:36-06:00
File Inode Change Date/Time     : 2024:10:09 10:27:36-06:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Unknown (53434)
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Red Mask                        : 0x27171a23
Green Mask                      : 0x20291b1e
Blue Mask                       : 0x1e212a1d
Alpha Mask                      : 0x311a1d26
Color Space                     : Unknown (,5%()
Rendering Intent                : Unknown (826103054)
Image Size                      : 1134x306
Megapixels                      : 0.347
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ xxd -l 100 tunn3l_v1s1on
xxd: tunn3l_v1s1on: No such file or directory
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ xxd -l 100 tunn3l_v1s10n
00000000: 424d 8e26 2c00 0000 0000 bad0 0000 bad0  BM.&,...........
00000010: 0000 6e04 0000 3201 0000 0100 1800 0000  ..n...2.........
00000020: 0000 5826 2c00 2516 0000 2516 0000 0000  ..X&,.%...%.....
00000030: 0000 0000 0000 231a 1727 1e1b 2920 1d2a  ......#..'..) .*
00000040: 211e 261d 1a31 2825 352c 2933 2a27 382f  !.&..1(%5,)3*'8/
00000050: 2c2f 2623 332a 262d 2420 3b32 2e32 2925  ,/&#3*&-$ ;2.2)%
00000060: 3027 2333                                0'#3
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ hexeditor tunn3l_v1s10n
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ eog  tunn3l_v1s10n

(eog:6435): EOG-WARNING **: 10:36:51.069: Couldn't load icon: Icon 'image-loading' not present in theme Adwaita
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ exiftool  tunn3l_v1s10n
ExifTool Version Number         : 12.40
File Name                       : tunn3l_v1s10n
Directory                       : .
File Size                       : 2.8 MiB
File Modification Date/Time     : 2024:10:09 10:36:34-06:00
File Access Date/Time           : 2024:10:09 10:36:51-06:00
File Inode Change Date/Time     : 2024:10:09 10:36:34-06:00
File Permissions                : -rw-r--r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 306
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x306
Megapixels                      : 0.347
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ hexeditor tunn3l_v1s10n
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ hexeditor tunn3l_v1s10n
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/tunnelvision$ eog  tunn3l_v1s10n

(eog:7227): EOG-WARNING **: 10:40:10.473: Couldn't load icon: Icon 'image-loading' not present in theme Adwaita


flag: picoCTF{qu1t3_a_v13w_2020}
```

## Notas 
```

```

## Referencias
````

```
