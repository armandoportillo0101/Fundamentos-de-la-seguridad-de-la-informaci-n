## Descripción
```
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/239/atbash.jpg)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ mkdir hidetosee
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ cd hidetosee
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/hidetosee$ wget https://artifacts.picoctf.net/c/239/atbash.jpg
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/hidetosee$ eog atbash.jpg
(eog:17349): EOG-WARNING **: 11:38:43.628: Couldn't load icon: Icon 'image-loading' not present in theme Adwaita
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/hidetosee$ steghide --extract -sf atbash.jpg
Enter passphrase:
wrote extracted data to "encrypted.txt".
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/hidetosee$ cat encrypted.txt
krxlXGU{zgyzhs_xizxp_1u84w779}
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/hidetosee$

flag: picoCTF{atbash_crack_1f84d779}
```

## Notas 
```
Despues de ejecutar el comando cat nos dara una serie de caracteres codificados con el codigo atbash cipher y usamos cyberchef para decodificarla
```

## Referencias
````
[https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfMXU4NHc3Nzl9](https://gchq.github.io/CyberChef/#recipe=Atbash_Cipher\(\)&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfMXU4NHc3Nzl9)
```
