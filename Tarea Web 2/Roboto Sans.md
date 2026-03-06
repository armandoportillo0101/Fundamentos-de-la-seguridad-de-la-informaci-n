## Descripción
```
The flag is somewhere on this web application not necessarily on the website. Find it.Check [this](http://saturn.picoctf.net:53717/) out.
```
## Solución
```
Para iniciar el reto debemos hacer clic en “Iniciar instancia” (nota: tenemos un temporizador de 15 minutos para resolver el reto). Luego se nos abre una opción que dice “Mira [esto](http://saturn.picoctf.net:50193/) ” y debemos vincularnos a la página web.

Se nos abre una página web, pero por el nombre del reto podemos intuir que lo que nos piden es un archivo oculto, robots.txt.
Vemos que ha aparecido un hash frente a nosotros que podemos copiar y decodificar. Vayamos al sitio [https://gchq.github.io/CyberChef/](https://gchq.github.io/CyberChef/) . Luego peguemos el HASH que encontramos allí.

Copiaremos el resultado que recibimos y lo pegaremos en la URL, es así como obtendremos la bandera.

flag: picoCTF{Who_D03sN7_L1k5_90B0T5_718c9043}
```

## Notas 
```

```

## Referencias
````
[https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Wm14aFp6RXVkSGgwO2FuTXZiWGxtYVcNCmFuTXZiWGxtYVd4bExuUjRkQT09DQpzdnNzc2hqd2V1aXdsO29paG8uYnN2ZGFzbGVqZw&ieol=CRLF&oeol=VT](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true,false\)&input=Wm14aFp6RXVkSGgwO2FuTXZiWGxtYVcNCmFuTXZiWGxtYVd4bExuUjRkQT09DQpzdnNzc2hqd2V1aXdsO29paG8uYnN2ZGFzbGVqZw&ieol=CRLF&oeol=VT)
```
