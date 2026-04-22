## Descripción
```
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ sudo wget http://www.caesum.com/handbook/Stegsolve.jar -O stegsolve.jar
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ sudo chmod +x stegsolve.jar
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ mkdir bin
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ mv stegsolve.jar bin/
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ ls
bin  scrambled1.png  scrambled2.png
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated$ cd bin
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/pixelated/bin$ java -jar stegsolve.jar

flag: picoCTF{2a4d45c7}

```

## Notas 
```
al ejecutar el ultimo comando mostrado nos mostrara una pantalla en la que tendremos que combinar las dos imágenes que descargamos al principio. Abres la primera imagen, después abres el menú de analyse y seleccionas la opcion de combiner y eliges la segunda imagen. Después de hacer todo lo anterior te dará la bandera
```

## Referencias
````
[https://github.com/zardus/ctf-tools/blob/master/stegsolve/install](https://github.com/zardus/ctf-tools/blob/master/stegsolve/install)
```
