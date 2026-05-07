## Descripción
```
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ ls
SafeOpener.class  timer.apk  vd3  vd4  vd5
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ unzip timer.apk
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ grep -R picoCTF
grep: SafeOpener.class: binary file matches
grep: classes3.dex: binary file matches
grep: vd3/VaultDoor3.class: binary file matches
vd3/VaultDoor3.java:        System.out.println("Password: picoCTF{" + password + "}");
vd4/VaultDoor4.java:    String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
vd5/VaultDoor5.java:    String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ ls
AndroidManifest.xml  SafeOpener.class  classes2.dex  kotlin  resources.arsc  vd3  vd5
META-INF             classes.dex       classes3.dex  res     timer.apk       vd4
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ ls
AndroidManifest.xml  SafeOpener.class  classes2.dex  kotlin  resources.arsc  vd3  vd5
META-INF             classes.dex       classes3.dex  res     timer.apk       vd4
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ find . -name classes3.dex
./classes3.dex
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$ strings classes3.dex | grep pico
*picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing$

flag: picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
```

## Notas 
```
Descargué el archivo timer.apk usando wget con el link que nos dan el reto.
```

## Referencias
````

```
