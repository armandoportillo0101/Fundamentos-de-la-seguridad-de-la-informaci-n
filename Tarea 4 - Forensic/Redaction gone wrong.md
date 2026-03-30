## Descripción
```
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/redaction$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/redaction$ pdftotext Financial_Report_for_ABC_Labs.pdf
cat Financial_Report_for_ABC_Labs.txt | grep -oE "picoCTF{.*}"
rm Financial_Report_for_ABC_Labs.txt
picoCTF{C4n_Y0u_S33_m3_fully}

flag: picoCTF{C4n_Y0u_S33_m3_fully}
```

## Notas 
```
1. **`pdftotext Financial_Report_for_ABC_Labs.pdf`**: Convierte el archivo PDF `Financial_Report_for_ABC_Labs.pdf` a un archivo de texto con el mismo nombre pero con extensión `.txt`. Esto genera `Financial_Report_for_ABC_Labs.txt`.
    
2. **`cat Financial_Report_for_ABC_Labs.txt | grep -oE "picoCTF{.*}"`**: Usa `cat` para mostrar el contenido del archivo de texto y lo pasa al comando `grep`. `grep` busca un texto que coincida con el patrón `picoCTF{.*}`, que representa el formato de una flag (`picoCTF{...}`). La opción `-oE` asegura que solo se muestra la coincidencia exacta encontrada, en lugar de toda la línea.
    
3. **`rm Financial_Report_for_ABC_Labs.txt`**: Elimina el archivo de texto temporal `Financial_Report_for_ABC_Labs.txt` después de extraer la información deseada.
    

Finalmente, se muestra la flag encontrada: `picoCTF{C4n_Y0u_S33_m3_fully}`.
```

## Referencias
````

```
