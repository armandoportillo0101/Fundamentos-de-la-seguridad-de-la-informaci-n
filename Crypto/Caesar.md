## Descripción
```
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ cd pico_retos
porti_04@DESKTOP-8HT902T:~/pico_retos$ cd crypto
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ wget https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ cat ciphertext
picoCTF{ynkooejcpdanqxeykjrbdofgkq}

flag: picoCTF{crossingtherubiconvfhsjkou}
```

## Notas 
```
Al recibir la bandera nos la dara encriptada, la puedes desencriptar en cyberchef y usas rot13. Pero ojo lo tendras que rotar las veces que sea necesario hasta que salga algo coherente
```

## Referencias
````
[https://gchq.github.io/CyberChef/#recipe=ROT13(true,true,false,30)&input=eW5rb29lamNwZGFucXhleWtqcmJkb2Zna3E](https://gchq.github.io/CyberChef/#recipe=ROT13\(true,true,false,30\)&input=eW5rb29lamNwZGFucXhleWtqcmJkb2Zna3E)
```
