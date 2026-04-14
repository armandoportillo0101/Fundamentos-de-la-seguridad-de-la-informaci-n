## Descripción
```
Can you get the real meaning from this file.Download the file [here](https://artifacts.picoctf.net/c_titan/108/enc_flag).
```
## Solución
```
## Paso 1: Identificación del formato (Base64)

Al abrir el archivo, nos encontramos con una cadena de texto larga que termina en `==`.

> **Tip de experto:** Cuando veas un texto con letras, números y que termina en uno o dos signos de igual (`=`), casi siempre es **Base64**. El `=` es puro relleno (_padding_) para que el mensaje tenga el tamaño correcto.

**Texto original:** `YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyZzBOMm8yYXpZNWZRPT0nCg==`

## Paso 2: Primera decodificación

Para leer esto, usamos una herramienta de decodificación. S

**Resultado:** `b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ=='`

## Paso 3: Limpieza de "ruido"

El resultado anterior empieza con una `b'` y termina con `'`. Esto es formato de programación (indica que son "bytes" en Python). Para seguir trabajando, debemos **ignorar la b y las comillas**, quedándonos solo con el interior: `d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ==`

## Paso 4: Segunda decodificación (Doble Base64)

Notas que el nuevo texto ¡también termina en `==`! Esto significa que el archivo estaba codificado dos veces. Repetimos el proceso de decodificación con la nueva cadena.

**Resultado:** `wpjvJAM{jhlzhy_k3jy9wa3k_h47j6k69}`

## Paso 5: El descifrado final (Cifrado César)

Ahora tenemos algo que _parece_ una frase, pero las letras no forman palabras reales. Sin embargo, mantiene una estructura de "Flag": `XXXXXXX{texto_con_guiones}`.

Esto es un **Cifrado César** (o cifrado por sustitución), donde cada letra ha sido reemplazada por otra que está a X posiciones de distancia en el abecedario.

### ¿Cómo resolverlo?

1. Ve a una herramienta como [dCode.fr](https://www.dcode.fr/caesar-cipher).
    
2. Pega la cadena `wpjvJAM{...}`.
    
3. Selecciona "Test all possible shifts" (probar todos los desplazamientos).
    
4. La herramienta buscará en qué posición las letras forman palabras coherentes (como "caesar", "decrypted", etc.).

flag: picoCTF{caesar_d3cr9pt3d_a47c6d69}
```

## Notas 
```

```

## Referencias
````
https://gchq.github.io/CyberChef/#recipe=ROT13_Brute_Force(true,true,false,100,0,true,'')&input=d3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2g0N2o2azY5fQ
```
