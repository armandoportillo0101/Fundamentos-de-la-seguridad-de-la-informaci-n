## Descripción
```
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/214/disk.flag.img.gz)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ wget https://artifacts.picoctf.net/c/214/disk.flag.img.gz
--2026-03-22 16:04:47--  https://artifacts.picoctf.net/c/214/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360927 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz            100%[=========================================>]  42.31M  1.88MB/s    in 21s     l
2026-03-22 16:05:10 (2.00 MB/s) - ‘disk.flag.img.gz’ saved [44360927/44360927]

porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ gzip -d disk.flag.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ ls -lah
total 401M
drwxr-xr-x  2 porti_04 porti_04 4.0K Oct 15 16:05 .
drwxr-xr-x 23 porti_04 porti_04 4.0K Oct 14 11:18 ..
-rw-r--r--  1 porti_04 porti_04 400M Mar 15  2023 disk.flag.img
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ file disk.flag.img
disk.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0xc,223,19), startsector 2048, 204800 sectors; partition 2 : ID=0x82, start-CHS (0xc,223,20), end-CHS (0x19,159,6), startsector 206848, 204800 sectors; partition 3 : ID=0x83, start-CHS (0x19,159,7), end-CHS (0x32,253,11), startsector 411648, 407552 sectors
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ mmls disk.flag.img
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ fls -o 0000411648 disk.flag.img
d/d 460:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 81: proc
d/d 82: dev
d/d 83: tmp
d/d 84: lib
d/d 87: var
d/d 96: usr
d/d 106:        bin
d/d 120:        sbin
d/d 466:        media
d/d 470:        mnt
d/d 471:        opt
d/d 472:        root
d/d 473:        run
d/d 475:        srv
d/d 476:        sys
d/d 2041:       swap
V/V 51001:      $OrphanFiles
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ fls -o 0000411648 disk.flag.img 472
r/r 1875:       .ash_history
r/r * 1876(realloc):    flag.txt
r/r 1782:       flag.txt.enc
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ icat -o 0000411648 disk.flag.img 1782
Salted__S�+%���+�O��k�ђ(A����c��
                                @]ԣ
L�ޢȤ7� ���؎$�'%porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ icat -o 0000411648 disk.flag.imxt.enc > flag.t
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ file flag.txt.enc
flag.txt.enc: openssl enc'd data with salted password
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ icat -o 0000411648 disk.flag.img 1875
touch flag.txt
nano flag.txt
apk get nano
apk --help
apk add nano
nano flag.txt
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ openssl aes256 -salt -d -in flag.txt.enc -k un
breakablepassword
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40E73087BF7F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:124:
,C����\���O��{X�����92�����Eq�porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ cat flag.txt
cat: flag.txt: No such file or directory
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$ openssl aes256 -salt -d -in flag.txt.enc -k unbreakablepassword1234567
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
40E7E5DF987F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:124:
picoCTF{h4un71ng_p457_1d02081e}porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/operationorchid$

flag: picoCTF{h4un71ng_p457_1d02081e}
```

## Notas 
```

```

## Referencias
````

```
