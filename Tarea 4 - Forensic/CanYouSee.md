## Descripción
```
How about some hide and seek?Download this file [here](https://artifacts.picoctf.net/c_titan/130/unknown.zip).
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://artifacts.picoctf.net/c_titan/130/unknown.zip
--2026-03-29 19:08:52--  https://artifacts.picoctf.net/c_titan/130/unknown.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2252265 (2.1M) [application/octet-stream]
Saving to: ‘unknown.zip’

unknown.zip                   100%[=================================================>]   2.15M   582KB/s    in 3.8s

2026-03-29 19:08:57 (582 KB/s) - ‘unknown.zip’ saved [2252265/2252265]
portidell_g3@DESKTOP-28KM9FK:~$ unzip unknown.zip
Archive:  unknown.zip
  inflating: ukn_reality.jpg
portidell_g3@DESKTOP-28KM9FK:~$ ls
ende.py  fixme3  fixme3.tar.gz  flag.txt.en  password.txt  ukn_reality.jpg  unknown.zip
portidell_g3@DESKTOP-28KM9FK:~$ exiftool ukn_reality.jpg
ExifTool Version Number         : 12.76
File Name                       : ukn_reality.jpg
Directory                       : .
File Size                       : 2.3 MB
File Modification Date/Time     : 2024:03:11 18:05:55-06:00
File Access Date/Time           : 2024:03:11 18:05:55-06:00
File Inode Change Date/Time     : 2026:03:29 19:09:31-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.01
Resolution Unit                 : inches
X Resolution                    : 72
Y Resolution                    : 72
XMP Toolkit                     : Image::ExifTool 11.88
Attribution URL                 : cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
Image Width                     : 4308
Image Height                    : 2875
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 4308x2875
Megapixels                      : 12.4
portidell_g3@DESKTOP-28KM9FK:~$

flag: picoCTF{ME74D47A_HIDD3N_6a9f5ac4}

```

## Notas 
```
Este valor es la bandera, solo que está en base 64: Attribution URL: cGljb0NURntNRTc0RDQ3QV9ISUREM05fNmE5ZjVhYzR9Cg==
```

## Referencias
````
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnROUlRjMFJEUTNRVjlJU1VSRU0wNWZObUU1WmpWaFl6UjlDZz09
```
