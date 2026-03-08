## Descripción
```
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir whatlieswhitin
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd  whatlieswhitin
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/whatlieswhitin$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/whatlieswhitin$ sudo gem install zsteg
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/whatlieswhitin$ zsteg -a buildings.png | grep pico
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/whatlieswhitin$

flag: picoCTF{h1d1ng_1n_th3_b1t5}

```

## Notas 
```
Para encontrar la bandera instalamos lo siguiente mediante este comando: sudo gem install zsteg.
```

## Referencias
````

```
