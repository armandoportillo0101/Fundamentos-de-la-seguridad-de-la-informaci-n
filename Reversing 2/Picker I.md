## Descripción
```
This service can provide you with a random number, but can it do anything else?

Additional details will be available after launching your challenge instance.
The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/513/picker-I.py).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ wget https://artifacts.picoctf.net/c/513/picker-I.py
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nano picker-I.py
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nc saturn.picoctf.net 54518
Try entering "getRandomNumber" without the double quotes...
==> win
0x70 0x69 0x63 0x6f 0x43 0x54 0x46 0x7b 0x34 0x5f 0x64 0x31 0x34 0x6d 0x30 0x6e 0x64 0x5f 0x31 0x6e 0x5f 0x37 0x68 0x33 0x5f 0x72 0x30 0x75 0x67 0x68 0x5f 0x62 0x35 0x32 0x33 0x62 0x32 0x61 0x31 0x7d
Try entering "getRandomNumber" without the double quotes...
==>

flag: picoCTF{4_d14m0nd_1n_7h3_r0ugh_b523b2a1}
```

## Notas 
```
El codigo hexadecimal que se nos dio lo decodificamos en cyberchef
```

## Referencias
````
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')&input=MHg3MCAweDY5IDB4NjMgMHg2ZiAweDQzIDB4NTQgMHg0NiAweDdiIDB4MzQgMHg1ZiAweDY0IDB4MzEgMHgzNCAweDZkIDB4MzAgMHg2ZSAweDY0IDB4NWYgMHgzMSAweDZlIDB4NWYgMHgzNyAweDY4IDB4MzMgMHg1ZiAweDcyIDB4MzAgMHg3NSAweDY3IDB4NjggMHg1ZiAweDYyIDB4MzUgMHgzMiAweDMzIDB4NjIgMHgzMiAweDYxIDB4MzEgMHg3ZA
```
