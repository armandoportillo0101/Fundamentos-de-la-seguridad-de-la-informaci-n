## Descripción
```
I made a cool website where you can announce whatever you want! Try it out!I heard templating is a cool and modular way to build web apps! Check out my website [here](http://rescued-float.picoctf.net:65189/)!
```
## Solución
```
Paso 1: Analizar la aplicación web
Al acceder a la URL proporcionada, aparecerá una página web sencilla con un campo de entrada de texto titulado «¿Qué quieres anunciar?» y un botón «Aceptar». La aplicación muestra al usuario el texto introducido.
Pulsa Intro o haz clic para ver la imagen a tamaño completo
Paso 2: Comprueba si hay vulnerabilidad SSTI
Para determinar si la aplicación es vulnerable a SSTI, introduce {{7*7}} en el campo de texto. Si el resultado muestra 49, se confirma que la aplicación evalúa la entrada, lo que indica una posible vulnerabilidad SSTI.​
Paso 3: Identificar el motor de plantillas
Los diferentes motores de plantillas interpretan las entradas de forma única. Al probar diversas cargas útiles, podemos deducir qué motor se está utilizando.
Paso 4: Aprovechar el SSTI para la ejecución remota de código
Una vez confirmado que la aplicación utiliza Jinja2, podemos crear una carga útil para ejecutar comandos del sistema.​
Recibe las historias de Mohamed Sahal en tu bandeja de entrada
Paso 5: Explora el sistema de archivos
Para localizar el indicador, muestra la lista de archivos del directorio actual:
{{ request.application.__globals__.__builtins__.__import__(“os”).popen(“ls”).read() }}

flag: picoCTF{s4rv3r_s1d3_t3mp14t3_1nj3ct10n5_4r3_c001_09365533}
```

## Notas 
```

```

## Referencias
````

```
