## Descripción
```
How about trying to match a regular expressionThe website is running [here](http://saturn.picoctf.net:49330/).
```
## Solución
```
Intentando hacer coincidir nuestra entrada de formulario con el patrón de expresión regular ^p.....F comentado en el código fuente de send_request(). ^ ancla el patrón al inicio del texto, coincide con cualquier carácter y, finalmente, un carácter F.

Flag: picoCTF{succ3ssfully_matchtheregex_c64c9546}
```

## Notas 
```
Al inspeccionar el código fuente de la página web, se observa el siguiente formato:


```
<form action="#" onsubmit="return send_request()">
  <input type="text" id="name" name="input" placeholder="Input text">
  <br>
  <br>
  <button id="submit-but" type="submit" id="submit-button">SUBMIT</button>
</form>
```

Con el siguiente script javascript `send_request()`:

```
<script>
  function send_request() {
    let val = document.getElementById("name").value;
    // ^p.....F!?
    fetch(`/flag?input=${val}`)
      .then(res => res.text())
      .then(res => {
        const res_json = JSON.parse(res);
        alert(res_json.flag)
        return false;
      })
    return false;
  }
</script>
```
```

## Referencias
````

```
