## Descripción
```
Can you make sense of this file? Download the file [here](https://artifacts.picoctf.net/c/472/enc_flag).
```

## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/472/enc_flag
--2026-02-10 18:08:10--  https://artifacts.picoctf.net/c/472/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.60, 3.161.225.11, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: ‘enc_flag’

enc_flag                    100%[=========================================>]     349  --.-KB/s    in 0s

--2026-02-10 18:09:03 (39.2 MB/s) - ‘enc_flag’ saved [349/349]

porti_04@DESKTOP-8HT902T:~$ ls
enc_flag  wget-log
porti_04@DESKTOP-8HT902T:~$ cat enc_flag
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKeldWaHdRMDB4V2tWU2JFNVdDbUpXV2tkVU1WcFhWVzFHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
porti_04@DESKTOP-8HT902T:~$ git log enc_flag
fatal: not a git repository (or any of the parent directories): .git
porti_04@DESKTOP-8HT902T:~$ strings enc_flag | grep pico
porti_04@DESKTOP-8HT902T:~$ base64 -d enc_flag
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JzWVhwQ00xWkVSbE5WCmJWWkdUMVpXVW1GdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
porti_04@DESKTOP-8HT902T:~$ base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_73494190}
porti_04@DESKTOP-8HT902T:~$
```

## Notas 
El comando `base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d` decodifica un archivo o cadena codificada en base64 múltiples veces.

- `base64 -d`: decodifica datos en formato base64.
- `enc_flag`: es el archivo o texto codificado en base64 que se está procesando.
- Las tuberías (`|`) encadenan las decodificaciones para aplicar el proceso repetidamente.

En este caso, el archivo `enc_flag` se decodifica 6 veces consecutivas hasta revelar el contenido original. Cada ejecución toma el resultado de la anterior hasta llegar al dato final

## Referencias
