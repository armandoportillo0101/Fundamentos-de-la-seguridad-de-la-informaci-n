## Descripción
```
What was I last working on? I remember writing a note to help me remember...You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/66/challenge.zip)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~$ wget https://artifacts.picoctf.net/c_titan/66/challenge.zip
--2026-02-16 16:20:59--  https://artifacts.picoctf.net/c_titan/66/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.3, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17740 (17K) [application/octet-stream]
Saving to: ‘challenge.zip’

challenge.zip               100%[=========================================>]  17.32K  --.-KB/s    in 0.07s

2026-02-16 16:21:00 (254 KB/s) - ‘challenge.zip’ saved [17740/17740]

porti_04@DESKTOP-8HT902T:~$ unzip challenge.zip
Archive:  challenge.zip
   creating: drop-in/
  inflating: drop-in/message.txt
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample
  inflating: drop-in/.git/hooks/commit-msg.sample
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample
  inflating: drop-in/.git/hooks/post-update.sample
  inflating: drop-in/.git/hooks/pre-applypatch.sample
  inflating: drop-in/.git/hooks/pre-commit.sample
  inflating: drop-in/.git/hooks/pre-merge-commit.sample
  inflating: drop-in/.git/hooks/pre-push.sample
  inflating: drop-in/.git/hooks/pre-rebase.sample
  inflating: drop-in/.git/hooks/pre-receive.sample
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample
  inflating: drop-in/.git/hooks/update.sample
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
 extracting: drop-in/.git/refs/heads/master
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD
  inflating: drop-in/.git/config
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/246218ab4fc7b30e9a9dff073e012316851469
   creating: drop-in/.git/objects/25/
 extracting: drop-in/.git/objects/25/16effb8d70e33bdd0023629b164a77225e1ec2
   creating: drop-in/.git/objects/33/
 extracting: drop-in/.git/objects/33/39c144a0c78dc2fbd3403d2fb37d3830be5d94
  inflating: drop-in/.git/index
 extracting: drop-in/.git/COMMIT_EDITMSG
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master
porti_04@DESKTOP-8HT902T:~$ cd drop-in
porti_04@DESKTOP-8HT902T:~/drop-in$ ls
message.txt
porti_04@DESKTOP-8HT902T:~/drop-in$ git init
Reinitialized existing Git repository in /home/porti_04/drop-in/.git/
porti_04@DESKTOP-8HT902T:~/drop-in$ ls
message.txt
porti_04@DESKTOP-8HT902T:~/drop-in$ git log
commit 3339c144a0c78dc2fbd3403d2fb37d3830be5d94 (HEAD -> master)
Author: picoCTF <ops@picoctf.com>
Date:   Tue Feb 9 21:10:22 2026 +0000

    picoCTF{t1m3m@ch1n3_d3161c0f}
porti_04@DESKTOP-8HT902T:~/drop-in$
```

## Notas 
```

```

## Referencias
````

```