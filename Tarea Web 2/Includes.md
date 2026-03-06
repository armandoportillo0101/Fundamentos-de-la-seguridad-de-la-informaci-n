## Descripción
```
Can you get the flag?

Additional details will be available after launching your challenge instance.
Go to this [website](http://saturn.picoctf.net:52484/) and see what you can discover.
```
## Solución
```
Hay que ver el contenido del link que se nos proporiciona despues de pulsar el boton de launch instance, nos aparecerá una pagina con x informacion. Tienes que ver el codigo fuente de dicha fuente: 
|   |
|---|
|<!DOCTYPE html>|
||<html lang="en">|
||<head>|
||<meta charset="UTF-8">|
||<meta name="viewport" content="width=device-width, initial-scale=1.0">|
||<meta http-equiv="X-UA-Compatible" content="ie=edge">|
||<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:52484/style.css)">|
||<title>On Includes</title>|
||</head>|
||<body>|
||<script src="[script.js](http://saturn.picoctf.net:52484/script.js)"></script>|
|||
||<h1>On Includes</h1>|
||<p>Many programming languages and other computer files have a directive,|
||often called include (sometimes copy or import), that causes the|
||contents of a second file to be inserted into the original file. These|
||included files are called copybooks or header files. They are often used|
||to define the physical layout of program data, pieces of procedural code|
||and/or forward declarations while promoting encapsulation and the reuse|
||of code.</p>|
||<br>|
||<p> Source: Wikipedia on Include directive </p>|
||<button type="button" onclick="greetings();">Say hello</button>|
||</body>|
||</html>|

la bandera se encuentra divida en dos partes y en cada una esta en un archivo diferente, la primera parte está en [style.css] y la segunda está en [script.js]

flag: picoCTF{1nclu51v17y_1of2_f7w_2of2_6edef411}
```

## Notas 
```

```

## Referencias
````

```