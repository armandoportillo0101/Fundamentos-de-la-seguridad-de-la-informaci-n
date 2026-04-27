## Descripción
```
We received an encrypted message. The modulus is built from primes large enough that factoring them isn’t an option, at least not today. See if you can make sense of the numbers and reveal the flag.Download the [message](https://challenge-files.picoctf.net/c_amiable_citadel/fddf51f15bd9f4145c4a4ebee5dfe7994bdab6393453f41f02c59cfd23a87fda/message.txt).
```
## Solución
```
Paso 1.- Descarge el archivo que aparece en la descripción del reto

Paso 2.- Hice un archivo llamado "solution.py": 
  GNU nano 7.2                                           solution.py
import gmpy2

e = 20
c = 6406374308104068575005667020962740842386353182361792134741714717629629240311434067717625885909023964707559165296004>

root, exact = gmpy2.iroot(c,e)

if not exact:
        print("Not found")
print(root)
print(int(root).to_bytes((root.bit_length()+7)//8, 'big').decode())

Paso 3.-
portidell_g3@DESKTOP-28KM9FK:~$ python3 solution.py
2756326214127165272055984685514956805532990337248526951293
portidell_g3@DESKTOP-28KM9FK:~$ nano solution.py
portidell_g3@DESKTOP-28KM9FK:~$ python3 solution.py
2756326214127165272055984685514956805532990337248526951293
picoCTF{t1ny_e_f053d79c}

flag: picoCTF{t1ny_e_f053d79c}
```

## Notas 
```
Los valores de e y c que aparecen el archivo nano los tomé el archivo txt que descargué en el paso 1.
```

## Referencias
````

```
