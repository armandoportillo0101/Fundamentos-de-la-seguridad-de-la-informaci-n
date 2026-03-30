## Descripción
```
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/215/pico.flag.png)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/stego$ wget https://artifacts.picoctf.net/c/215/pico.flag.png
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/stego$ zsteg 2b pico.flag.png
[.] 2b
[!] #<Errno::ENOENT: No such file or directory @ rb_sysopen - 2b>

[.] pico.flag.png
b1,r,lsb,xy         .. text: "~__B>wV_G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_96ae0ac1}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b2,a,lsb,xy         .. file: Matlab v4 mat-file (little endian) >\004<\305P, numeric, rows 0, columns 0
b2,a,msb,xy         .. file: Matlab v4 mat-file (little endian) | <\243, numeric, rows 0, columns 0
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,lsb,xy      .. file: Novell LANalyzer capture file
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
b4,abgr,lsb,xy      .. file: Novell LANalyzer capture file
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/stego$

flag: picoCTF{7h3r3_15_n0_5p00n_96ae0ac1}
```

## Notas 
```
- **`zsteg`**: Es la herramienta que analiza archivos para descubrir datos ocultos.
- **`2b`**: Esta opción indica un tipo de análisis específico en `zsteg`, buscando información oculta en cada segundo bit de los datos de la imagen. En esteganografía, los bits de las imágenes se pueden usar para esconder información sin alterar visualmente el archivo.
- **`pico.flag.png`**: El archivo de imagen que contiene la posible información oculta, como una flag o mensaje.
```

## Referencias
````

```
