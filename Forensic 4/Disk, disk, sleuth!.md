## Descripción
```
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/626ea9c275fbd02dd3451b81f9c5e249/dds1-alpine.flag.img.gz)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/diskdisk$ gzip -d dds1-alpine.flag.img.gz
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/diskdisk$ srch_strings dds1-alpine.flag.img.gz | grep picoCTF
'dds1-alpine.flag.img.gz': No such file
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/diskdisk$ srch_strings dds1-alpine.flag.img | grep picoCTF
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_a6f4cab5}
```

## Notas 
```
Para resolver el reto primero hay que descargar el archivo .gz que aparece en la descripción del reto y despues de descargarlo hay que descomprimirlo
```

## Referencias
````

```
