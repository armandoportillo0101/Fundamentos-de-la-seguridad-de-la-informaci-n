## Descripción
```
Welcome to the challenge! In this challenge, you will explore a web application and find an endpoint that exposes a file containing a hidden flag.The application is a simple blog website where you can read articles about various topics, including an article about API Documentation. Your goal is to explore the application and find the endpoint that generates files holding the server’s memory, where a secret flag is hidden.The website is running [picoCTF News](http://verbal-sleep.picoctf.net:52529/).
```
## Solución
```
Entrar al link que aparece después de iniciar la instancia, una vez en la página de noticias dar click a "# API Documentation", después escribir el url "http://verbal-sleep.picoctf.net:64391/heapdump" y descargar el archivo, por último abres el archivo descargado con algúnd editor como por ejemplo Visual Studio Code y ahí estará la bandera

flag: picoCTF{Pat!3nt_15_Th3_K3y_546786ba}
```

## Notas 
```

```

## Referencias
````

```
