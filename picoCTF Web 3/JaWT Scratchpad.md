## Descripción
```
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210
```
## Solución
```

|||┌──(kali㉿kali)-[~]|
|||└─$ nano hash|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ cat hash|
|||eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYmlhbmsifQ.SDMWjiepwKeoS0nuoJ_7t4rk3kw3siiZKjKaRPjrQKI|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ ls /usr/share/wordlists|
|||amass dirbuster fasttrack.txt john.lst metasploit rockyou.txt.gz wfuzz|
|||dirb dnsmap.txt fern-wifi legion nmap.lst sqlmap.txt wifite.txt|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||gzip: /usr/share/wordlists/rockyou.txt: Permission denied|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||[sudo] password for kali:|
|||Sorry, try again.|
|||[sudo] password for kali:|
|||Sorry, try again.|
|||[sudo] password for kali:|
|||sudo: 3 incorrect password attempts|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||[sudo] password for kali:|
|||Sorry, try again.|
|||[sudo] password for kali:|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||gzip: /usr/share/wordlists/rockyou.txt.gz: No such file or directory|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ ls /usr/share/wordlists|
|||amass dirbuster fasttrack.txt john.lst metasploit rockyou.txt wfuzz|
|||dirb dnsmap.txt fern-wifi legion nmap.lst sqlmap.txt wifite.txt|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||gzip: /usr/share/wordlists/rockyou.txt.gz: No such file or directory|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz|
|||gzip: /usr/share/wordlists/rockyou.txt.gz: No such file or directory|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ ls /usr/share/wordlists|
|||amass dirbuster fasttrack.txt john.lst metasploit rockyou.txt wfuzz|
|||dirb dnsmap.txt fern-wifi legion nmap.lst sqlmap.txt wifite.txt|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ heah /usr/share/wordlists/rockyou.txt|
|||Command 'heah' not found, did you mean:|
|||command 'head' from deb coreutils|
|||command 'heat' from deb python3-heatclient|
|||Try: sudo apt install <deb name>|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ head /usr/share/wordlists/rockyou.txt|
|||123456|
|||12345|
|||123456789|
|||password|
|||iloveyou|
|||princess|
|||1234567|
|||rockyou|
|||12345678|
|||abc123|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ jhon|
|||Command 'jhon' not found, did you mean:|
|||command 'jshon' from deb jshon|
|||command 'john' from deb john|
|||Try: sudo apt install <deb name>|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ sudo apt install john|
|||john is already the newest version (1.9.0-Jumbo-1+git20211102-0kali7+b1).|
|||john set to manually installed.|
|||Summary:|
|||Upgrading: 0, Installing: 0, Removing: 0, Not Upgrading: 0|
||||
|||┌──(kali㉿kali)-[~]|
|||└─$ john hash -w=/usr/share/wordlists/rockyou.txt|
|||Using default input encoding: UTF-8|
|||Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])|
|||Will run 2 OpenMP threads|
|||Press 'q' or Ctrl-C to abort, almost any other key for status|
|||ilovepico (?)|
|||1g 0:00:00:03 DONE (2024-09-23 13:31) 0.2624g/s 1941Kp/s 1941Kc/s 1941KC/s iloverob4live345..ilovepatri|
|||Use the "--show" option to display all of the cracked passwords reliably|
|||Session completed.|
||||

flag: picoCTF{jawt_was_just_what_you_thought_44c752f5}

```

## Notas 
```
La opción `-w-` en John the Ripper se utiliza para indicar que las palabras de la lista de palabras deben ser leídas desde la entrada estándar (stdin) en lugar de desde un archivo.
```

## Referencias
````

```
