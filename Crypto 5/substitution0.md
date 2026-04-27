## Descripción
```
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/153/message.txt).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/tercer_parcial$ wget https://artifacts.picoctf.net/c/153/message.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/tercer_parcial$ cat message.txt
OHNFUMWSVZLXEGCPTAJDYIRKQB

Suauypcg Xuwaogf oacju, rvds o waoiu ogf jdoduxq ova, ogf hacywsd eu dsu huudxu
mace o wxojj noju vg rsvns vd roj ugnxcjuf. Vd roj o huoydvmyx jnoaohouyj, ogf, od
dsod dveu, yglgcrg dc godyaoxvjdj—cm ncyaju o wauod pavbu vg o jnvugdvmvn pcvgd
cm ivur. Dsuau ruau drc acygf hxonl jpcdj guoa cgu ukdauevdq cm dsu honl, ogf o
xcgw cgu guoa dsu cdsua. Dsu jnoxuj ruau uknuufvgwxq soaf ogf wxcjjq, rvds oxx dsu
oppuoaognu cm hyagvjsuf wcxf. Dsu ruvwsd cm dsu vgjund roj iuaq aueoalohxu, ogf,
dolvgw oxx dsvgwj vgdc ncgjvfuaodvcg, V ncyxf soafxq hxoeu Zypvdua mca svj cpvgvcg
aujpundvgw vd.

Dsu mxow vj: pvncNDM{5YH5717Y710G_3I0XY710G_03055505}

flag: picoCTF{5UB5717U710N_3V0LU710N_03055505}
```

## Notas 
```
En la parte superior del texto del mensaje, tenemos una clave para descifrar. El uso de la herramienta en línea llamada [Boxentriq](https://www.boxentriq.com/code-breaking/keyed-caesar-cipher) te ayudará a descifrar este texto cifrado.
```

## Referencias
````

```
