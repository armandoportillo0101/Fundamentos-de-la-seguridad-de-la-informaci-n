
## Descripción
``There is a nice program that you can talk to by using this command in a shell: `$ nc mercury.picoctf.net 21135`, but it doesn't speak English...
## Solución
`` porti_04@DESKTOP-8HT902T:~$  nc mercury.picoctf.net 21135
112
105
99
111
67
84
70
123
103
48
48
100
95
107
49
116
116
121
33
95
110
49
99
51
95
107
49
116
116
121
33
95
97
102
100
53
102
100
97
52
125
10
porti_04@DESKTOP-8HT902T:~$

bandera obtenida: picoCTF{g00d_k1tty!_n1c3_k1tty!_afd5fda4}
## Notas 
``Lo que yo hice para resolver este problema fue copiar la serie de numeros que me salieron despues de darle enter a nc mercury.picoctf.net 21135 en un covertidor de ASII a texto de forma seguida.
## Referencias
``[https://www.duplichecker.com/ascii-to-text.php](https://www.duplichecker.com/ascii-to-text.php)