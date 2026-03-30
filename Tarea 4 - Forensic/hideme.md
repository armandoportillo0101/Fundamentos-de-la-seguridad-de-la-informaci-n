## Descripción
```
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/262/flag.png).
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://artifacts.picoctf.net/c/262/flag.png
--2026-03-29 20:28:38--  https://artifacts.picoctf.net/c/262/flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 42945 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                      100%[=================================================>]  41.94K  --.-KB/s    in 0.01s

2026-03-29 20:28:39 (2.81 MB/s) - ‘flag.png’ saved [42945/42945]

portidell_g3@DESKTOP-28KM9FK:~$ binwalk flag.png

                                               /home/portidell_g3/flag.png
------------------------------------------------------------------------------------------------------------------------
DECIMAL                            HEXADECIMAL                        DESCRIPTION
------------------------------------------------------------------------------------------------------------------------
0                                  0x0                                PNG image, total size: 39739 bytes
39739                              0x9B3B                             ZIP archive, file count: 2, total size: 3206
                                                                      bytes
------------------------------------------------------------------------------------------------------------------------

Analyzed 1 file for 85 file signatures (187 magic patterns) in 2.0 milliseconds
portidell_g3@DESKTOP-28KM9FK:~$ binwalk -e flag.png

                                         /home/portidell_g3/extractions/flag.png
------------------------------------------------------------------------------------------------------------------------
DECIMAL                            HEXADECIMAL                        DESCRIPTION
------------------------------------------------------------------------------------------------------------------------
0                                  0x0                                PNG image, total size: 39739 bytes
39739                              0x9B3B                             ZIP archive, file count: 2, total size: 3206
                                                                      bytes
------------------------------------------------------------------------------------------------------------------------
[#] Extraction of png data at offset 0x0 declined
[+] Extraction of zip data at offset 0x9B3B completed successfully
------------------------------------------------------------------------------------------------------------------------

Analyzed 1 file for 85 file signatures (187 magic patterns) in 119.0 milliseconds
portidell_g3@DESKTOP-28KM9FK:~$ ls
extractions  flag.png  snap
portidell_g3@DESKTOP-28KM9FK:~$ cd extractions
portidell_g3@DESKTOP-28KM9FK:~/extractions$ ls
flag.png  flag.png.extracted
portidell_g3@DESKTOP-28KM9FK:~/extractions$ cd flag.png.extracted
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted$ ls
9B3B
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted$ cd 9B3B
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted/9B3B$ ls
secret
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted/9B3B$ cd secret
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted/9B3B/secret$ ls
flag.png
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted/9B3B/secret$ eog flag.png
Command 'eog' not found, but can be installed with:
sudo snap install eog  # version 47.0, or
sudo apt  install eog  # version 45.0-1ubuntu1
See 'snap info eog' for additional versions.
portidell_g3@DESKTOP-28KM9FK:~/extractions/flag.png.extracted/9B3B/secret$ sudo apt  install eog

flag: picoCTF{Hiddinng_An_imeg3_within_@n_ima9e_82101824}
```

## Notas 
```

```

## Referencias
````

```
