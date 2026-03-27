## Descripción
```
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.
Connect to this PostgreSQL server and find the flag!`psql -h saturn.picoctf.net -p 55850 -U postgres pico`Password is `postgres`
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2$ psql -h saturn.picoctf.net -p 55850 -U postgres pico
Password for user postgres:
psql (14.13 (Ubuntu 14.13-0ubuntu0.22.04.1), server 15.2 (Debian 15.2-1.pgdg110+1))
WARNING: psql major version 14, server major version 15.
         Some psql features might not work.
Type "help" for help.

pico=# Select * from flags;
 id | firstname | lastname  |                address
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

pico=#

flag:  picoCTF{L3arN_S0m3_5qL_t0d4Y_31fd14c0}
```

## Notas 
```
Verifique la función “ayuda” donde tenía opciones para verificar los comandos “psql” usando “?”, lo usé y verifiqué las consultas. Allí tengo una opción para describir las tablas (“\d”), usándola obtuve todos los nombres de las tablas y luego simplemente envié una consulta SQL básica a la tabla “flags” real (la obtuve usando el comando “\d”)
```

## Referencias
````

```
