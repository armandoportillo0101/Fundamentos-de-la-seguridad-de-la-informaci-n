## Descripción
```
Additional details will be available after launching your challenge instance.
Try [here](http://titan.picoctf.net:52607/) to find the flag
```
## Solución
```
1. Podemos ingresar algo en este formulario, hacer clic en el botón Registrar y usar Burp para capturar la información
2. Continúe haciendo clic en el botón Reenviar, obtendremos la página de autenticación 2FA
3. Simplemente ingrese algo y use burp para capturarlo
4. Podemos ver “otp=123” en formato raw. Simplemente elimine esta línea y haga clic en Avanzar. Obtendremos la bandera

picoCTF{#0TP_Bypvss_SuCc3$S_b3fa4f1a}
```

## Notas 
```

```

## Referencias
````

```
