## Descripción
```
Python scripts are invoked kind of like programs in the Terminal...Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/flag.txt.en)?
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/ende.py
--2026-03-27 11:25:04--  https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/ende.py
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.22, 3.161.44.103, 3.161.44.84, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.22|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1328 (1.3K) [application/octet-stream]
Saving to: ‘ende.py’

ende.py                       100%[=================================================>]   1.30K  --.-KB/s    in 0s

2026-03-27 11:25:05 (99.9 MB/s) - ‘ende.py’ saved [1328/1328]

portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/password.txt
--2026-03-27 11:25:15--  https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/password.txt
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.84, 3.161.44.103, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 33 [application/octet-stream]
Saving to: ‘password.txt’

password.txt                  100%[=================================================>]      33  --.-KB/s    in 0s

2026-03-27 11:25:16 (9.06 MB/s) - ‘password.txt’ saved [33/33]

portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/flag.txt.en
--2026-03-27 11:25:22--  https://challenge-files.picoctf.net/c_wily_courier/1b9b921ec0fd3ea71d7e326c84ff94912e8e7d2d67c277af04005cace61cf230/flag.txt.en
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.22, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 140 [application/octet-stream]
Saving to: ‘flag.txt.en’

flag.txt.en                   100%[=================================================>]     140  --.-KB/s    in 0s

2026-03-27 11:25:23 (31.7 MB/s) - ‘flag.txt.en’ saved [140/140]

portidell_g3@DESKTOP-28KM9FK:~$ ls
ende.py  fixme3  fixme3.tar.gz  flag.txt.en  password.txt
portidell_g3@DESKTOP-28KM9FK:~$ cat password.txt
720b6ad346f84cd483c60c7464dd95d4
portidell_g3@DESKTOP-28KM9FK:~$ cat flag.txt
cat: flag.txt: No such file or directory
portidell_g3@DESKTOP-28KM9FK:~$ cat flag.txt.en
gAAAAABpRaHLJvQHNKx7S5bkBbCbLRygnKBNN2x32PTowWwOk2iIsCAgGdGgp_g-lIbghg4z6VSdljq5-moyXGu-5aQcrz5iaUEjHJWDAvd2xSZCeNVfUSJoUfj_wuZyjP3gQB5LdglQportidell_g3@DESKTOP-28KM9FK:~$ cat ende.py

import sys
import base64
from cryptography.fernet import Fernet



usage_msg = "Usage: "+ sys.argv[0] +" (-e/-d) [file]"
help_msg = usage_msg + "\n" +\
        "Examples:\n" +\
        "  To decrypt a file named 'pole.txt', do: " +\
        "'$ python "+ sys.argv[0] +" -d pole.txt'\n"



if len(sys.argv) < 2 or len(sys.argv) > 4:
    print(usage_msg)
    sys.exit(1)



if sys.argv[1] == "-e":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "rb") as f:
        data = f.read()
        data_c = c.encrypt(data)
        sys.stdout.write(data_c.decode())


elif sys.argv[1] == "-d":
    if len(sys.argv) < 4:
        sim_sala_bim = input("Please enter the password:")
    else:
        sim_sala_bim = sys.argv[3]

    ssb_b64 = base64.b64encode(sim_sala_bim.encode())
    c = Fernet(ssb_b64)

    with open(sys.argv[2], "r") as f:
        data = f.read()
        data_c = c.decrypt(data.encode())
        sys.stdout.buffer.write(data_c)


elif sys.argv[1] == "-h" or sys.argv[1] == "--help":
    print(help_msg)
    sys.exit(1)


else:
    print("Unrecognized first argument: "+ sys.argv[1])
    print("Please use '-e', '-d', or '-h'.")

portidell_g3@DESKTOP-28KM9FK:~$ python3 ende.py -d flag.txt.en
Please enter the password:720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}

flag: picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}
```

## Notas 
```

```

## Referencias
````

```
