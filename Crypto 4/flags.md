## Descripción
```
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/tercer_parcial/flags$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/tercer_parcial/flags$ open flag.png

(eog:5675): EOG-WARNING **: 21:24:35.989: Couldn't load icon: Icon 'image-loading' not present in theme Adwaita
porti_04@DESKTOP-8HT902T:~/pico_retos/tercer_parcial/flags$

flag: PICOCTF{F1AG5AND5TUFF}
```

## Notas 
```
A primera vista, parece un simple cifrado de sustitución. El formato de la bandera se ajusta a la plantilla, por lo que podemos suponer con seguridad que la secuencia comienza con "picoctf".

Esto nos lleva a:

```
picoctf{f??????????ff}
```

Supongamos que la frase entre llaves tiene sentido, como la mayoría de las banderas. Como este es un desafío sobre banderas y la primera palabra comienza con `F`, podemos suponer que lo tiene `flags`(lo que tiene más sentido que `flag`).

Esto nos lleva a:

```
picoctf{flagsa??s??ff}
```

Busqué en Google " [bandera con rombos rojos](https://www.google.com/search?client=firefox-b-d&q=flag+red+dimond) ", lo que me llevó a una página de Wikipedia [Galería de banderas con rombos](https://commons.wikimedia.org/wiki/Gallery_of_flags_with_diamonds) . Allí, vi [la bandera ICS foxtrot](https://commons.wikimedia.org/wiki/Gallery_of_flags_with_diamonds#/media/File:ICS_Foxtrot.svg) , que me pareció una gran pista, ya que `foxtrot`es una de esas palabras que solo se escuchan cuando alguien está deletreando `F`en un alfabeto fonético.

La búsqueda `ICS Flags`nos lleva a la entrada de Wikipedia [sobre banderas de señales marítimas internacionales](https://en.wikipedia.org/wiki/International_maritime_signal_flags) , donde se enumeran todas las banderas.
```

## Referencias
````

```
