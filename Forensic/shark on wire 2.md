## Descripción
```
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.
```
## Solución
porti_04@DESKTOP-8HT902T:~$ ls
bash  picoCTF_retos  pico_retos
porti_04@DESKTOP-8HT902T:~$ cd pico_retos
porti_04@DESKTOP-8HT902T:~/pico_retos$ ñs
ñs: command not found
porti_04@DESKTOP-8HT902T:~/pico_retos$ ls
forensic
porti_04@DESKTOP-8HT902T:~/pico_retos$ cd forensic
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ ls
corrupt     gloryofthegarden  moonwalk      sharkonwire2  whatlieswhitin
extensions  like1000          sharkonwire1  someta        whitepages
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd skarkonwire2
-bash: cd: skarkonwire2: No such file or directory
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic$ cd  sharkonwire2
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire2$ dir
capture.pcap  exp.py
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire2$ nano exp.py
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire2$ python3 exp.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}
porti_04@DESKTOP-8HT902T:~/pico_retos/forensic/sharkonwire2$

archivo de nano para sacar la bandera
  GNU nano 6.2                                        exp.py           from scapy.all import *

packets = rdpcap('capture.pcap')

flag=''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport-5000)
print (flag)

flag: picoCTF{p1LLf3r3d_data_v1a_st3g0}```

```

## Notas 
```

```

## Referencias
````

```
