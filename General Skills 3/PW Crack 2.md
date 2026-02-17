## Descripción
```
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/13/level2.py
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
porti_04@DESKTOP-8HT902T:~$ ls
level2.flag.txt.enc  level2.py
porti_04@DESKTOP-8HT902T:~$ cat level2.py
### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level2.flag.txt.enc', 'rb').read()



def level_2_pw_check():
    user_pw = input("Please enter correct password for flag: ")
    if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
        print("Welcome back... your flag, user:")
        decryption = str_xor(flag_enc.decode(), user_pw)
        print(decryption)
        return
    print("That password is incorrect")

El código `user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)` construye una cadena de texto a partir de los valores hexadecimales dados. Aquí está el desglose:

- `chr(0x64)` es el carácter correspondiente al código hexadecimal `0x64`, que es `'d'`.
- `chr(0x65)` es `'e'`.
- `chr(0x37)` es `'7'`.
- `chr(0x36)` es `'6'`.

Entonces, la cadena construida será `'de76'`.

level_2_pw_check()
porti_04@DESKTOP-8HT902T:~$ python3 level2.py
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
porti_04@DESKTOP-8HT902T:~$
```

## Notas 
```

```

## Referencias
````

```
