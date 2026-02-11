## Descripción
```
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static)? This [BASH script](https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/ltdis.sh) might help!
```

## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static
--2026-02-10 15:16:04--  https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/static
porti_04@DESKTOP-8HT902T:~$ wget https://mercury.picoctf.net/static/0f6ea599582dcce7b4f1ba94e3617baf/ltdis.sh
porti_04@DESKTOP-8HT902T:~$ cat static
 HH/lib64/ld-linux-x86-64.so.2GNUGNU�b����Q����=�       c=
                                                           Y h "libc.so.6puts__cxa_finalize__libc_start_mainGL � � � � � � H�H��gisterTMCloneTable__gmon_start___ITM_registerTMCloneTableu␦i  1�
 H��t��H���5�
 �%�
 @�%�
 h������%�
H�=�����^H��H���PTL��H�
 �DH�=�
 UH��
 H9�H��tH�Z
]��f.�]�@f.�H�=�
 H�5�
 UH)�H��H��H��H��?H�H��tH�!
 H��t
     ]��f�]�@f.��=I
 u/H�=�  UH��t
8#TT 1tt$D���o�N=�       �
�� � @ @ �0@)pf�p�V``�^�y�
porti_04@DESKTOP-8HT902T:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_6f8c8200}
porti_04@DESKTOP-8HT902T:~$

```
## Notas 
```
El comando `strings static | grep pico` funciona de manera muy similar al ejemplo anterior, pero en este caso, se está analizando un archivo llamado `static`.

- **`strings static`**: Extrae todas las secuencias de texto legible del archivo llamado `static`. Esto es útil cuando `static` es un archivo binario o cualquier archivo que no sea fácilmente legible de forma directa.
- **`| grep pico`**: Luego filtra la salida de `strings` para mostrar solo las líneas que contienen la palabra "pico".
```
## Referencias
