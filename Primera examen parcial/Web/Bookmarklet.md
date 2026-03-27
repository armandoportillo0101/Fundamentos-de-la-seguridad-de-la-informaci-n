## Descripción
```
Why search for the flag when I can make a bookmarklet to print it for me?

Additional details will be available after launching your challenge instance.
Why search for the flag when I can make a bookmarklet to print it for me?Browse [here](http://titan.picoctf.net:61499/), and find the flag!
```
## Solución
```
Hay que ver que contiene el enlace despues de presionar el botón de launch instance.

Habrá una función de Javascript que descifra una bandera cifrada. Parece ser lo que estamos buscando. Copia el código que te aparece e inspecciona la página web. Ve a la consola y pega este código y presiono Enter.

flag: picoCTF{p@g3_turn3r_cebccdfe}

```

## Notas 
```
Este el codigo que aparece en la pagina: javascript:(function() { var encryptedFlag = "àÒÆÞ¦È¬ëÙ£Ö�ÓÚåÛÑ¢ÕÓÉÕËÆÒÇÚËí"; var key = "picoctf"; var decryptedFlag = ""; for (var i = 0; i < encryptedFlag.length; i++) { decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256); } alert(decryptedFlag); })();
```

## Referencias
````

```
