## Descripción
```
How well can you perfom basic binary operations?Start searching for the flag here `nc titan.picoctf.net 53433`[](https://github.com/armandoportillo0101/Seguridad-de-Redes/blob/main/Plantilla.md#objetivo)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ nc titan.picoctf.net 53433

Welcome to the Binary Challenge!"
Your task is to perform the unique operations in the given order and find the final result in hexadecimal that yields the flag.

Binary Number 1: 01001101
Binary Number 2: 01000000


Question 1/6:
Operation 1: '*'
Perform the operation on Binary Number 1&2.
Enter the binary result: 1001101000000
Correct!

Question 2/6:
Operation 2: '>>'
Perform a right shift of Binary Number 2 by 1 bits .
Enter the binary result: 00100000
Correct!

Question 3/6:
Operation 3: '&'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01000000
Correct!

Question 4/6:
Operation 4: '|'
Perform the operation on Binary Number 1&2.
Enter the binary result: 01001101
Correct!

Question 5/6:
Operation 5: '<<'
Perform a left shift of Binary Number 1 by 1 bits.
Enter the binary result: 10011010
Correct!

Question 6/6:
Operation 6: '+'
Perform the operation on Binary Number 1&2.
Enter the binary result: 10001101
Correct!

Enter the results of the last operation in hexadecimal: 8D

Correct answer!
The flag is: picoCTF{b1tw^3se_0p3eR@tI0n_su33essFuL_6ab1ad84}
```

## Notas 
### 1. **Desplazamiento a la derecha (`>>`)**
**Operación**: Mueve todos los bits de un número hacia la derecha, llenando con ceros los espacios vacíos a la izquierda.

**Ejemplo**:

- Binary Number: `00101100`
- Desplazamiento a la derecha por 1 bit: `00010110`

### 2. **Operación AND (`&`)**
**Operación**: Compara los bits de dos números binarios en la misma posición. El resultado es 1 solo si ambos bits son 1; de lo contrario, es 0.

**Ejemplo**:

- Binary Number 1: `01001101`
- Binary Number 2: `01000000`
- Resultado de `01001101 & 01000000`: `01000000`

### 3. **Operación OR (`|`)**
**Operación**: Compara los bits de dos números binarios en la misma posición. El resultado es 1 si al menos uno de los bits es 1; de lo contrario, es 0.

**Ejemplo**:

- Binary Number 1: `01001101`
- Binary Number 2: `01000000`
- Resultado de `01001101 | 01000000`: `01001101`

### 4. **Desplazamiento a la izquierda (`<<`)**
**Operación**: Mueve todos los bits de un número hacia la izquierda, llenando con ceros los espacios vacíos a la derecha.

**Ejemplo**:

- Binary Number: `01001101`
- Desplazamiento a la izquierda por 1 bit: `10011010`

### 5. **Suma (`+`)**
**Operación**: Suma los dos números binarios bit por bit, teniendo en cuenta el acarreo.

**Ejemplo**:

- Binary Number 1: `01001101`
- Binary Number 2: `01000000`
- Resultado de `01001101 + 01000000`: `10001101` (en binario)

### 6. **Conversión a hexadecimal**
**Operación**: Convierte el resultado binario o decimal a hexadecimal.

**Ejemplo**:

- Decimal `141` convertido a hexadecimal: `8D`

## Referencias
````

```