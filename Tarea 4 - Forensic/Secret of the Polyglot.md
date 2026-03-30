## Descripción
```
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/97/flag2of2-final.pdf).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ wget https://artifacts.picoctf.net/c_titan/97/flag2of2-final.pdf
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ mv flag2of2-final.pdf flag2of2-final.png
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ eog flag2of2-final.png
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ ghex flag2of2-final.png
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ ghex flag2of2-final.png
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ ls
flag2of2-final.pdf  flag2of2-final.png  output.pdf
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ pdftotext output.pdf output.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ cat
flag2of2-final.pdf  flag2of2-final.png  output.pdf          output.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/sotp$ cat output.txt
1n_pn9_&_pdf_724b1287}

flag: picoCTF{f1u3n7_1n_pn9_&_pdf_724b1287}
```

## Notas 
```
Desde exiftool, sabemos que hay algo oculto después del fragmento IEND, podemos desplazarnos hasta la parte inferior o usar la búsqueda y el filtro. Desde aquí, veremos una firma de encabezado PDF después del fragmento final del PNG. Podemos extraer el hexadecimal PDF en un nuevo archivo y guardarlo como flag.pdf, pero recuerda empezar desde `25 50 44 46`. Copie y pegue el PDF hexadecimal en un nuevo archivo y lo guarde como output.pdf.

Por ultimo solo lo abri y me dio la segunda parte de la bandera, ya que en este reto se nos da la bandera en dos partes.
```

## Referencias
````

```
