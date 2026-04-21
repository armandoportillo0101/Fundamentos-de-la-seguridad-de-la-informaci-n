## Descripción
```
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/mindpqs$ wget https://mercury.picoctf.net/static/51d68e61bb41207a55f24e753f07c5a3/values
--2024-10-23 10:24:04--  
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/mindpqs$ cat  values
Decrypt my super sick RSA:
c: 62324783949134119159408816513334912534343517300880137691662780895409992760262021
n: 1280678415822214057864524798453297819181910621573945477544758171055968245116423923
e: 65537porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/mindpqs
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/mindpqs$ python3
Python 3.10.12 (main, Sep 11 2024, 15:47:36) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> c =  62324783949134119159408816513334912534343517300880137691662780895409992760262021
>>> e = 65537
>>> p =  1899107986527483535344517113948531328331
>>> q =  674357869540600933870145899564746495319033
>>> n = p * q
>>> n
1280678415822214057864524798453297819181910621573945477544758171055968245116423923
>>> tn = (p-1) * (q-1)
>>> tn
1280678415822214057864524798453297819181234364596418349127352680639289550089776560
>>> d = pow (e, -1, tn)
>>> d
449332735606084960351204406909610297301574728466820933515942864925459265983556193
>>> m = pow(c, d, n)
>>> m
13016382529449106065927291425342535437996222135352905256639555654677400177227645
>>> bytes.fromhex( hex(m)[2:] ).decode
<built-in method decode of bytes object at 0x7f09fe954cb0>
>>> bytes.fromhex( hex(m)[2:] ).decode()
'picoCTF{sma11_N_n0_g0od_05012767}'
>>>

flag: picoCTF{sma11_N_n0_g0od_05012767}
```

## Notas 
```

```

## Referencias
````

```
