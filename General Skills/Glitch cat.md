
## Descripción
``Our flag printing service has started glitching!
Additional details will be available after launching your challenge instance.

## Solución
``porti_04@DESKTOP-8HT902T:~$ nc saturn.picoctf.net 53436
'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

- `'picoCTF{gl17ch_m3_n07_'` es una cadena de texto.
- `chr(0x39)` es el carácter correspondiente al código hexadecimal `0x39`, que es `'9'`.
- `chr(0x63)` es `'c'`.
- `chr(0x34)` es `'4'`.
- `chr(0x32)` es `'2'`.
- `chr(0x61)` es `'a'`.
- `chr(0x34)` es `'4'`.
- `chr(0x35)` es `'5'`.
- `chr(0x64)` es `'d'`.
- `'}'`
Cuando juntas todo esto, obtienes la cadena completa:
`picoCTF{gl17ch_m3_n07_9c42a45d}`

## Notas 

## Referencias