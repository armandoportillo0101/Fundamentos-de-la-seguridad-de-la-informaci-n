## Descripción
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/someta$ cd ..
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ mkdir sharkonwire1
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd sharkonwire1
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire1$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire1$ wireshark capture.pcap
 ** (wireshark:6694) 10:56:28.925230 [GUI WARNING] -- QStandardPaths: wrong permissions on runtime directory /run/user/1000/, 0755 instead of 0700
nl80211 not found.

flag: picoCTF{StaT31355_636f6e6e}
```

## Notas 
```
Al entrar al wireshark despues de ejecutar en la consola nos arrojará una serie de direcciones, se la click derecho a la que sea de tu eleccion, despues das en follow, despues das click a UDP stream y vas a buscarla hasta el stream 6, ahí se encontrará la bandera.
```

## Referencias
````

```
