## Descripción
```
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/17/level3.py
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
porti_04@DESKTOP-8HT902T:~$ ls
flag.txt  level3.flag.txt.enc  level3.hash.bin  level3.py  warm
porti_04@DESKTOP-8HT902T:~$ nano level3.py
el nano: 
import hashlib

def level_3_pw_check():

    # The code below is altered.

    pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]

    for i in range(0, len(pos_pw_list)):

    # user_pw = input("Please enter correct password for flag: ")
        user_pw = pos_pw_list[i]
        user_pw_hash = hash_pw(user_pw)

        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key)

tome los valores de entre los corchetes de esta linea y los converti a texto de esta linea: pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"] 
bandera: _picoCTF{m45h_fl1ng1ng_cd6ed2eb}_
```

## Notas 
```

```

## Referencias
````

```
