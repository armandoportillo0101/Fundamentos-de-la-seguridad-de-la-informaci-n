## Descripción
```
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/290/SafeOpener.class) is supposed to help me with retrieving the lost key. Can you help me unlock my safe?
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ wget https://artifacts.picoctf.net/c/290/SafeOpener.class
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ file SafeOpener.class
SafeOpener.class: compiled Java class data, version 52.0 (Java 1.8)
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ ls
SafeOpener.class  vd3  vd4  vd5
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ strings -t x SafeOpener.class | grep picoCTF
    31d ,picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_7db9fb8c}

flag: picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_7db9fb8c}
```

## Notas 
```

```

## Referencias
````

```
