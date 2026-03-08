## Descripción
```
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ cd picoCTF_retos
porti_04@DESKTOP-8HT902T:~/picoCTF_retos$ dir
porti_04@DESKTOP-8HT902T:~/picoCTF_retos$ cd ..
porti_04@DESKTOP-8HT902T:~$ cd pico_retos
porti_04@DESKTOP-8HT902T:~/pico_retos$ dir
forensic
porti_04@DESKTOP-8HT902T:~/pico_retos$ cd forensic
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir gloryofthegarden
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd gloryofthegarden
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/gloryofthegarden$ wget https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/gloryofthegarden$ hexeditor garden.jpg

flag: picoCTF{more_than_m33ts_the_3y3eBdBd2cc}
```

## Notas 
```
Al abrir hacer que garden.jpg se abra como un archivo hexadecimal, tenemos que dar control w, después damos clic a la opcion de búsqueda de texto e ingresamos "picoCTF", después de hacer veremos la bandera[](https://github.com/armandoportillo0101/Seguridad-de-Redes/blob/main/Plantilla.md#notas-adicionales)
```

## Referencias
````

```
