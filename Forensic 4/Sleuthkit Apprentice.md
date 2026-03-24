## Descripción
```
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir apprentice
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd apprentice
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ wget (https://artifacts.picoctf.net/c/136/disk.flag.img.gz
-bash: syntax error near unexpected token `https://artifacts.picoctf.net/c/136/disk.flag.img.gz'
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ wget https://artifacts.picoctf.net/c/136/disk.flag.img.gz
--2024-10-14 10:50:28--  https://artifacts.picoctf.net/c/136/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 47534571 (45M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz         100%[=================================>]  45.33M  2.09MB/s    in 35s

2024-10-14 10:51:04 (1.30 MB/s) - ‘disk.flag.img.gz’ saved [47534571/47534571]

porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ gzip -d disk.flag.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ fls -o 360448 disk.flag.img -r 3981
r/r * 2082(realloc):    flag.txt
r/r 2371:       flag.uni.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ fls -o 360448 disk.flag.img -r 1995
r/r 2363:       .ash_history
d/d 3981:       my_folder
+ r/r * 2082(realloc):  flag.txt
+ r/r 2371:     flag.uni.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ icat -o 360448 disk.flag.img 2363
apk add nano
mkdir my_folder
cd my_folder/
nano flag.txt
ls -al
iconv -f ascii -t utf16 > flag.uni.txt
l
ls -al
iconv -f ascii -t utf16 flag.txt > flag.uni.txt
ls -al
shred
shred -zu flag.txt
ls -al
halt
halt
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/apprentice$ icat -o 360448 disk.flag.img 2371
picoCTF{by73_5urf3r_3497ae6b}

flag: picoCTF{by73_5urf3r_3497ae6b} 
```

## Notas 
```

```

## Referencias
````

```
