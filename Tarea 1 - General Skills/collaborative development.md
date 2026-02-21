## Descripción
```
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/70/challenge.zip)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c_titan/70/challenge.zip
porti_04@DESKTOP-8HT902T:~$ ls
challenge.zip  wget-log
porti_04@DESKTOP-8HT902T:~$ unzip challenge.zip
porti_04@DESKTOP-8HT902T:~$ cd drop-in
porti_04@DESKTOP-8HT902T:~/drop-in$ ls
flag.py
porti_04@DESKTOP-8HT902T:~/drop-in$ flag.py
flag.py: command not found
porti_04@DESKTOP-8HT902T:~/drop-in$ git log flag.py
commit 54c7842e34d03976ddc080a9dd76742751024358 (HEAD -> main)
Author: picoCTF <ops@picoctf.com>
Date:   Thu Feb 19 21:09:44 2024 +0000

    init flag printer
porti_04@DESKTOP-8HT902T:~/drop-in$ git brancg
git: 'brancg' is not a git command. See 'git --help'.

The most similar command is
        branch
porti_04@DESKTOP-8HT902T:~/drop-in$ git branch
  feature/part-1
  feature/part-2
  feature/part-3
* main
porti_04@DESKTOP-8HT902T:~/drop-in$ git checkout feature/part-1
Switched to branch 'feature/part-1'
porti_04@DESKTOP-8HT902T:~/drop-in$ cat flag.py
print("Printing the flag...")
print("picoCTF{t3@mw0rk_", end='')porti_04@DESKTOP-8HT902T:~/drop-in$ git checkout feature/part-2
Switched to branch 'feature/part-2'
porti_04@DESKTOP-8HT902T:~/drop-in$ cat flag.py
print("Printing the flag...")

print("m@k3s_th3_dr3@m_", end='')porti_04@DESKTOP-8HT902T:~/drop-in$ git checkout feature/part-3
Switched to branch 'feature/part-3'
porti_04@DESKTOP-8HT902T:~/drop-in$ cat flag.py
print("Printing the flag...")

print("w0rk_7ffa0077}")
```

## Notas 
```
`git branch` es un comando que lista, crea o elimina ramas en Git. Usado sin opciones, muestra todas las ramas locales. Para crear una nueva rama, puedes usar `git branch nombre_rama`, y para eliminar una rama, `git branch -d nombre_rama`.
```

## Referencias
````

```