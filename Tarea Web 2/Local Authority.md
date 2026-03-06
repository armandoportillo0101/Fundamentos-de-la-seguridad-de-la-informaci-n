## Descripción
```
Additional details will be available after launching your challenge instance.
Can you get the flag?Go to this [website](http://saturn.picoctf.net:58672/) and see what you can discover.
```
## Solución
```
Despues el reto, vemos que hay botton launcher que te genera un link de una pagina web parte del reto, es una pagina donde te puedes loggear pero al momento de loggearte no te deja, por lo que procedemos a ver el codigo fuente de la pagina:
|   |   |
|---|---|
||<!DOCTYPE html>|
||<html lang="en">|
||<head>|
||<meta charset="UTF-8">|
||<meta name="viewport" content="width=device-width, initial-scale=1.0">|
||<meta http-equiv="X-UA-Compatible" content="ie=edge">|
||<link rel="stylesheet" href="[style.css](http://saturn.picoctf.net:50795/style.css)">|
||<title>Login Page</title>|
||</head>|
||<body>|
||<script src="[secure.js](http://saturn.picoctf.net:50795/secure.js)"></script>|
|||
||<p id='msg'></p>|
|||
||<form hidden action="admin.php" method="post" id="hiddenAdminForm">|
||<input type="text" name="hash" required id="adminFormHash">|
||</form>|
|||
||<script type="text/javascript">|
||function filter(string) {|
||filterPassed = true;|
||for (let i =0; i < string.length; i++){|
||cc = string.charCodeAt(i);|
|||
||if ( (cc >= 48 && cc <= 57) \||
||(cc >= 65 && cc <= 90) \||
||(cc >= 97 && cc <= 122) )|
||{|
||filterPassed = true;|
||}|
||else|
||{|
||return false;|
||}|
||}|
|||
||return true;|
||}|
|||
||window.username = "";|
||window.password = "";|
|||
||usernameFilterPassed = filter(window.username);|
||passwordFilterPassed = filter(window.password);|
|||
||if ( usernameFilterPassed && passwordFilterPassed ) {|
|||
||loggedIn = checkPassword(window.username, window.password);|
|||
||if(loggedIn)|
||{|
||document.getElementById('msg').innerHTML = "Log In Successful";|
||document.getElementById('adminFormHash').value = "2196812e91c29df34f5e217cfd639881";|
||document.getElementById('hiddenAdminForm').submit();|
||}|
||else|
||{|
||document.getElementById('msg').innerHTML = "Log In Failed";|
||}|
||}|
||else {|
||document.getElementById('msg').innerHTML = "Illegal character in username or password."|
||}|
||</script>|
|||
||</body>|
||</html>|
|||
Al ver y revisar este codigo pasamos al archivo "secure.js":
function checkPassword(username, password)
{
  if( username === 'admin' && password === 'strongPassword098765' )
  {
    return true;
  }
  else
  {
    return false;
  }
}
Por lo que vemos este archivo nos da el usuario y la contreseña de dicho usuario, las ingresamos en la pagina para loggearse y nos dara la bandera

flag: picoCTF{j5_15_7r4n5p4r3n7_05df90c8}
```

## Notas 
```

```

## Referencias
````

```
