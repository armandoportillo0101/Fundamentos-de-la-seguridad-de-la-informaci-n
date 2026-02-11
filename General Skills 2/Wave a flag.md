## Descripción
```
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm) has extraordinarily helpful information..
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://mercury.picoctf.net/static/f95b1ee9f29d631d99073e34703a2826/warm
porti_04@DESKTOP-8HT902T:~$ ls
warm
porti_04@DESKTOP-8HT902T:~$ file warm
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=01b148cdedfc38125cac0d87e0537466d47927b1, with debug_info, not stripped
porti_04@DESKTOP-8HT902T:~$ ./warm
-bash: ./warm: Permission denied
porti_04@DESKTOP-8HT902T:~$ ./warm -h
-bash: ./warm: Permission denied
porti_04@DESKTOP-8HT902T:~$ chmod +x warm
porti_04@DESKTOP-8HT902T:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
porti_04@DESKTOP-8HT902T:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_f0668f62}
porti_04@DESKTOP-8HT902T:~$

```

## Notas 
### 1. `chmod +x warm`
- **`chmod`**: Es el comando que cambia los permisos de un archivo en sistemas tipo Unix (Linux, macOS).
- **`+x`**: Añade el permiso de ejecución (execute) al archivo.
- **`warm`**: Es el nombre del archivo al que le estás asignando el permiso de ejecución.

En resumen, `chmod +x warm` hace que el archivo `warm` sea ejecutable, permitiendo que puedas correrlo como un programa.

### 2. `./warm -h`
- **`./warm`**: Ejecuta el archivo llamado `warm` desde el directorio actual. El prefijo `./` indica que el archivo está en el directorio en el que te encuentras.
- **`-h`**: Es una opción que típicamente muestra la ayuda del programa o información sobre cómo usarlo. Muchas aplicaciones incluyen la opción `-h` (o `--help`) para ofrecer instrucciones de uso.
## Referencias
