## Descripción
```
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ cd pico_retos
porti_04@DESKTOP-8HT902T:~/pico_retos$ ls
forensic
porti_04@DESKTOP-8HT902T:~/pico_retos$ cd forensic
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir moonwalk
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd moonwalk
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/moonwalk$ wget https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/moonwalk$ sudo git clone https://github.com/colaclanth/sstv
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/moonwalk/sstv$ sudo python3 setup.py install
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/moonwalk$ sstv -d message.wav -o flag.jpg
Se utilizo el repositorio https://github.com/colaclanth/sstv que proporciona una herramienta para decodificar el audio y nos da una imagen que nos da la bandera


flag: picoCTF{beep_boop_im_in_space}
```

## Notas 
```

```

## Referencias
````

```
