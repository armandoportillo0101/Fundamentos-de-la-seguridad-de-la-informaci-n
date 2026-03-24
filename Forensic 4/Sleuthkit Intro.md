## Descripción
```
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Additional details will be available after launching your challenge instance.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ dir
apprentice    extensions         matryoshka    operationorchid  sleuthkit     webnet1
capture.pcap  gloryofthegarden   milkslap      picopico.key     someta        whatlieswhitin
corrupt       like1000           moonwalk      sharkonwire1     tunnelvision  whitepages
diskdisk      macrohardweakedge  operationoni  sharkonwire2     webnet
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir sleuthkitIntro
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd sleuthkitIntro
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ wget https://artifacts.picoctf.net/c/164/disk.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ gzip -d disk.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ ls
disk.img
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ file disk.img
disk.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,190,50), startsector 2048, 202752 sectors
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ mmls disk.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$ nc saturn.picoctf.net 60977
What is the size of the Linux partition in the given disk image?
Length in sectors: 0000202752
0000202752
Great work!
picoCTF{mm15_f7w!}
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sleuthkitIntro$

flag: picoCTF{mm15_f7w!}
```

## Notas 
```

```

## Referencias
````

```
