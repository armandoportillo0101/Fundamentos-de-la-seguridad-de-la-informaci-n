## Descripción
```
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/128/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ mkdir basicmod
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ cd basicmod
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/basicmod$ wget https://artifacts.picoctf.net/c/128/message.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/basicmod$ cat message.txt
165 248 94 346 299 73 198 221 313 137 205 87 336 110 186 69 223 213 216 216 177 138 
 porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/basicmod$ nano
 porti_04@DESKTOP-8HT902T:~/pico_retos/crypto/basicmod$ python3 exp.py
R
0
U
N
D
_
N
_
R
0
U
N
D
_
B
6
B
2
5
5
3
1
R0UND_N_R0UND_B6B25531

flag: picoCTF{R0UND_N_R0UND_B6B25531}
```

## Notas 
```
Aqui esta el archivo nano que cramos: GNU nano 6.2 exp.py data = open('message.txt', 'r').read().split() flag = '' for c in data: char = int(c) % 37 if char >= 0 and char <= 25: s = chr(char+65) elif char >= 26 and char <= 35: s = chr(char+22) elif char ==36: s = '_' flag += s print(s) print(flag)
```

## Referencias
````

```
