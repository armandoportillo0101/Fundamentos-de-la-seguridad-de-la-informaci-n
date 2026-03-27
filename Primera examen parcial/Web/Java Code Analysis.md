## Descripción
```
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!Here are the credentials to get you started:

- Username: "user"
- Password: "user"

Source code can be downloaded [here](https://artifacts.picoctf.net/c/483/bookshelf-pico.zip).Website can be accessed [here!](http://saturn.picoctf.net:49333/).
```
## Solución
```
Así que nos dieron las credenciales para una cuenta de usuario que es “gratuita”. El sitio web contiene tres libros y los usuarios “gratuitos” solo pueden leer uno, mientras que los usuarios premium, incluidos los gratuitos, premium y administradores, pueden leer uno cada uno. Obviamente no se nos permite leer el libro “Bandera”; debemos ser administradores.

Las sugerencias giran en torno a la manipulación de tokens JWT y la búsqueda en archivos fuente para generar un nuevo token JWT.

El código fuente muestra claramente que el sitio web utiliza tokens JWT para autorizar a los usuarios y otorgar acceso a los libros en función de sus roles.
# Servicio JWT

El código fuente de JwtService parece bastante sencillo y rápidamente detectamos la línea 27, que es donde se genera SECRET_KEY. Esto es algo que necesitaremos saber para codificar nuestros propios tokens JWT, por lo tanto, debemos echar un vistazo al código fuente de Según este código fuente, primero intenta leer la clave desde un archivo local llamado **server_secret.txt** ; sin embargo, si no se encuentra el archivo, se utiliza una cadena “aleatoria” codificada de 1234 en su lugar.

Aquí, probablemente sea seguro asumir que ni nosotros ni el servidor podremos acceder a este archivo, por lo que podemos avanzar con la suposición de que **SECRET_KEY** será **1234** .

Primero debemos decodificar el token JWT que poseemos actualmente antes de intentar codificar el nuestro utilizando esto.

# **Descodificación de JWT**

Podemos utilizar el sitio web [**jwt.io**](https://jwt.io/) para decodificar y codificar tokens JWT.

Al copiar y pegar nuestro token portador actual de la solicitud de Burp Suite que capturamos anteriormente, podemos ver la carga útil del token JWT.

Entonces, aquí está el token JWT en uso, así que modifiquémoslo.la `**SecretGenerator**`clase, estableceremos el valor del campo userId en 2.

Además, como ya sabemos antes, 1234 debería funcionar como SECRET_KEY.

Ahora que tenemos toda esta información, podemos usar jwt.io para codificar un nuevo token JWT.


flag: picoCTF{w34k_jwt_n0t_g00d_42f5774a}
```

## Notas 
```

```

## Referencias
````
https://jwt.io/
```
