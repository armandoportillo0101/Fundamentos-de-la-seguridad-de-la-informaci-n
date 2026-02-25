## Descripción
```
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:34561/](http://mercury.picoctf.net:34561/)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ curl -X HEAD http://mercury.picoctf.net:34561/index.php
Warning: Setting custom HTTP method to HEAD with -X/--request may not work the
Warning: way you want. Consider using -I/--head instead.
porti_04@DESKTOP-8HT902T:~$ curl -I HEAD http://mercury.picoctf.net:34561/index.php
curl: (6) Could not resolve host: HEAD
HTTP/1.1 200 OK
flag: picoCTF{r3j3ct_th3_du4l1ty_8f878508}
Content-type: text/html; charset=UTF-8

```

## Notas 
```
curl -X: se utiliza para especificar el método HTTP que deseas usar al hacer una solicitud. Por defecto, `curl` utiliza el método `GET`, pero con la opción `-X` puedes indicar otros métodos, como `POST`, `PUT`, `DELETE`, etc.

curl -I: se utiliza para realizar una solicitud HTTP y obtener solo los encabezados de la respuesta. La opción `-I` (o `--head`) le dice a `curl` que solicite únicamente los headers, sin descargar el cuerpo del contenido.
```

## Referencias
````
[https://keepcoding.io/blog/que-es-burp-suite/](https://keepcoding.io/blog/que-es-burp-suite/)
```
