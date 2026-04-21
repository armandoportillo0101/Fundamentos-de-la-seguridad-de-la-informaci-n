## Descripción
```
Why use p and q when I can use more?Connect with nc fickle-tempest.picoctf.net 49645.
```
## Solución
```
Paso 1.- 
portidell_g3@DESKTOP-28KM9FK:~$ nc fickle-tempest.picoctf.net 49645
c: 3258858233940769241648168840463245515132576306566763036699253078973057260208334334740832371709473298422391141061483726484202767356824737810455611843793316853930951329152329311925918750855910722564367549960991408046308289009881607514765397430363874474177653473933131915446502297764446185945947941476828760392582380437149258549626395733573632792
n: 6550931916731614058733795150439985190773686862005459341397455747619946990501635090919341265341350786293946148209574769738774466546063442162171713091188338847269207798974197390234438034985507897023774916868027003908456026378680787265623545084220964112723752168608915725654295100517155759831763050921056210033823175132058919311079333330343582683
e: 65537

Paso 2.- En un rsa cipher calculator colocar
Value of the cipher message (Integer) C= x  
Public Key E (Usually E=65537) E= x  
Public Key value (Integer) N= x

	Y nos dará esto: �|À_½±·�¤l²;��Ñ�Ñ�f�E  
	e  
	ê3��ßð0£é�(a_Ð×ZFR"!  ��<HW¤dµµY�E�<ó°C(pÚñ3èÍZ�r����$�î!s3)ê��¼�e¹tk�\á9((æ���ÿ�Ý�9��ÛôÂ�    9��Ú���xÆdÑ��hèc5�T~Å6Jg8vï¨
	Lo cuál aún no es la bandera

Paso 3.- Ir a una interger factorization calcularo y pegar el valor de n, después factorizarlo y de los valores obtenidos solo tomar el valor de Euler's totient

Paso 4.- Pegar el valor de Euler's totient en la calculadora rsa cipher, en el campo "Intermediate value Phi (Integer) φ=", no olvides poner los valores de c, n y e que se no dieron y por último calcularlo

flag: picoCTF{too_many_fact0rs_3023548}
```

## Notas 
```

```

## Referencias
````
https://www.dcode.fr/rsa-cipher
https://www.alpertron.com.ar/ECM.HTM
```
