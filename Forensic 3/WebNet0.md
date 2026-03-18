## Descripción
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key). Recover the flag.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/webnet$ ssldump capture.pcap -k picopico.key -d
Command 'ssldump' not found, but can be installed with:
sudo apt install ssldump
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/webnet$ sudo apt install ssldump
[sudo] password for porti_04:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libnet1
The following NEW packages will be installed:
  libnet1 ssldump
0 upgraded, 2 newly installed, 0 to remove and 20 not upgraded.
Need to get 105 kB of archives.
After this operation, 327 kB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://archive.ubuntu.com/ubuntu jammy/main amd64 libnet1 amd64 1.1.6+dfsg-3.1build3 [46.9 kB]
Get:2 http://archive.ubuntu.com/ubuntu jammy/universe amd64 ssldump amd64 1.3-2build1 [58.5 kB]
Fetched 105 kB in 4s (24.5 kB/s)
Selecting previously unselected package libnet1:amd64.
(Reading database ... 60833 files and directories currently installed.)
Preparing to unpack .../libnet1_1.1.6+dfsg-3.1build3_amd64.deb ...
Unpacking libnet1:amd64 (1.1.6+dfsg-3.1build3) ...
Selecting previously unselected package ssldump.
Preparing to unpack .../ssldump_1.3-2build1_amd64.deb ...
Unpacking ssldump (1.3-2build1) ...
Setting up libnet1:amd64 (1.1.6+dfsg-3.1build3) ...
Setting up ssldump (1.3-2build1) ...
Processing triggers for man-db (2.10.2-1) ...
Processing triggers for libc-bin (2.35-0ubuntu3.8) ...
/sbin/ldconfig.real: /usr/lib/wsl/lib/libcuda.so.1 is not a symbolic link

porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/webnet$ ssldump capture.pcap -k picopico.key -d
PCAP: eth0: You don't have permission to capture on that device (socket: Operation not permitted)
ERROR: Aborting
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/webnet$ ssldump -r capture.pcap -k picopico.key -d | grep pico -A 2
    61 67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67    ag: picoCTF{nong
    73 68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63    shim.shrimp.crac
    6b 65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c    kers}..Content-L
--
    67 3a 20 70 69 63 6f 43 54 46 7b 6e 6f 6e 67 73    g: picoCTF{nongs
    68 69 6d 2e 73 68 72 69 6d 70 2e 63 72 61 63 6b    him.shrimp.crack
    65 72 73 7d 0d 0a 43 6f 6e 74 65 6e 74 2d 4c 65    ers}..Content-Le
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/webnet$

flag: picoCTF{nongshim.shrimp.crackers}
```

## Notas 
```

```

## Referencias
````

```
