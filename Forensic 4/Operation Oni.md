## Descripción
```
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download disk image](https://artifacts.picoctf.net/c/69/disk.img.gz)
- Remote machine: `ssh -i key_file -p 51881 ctf-player@saturn.picoctf.net`
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ cd pico_retos
porti_04@DESKTOP-8HT902T:~/pico_retos$ dir
forensic
porti_04@DESKTOP-8HT902T:~/pico_retos$ cd forensic
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ dir
apprentice    extensions         matryoshka    operationorchid  sleuthkit     webnet1
capture.pcap  gloryofthegarden   milkslap      picopico.key     someta        whatlieswhitin
corrupt       like1000           moonwalk      sharkonwire1     tunnelvision  whitepages
diskdisk      macrohardweakedge  operationoni  sharkonwire2     webnet
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd operationoni
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ wget https://artifacts.picoctf.net/c/69/disk.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ gzip -d disk.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ ls -lah
total 231M
drwxr-xr-x  2 porti_04 porti_04 4.0K Oct 15 15:56 .
drwxr-xr-x 23 porti_04 porti_04 4.0K Oct 14 11:18 ..
-rw-r--r--  1 porti_04 porti_04 230M Aug  4  2023 disk.img
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ fls -o 0000206848 disk.img -r
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ fls -o 0000206848 disk.img 470 -r
r/r 2344:       .ash_history
d/d 3916:       .ssh
+ r/r 2345:     id_ed25519
+ r/r 2346:     id_ed25519.pub
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ icat -o 0000206848 disk.img 2344
ssh-keygen -t ed25519
ls .ssh/
halt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ icat -o 0000206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ icat -o 0000206848 disk.img 2345 > key_file
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$ chmod 600 key_file
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$  ssh -i key_file -p 63916 ctf-player@saturn.picoctf.net
ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt
picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$ Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationoni$

flag: picoCTF{k3y_5l3u7h_339601ed}
```

## Notas 
```

```

## Referencias
````

```
