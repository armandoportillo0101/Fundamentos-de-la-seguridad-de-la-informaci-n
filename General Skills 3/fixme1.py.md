## Descripción
```
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/26/fixme1.py
porti_04@DESKTOP-8HT902T:~$ ls
fixme1.py  wget-log
porti_04@DESKTOP-8HT902T:~$ nano fixme1.py
  GNU nano 6.2                                       fixme1.py
import random


def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])


flag_enc = chr(0x15) + chr(0x07) + chr(0x08) + chr(0x06) + chr(0x27) + chr(0x21) + chr(0x23) + chr(0x15) + ch>


flag = str_xor(flag_enc, 'enkidu')
print('That is correct! Here is your flag: ' + flag)

porti_04@DESKTOP-8HT902T:~$ python3 fixme1.py
That is correct! Here is your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}


```

## Notas 
```

```

## Referencias
````

```
