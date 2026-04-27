## Descripción
```
This service provides you an encrypted flag. Can you decrypt it with just N & e?Connect to the program with netcat:`$ nc verbal-sleep.picoctf.net 59502`The program's source code can be downloaded [here](https://challenge-files.picoctf.net/c_verbal_sleep/b1999e70e98a4fb11d441bd4ef60a948c1ae4a27a3a7154ed2678990b91f52e4/encrypt.py).
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ nc verbal-sleep.picoctf.net 59502
N: 26589321892521471459626582461976613362809024544026278922246860865114824975210035516383358264055674801485962856309026056868231592312680902004123532438366082
e: 65537
cyphertext: 24731418040595805996942675042584966593977181271797354780319762888420071998490216491976671181850987930556538438584028153092183795930430227658153249927588965
^C
portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_verbal_sleep/b1999e70e98a4fb11d441bd4ef60a948c1ae4a27a3a7154ed2678990b91f52e4/encrypt.py
--2026-04-26 21:48:20--  https://challenge-files.picoctf.net/c_verbal_sleep/b1999e70e98a4fb11d441bd4ef60a948c1ae4a27a3a7154ed2678990b91f52e4/encrypt.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.174.207.109, 3.174.207.125, 3.174.207.121, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.174.207.109|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 703 [application/octet-stream]
Saving to: ‘encrypt.py’

encrypt.py                    100%[=================================================>]     703  --.-KB/s    in 0s

2026-04-26 21:48:29 (25.0 MB/s) - ‘encrypt.py’ saved [703/703]

portidell_g3@DESKTOP-28KM9FK:~$ cat encrypt.py
from sys import exit
from Crypto.Util.number import bytes_to_long, inverse
from setup import get_primes

e = 65537

def gen_key(k):
    """
    Generates RSA key with k bits
    """
    p,q = get_primes(k//2)
    N = p*q
    d = inverse(e, (p-1)*(q-1))

    return ((N,e), d)

def encrypt(pubkey, m):
    N,e = pubkey
    return pow(bytes_to_long(m.encode('utf-8')), e, N)

def main(flag):
    pubkey, _privkey = gen_key(1024)
    encrypted = encrypt(pubkey, flag)
    return (pubkey[0], encrypted)

if __name__ == "__main__":
    flag = open('flag.txt', 'r').read()
    flag = flag.strip()
    N, cypher  = main(flag)
    print("N:", N)
    print("e:", e)
    print("cyphertext:", cypher)
    exit()
portidell_g3@DESKTOP-28KM9FK:~$ nano
portidell_g3@DESKTOP-28KM9FK:~$ python3 decrypt.py

flag: picoCTF{tw0_1$_pr!m305af7255}
```

## Notas 
```
Aquí está el archivo nano "decrypt.py": 
from sys import exit
from Crypto.Util.number import bytes_to_long, long_to_bytes, inverse

# 1. Standard RSA e
e = 65537

# 2. Your N and ciphertext
N = 26589321892521471459626582461976613362809024544026278922246860865114824975210035516383358264055674801485962856309026056868231592312680902004123532438366082
ciphertext = 24731418040595805996942675042584966593977181271797354780319762888420071998490216491976671181850987930556538438584028153092183795930430227658153249927588965

def gen_key():
    """
    Generates RSA private key d
    Since N is even, one factor (q) is 2.
    """
    q = 2
    p = N // q  # Integer division

    # Calculate Euler's Totient: phi(n) = (p-1)(q-1)
    phi = (p - 1) * (q - 1)

    # Calculate private exponent d
    d = inverse(e, phi)
    return d

def decrypt(d, c):
    return pow(c, d, N)

if __name__ == "__main__":
    try:
        d = gen_key()
        plain = decrypt(d, ciphertext)

        print("N:", N)
        print("d:", d)
        print("--- DECRYPTED MESSAGE ---")
        print(long_to_bytes(plain).decode(errors='ignore'))
    except Exception as e:
        print(f"An error occurred: {e}")
    exit()
```

## Referencias
````

```
