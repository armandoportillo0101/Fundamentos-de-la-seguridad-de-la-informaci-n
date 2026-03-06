## Descripción
```
Do you know how to use the web inspector?Start searching [here](http://titan.picoctf.net:56691/) to find the flag
```
## Solución
```
Paso 1: Haga clic en el enlace del sitio web proporcionado. Aparecerá la siguiente página de inicio. En la navegación, nada destaca realmente.
Paso 2: Haga clic con el botón derecho del ratón en la página y desplácese hacia abajo hasta «Inspeccionar». Se abrirá una ventana independiente, como se muestra a continuación

Paso 3: Continúe inspeccionando el código fuente de cada sección. La página de inicio no parece tener nada sospechoso, por lo que pasamos a «Acerca de».

Paso 4: Al inspeccionar manualmente el código fuente de «Acerca de», observamos algo. En la clase de la sección, hay este texto:

Copiar: <section class="about" notify_true="cGljb0NURnt3ZWJfc3VjYzNzc2Z1bGx5X2QzYzBkZWRfZjZmNmI3OGF9">

Paso 5: ¿Recuerdas nuestra segunda pista? La bandera puede estar codificada o no. Así que supondremos que está codificada e intentaremos descodificarla.

A continuación, copiaremos y pegaremos la larga cadena en Cyberchef.

Traducción realizada con la versión gratuita del traductor DeepL.com

flag: picoCTF{web_succ3ssfully_d3c0ded_df0da727}
```

## Notas 
```

```

## Referencias
````
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=Y0dsamIwTlVSbnQzWldKZmMzVmpZek56YzJaMWJHeDVYMlF6WXpCa1pXUmZaR1l3WkdFM01qZDk
```
