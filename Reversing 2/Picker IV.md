## Descripción
```
Can you figure out how this program works to get the flag?Connect to the program with netcat:`$ nc saturn.picoctf.net 52978`The program's source code can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV.c). The binary can be downloaded [here](https://artifacts.picoctf.net/c/529/picker-IV).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ wget https://artifacts.picoctf.net/c/529/picker-IV.c
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ wget https://artifacts.picoctf.net/c/529/picker-IV
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ file picker-IV
picker-IV: ELF 64-bit LSB executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=12b33c5ff389187551aae5774324da558cee006c, for GNU/Linux 3.2.0, not stripped
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ readelf picker-IV
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ readelf -a picker-IV
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ readelf -a picker-IV | grep win
No processor specific unwind information to decode
    63: 000000000040129e   150 FUNC    GLOBAL DEFAULT   15 win
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ nc saturn.picoctf.net 52978
Enter the address in hex to jump to, excluding '0x': 0x40129e
You input 0x40129e
You won!
picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}


flag: picoCTF{n3v3r_jump_t0_u53r_5uppl13d_4ddr35535_b8de1af4}
```

## Notas 
```

```

## Referencias
````

```
