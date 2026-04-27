## Descripción
```
We found a leak of a blackmarket website's login credentials. Can you find the password of the user `cultiris` and successfully decrypt it?Download the leak [here](https://artifacts.picoctf.net/c/151/leak.tar).The first user in `usernames.txt` corresponds to the first password in `passwords.txt`. The second user corresponds to the second password, and so on.
```
## Solución
```
Paso 1.- Descargue el archivo .zip que aparece en la explicación

Paso 2.- Al abrir el archivo, buscar en él hasta llegar a un carpeta que contenga dos archivos .txt "passwords" y "usernames".

Paso 3.- Ya estando en la carpeta y habiendo ubicado los archivos, abrir el txt "passwords"

Paso 4.- En el archivo "passowords" buscar algo como: cvpbPGS{P7e1S_54I35_71Z3} o que tenga los corchetes, pues es la única línea que lo contiene y esa es la bandera, solo faltaría decodificarla

Paso 5.- al encontrar algo como "cvpbPGS{P7e1S_54I35_71Z3}", decodificarla en root 13

flag: picoCTF{C7r1F_54V35_71M3}
```

## Notas 
```

```

## Referencias
````
https://rot13.com/
```
