## Descripción
```
Can you find the robots? `https://jupiter.challenges.picoctf.org/problem/60915/` ([link](https://jupiter.challenges.picoctf.org/problem/60915/)) or http://jupiter.challenges.picoctf.org:60915
```
## Solución
```
Despues de meternos a la pagina https://jupiter.challenges.picoctf.org/problem/60915/, escribimos en el url de busqueda https://jupiter.challenges.picoctf.org/problem/60915/robots.txt. 
Despues nos aparecera: 
User-agent: *
Disallow: /8028f.html

y pegaremos /8028f.html en la url de busqueda:  https://jupiter.challenges.picoctf.org/problem/60915/8028f.html

ingresamos y nos dará la bandera. 

bandera: picoCTF{ca1cu1at1ng_Mach1n3s_8028f}
```

## Notas 
```
robots.txt` es un archivo de texto simple que se coloca en la raíz de un sitio web para dar instrucciones a los rastreadores web (también conocidos como "bots" o "web crawlers").
```

## Referencias
````

```
