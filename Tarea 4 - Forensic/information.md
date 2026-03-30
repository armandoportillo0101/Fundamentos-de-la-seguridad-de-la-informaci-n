## Descripción
```
Files can always be changed in a secret way. Can you find the flag? [cat.jpg](https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/info$ wget https://mercury.picoctf.net/static/c28a959c5605d5f67480d5dd3a77f302/cat.jpg
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/info$ file cat.jpg
cat.jpg: JPEG image data, JFIF standard 1.02, aspect ratio, density 1x1, segment length 16, baseline, precision 8, 2560x1598, components 3
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/info$ exiftool cat.jpg
ExifTool Version Number         : 12.40
File Name                       : cat.jpg
Directory                       : .
File Size                       : 858 KiB
File Modification Date/Time     : 2021:03:15 12:24:46-06:00
File Access Date/Time           : 2024:10:26 00:37:49-06:00
File Inode Change Date/Time     : 2024:10:26 00:36:28-06:00
File Permissions                : -rw-r--r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
JFIF Version                    : 1.02
Resolution Unit                 : None
X Resolution                    : 1
Y Resolution                    : 1
Current IPTC Digest             : 7a78f3d9cfb1ce42ab5a3aa30573d617
Copyright Notice                : PicoCTF
Application Record Version      : 4
XMP Toolkit                     : Image::ExifTool 10.80
License                         : cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9
Rights                          : PicoCTF
Image Width                     : 2560
Image Height                    : 1598
Encoding Process                : Baseline DCT, Huffman coding
Bits Per Sample                 : 8
Color Components                : 3
Y Cb Cr Sub Sampling            : YCbCr4:2:0 (2 2)
Image Size                      : 2560x1598
Megapixels                      : 4.1
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/info$ echo cGljb0NURnt0aGVfbTN0YWRhdGFfMXNfbW9kaWZpZWR9| base64 -d
picoCTF{the_m3tadata_1s_modified}

flag: picoCTF{the_m3tadata_1s_modified}


```

## Notas 
```
El campo de licencia está lleno de una cadena interesante, que parece un poco fuera de lugar para un estándar de licencia real. Podría ser una cadena que esconde algo. Dado el tipo de caracteres utilizados y la longitud de la cadena, podría ser una cadena codificada en base64.
```

## Referencias
````

```
