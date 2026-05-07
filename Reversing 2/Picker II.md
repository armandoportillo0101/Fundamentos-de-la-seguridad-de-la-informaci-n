## Descripción
```
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 59543`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/521/picker-II.py).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ wget https://artifacts.picoctf.net/c/521/picker-II.py
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nano
AndroidManifest.xml  classes.dex          kotlin/              res/                 vd3/
META-INF/            classes2.dex         picker-I.py          resources.arsc       vd4/
SafeOpener.class     classes3.dex         picker-II.py         timer.apk            vd5/
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nano picker-II.py
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nc saturn.picoctf.net 59543
==> print( open('flag.txt', 'r').read() )
picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
'NoneType' object is not callable

flag: picoCTF{f1l73r5_f41l_c0d3_r3f4c70r_m1gh7_5ucc33d_b924e8e5}
```

## Notas 
```

```

## Referencias
````

```
