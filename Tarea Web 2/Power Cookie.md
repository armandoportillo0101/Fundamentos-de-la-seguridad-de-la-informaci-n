## Descripción
```
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/134/capture.flag.pcap)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ wget https://artifacts.picoctf.net/c/134/capture.flag.pcap
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ cat capture.flag.pcap
�ò��B[a�jP'5'�9E�B�\@@d}

DC.Q�iD
'�9�c�Sc5'�9�7
              ␦y!()*w��9��
                          focal-VirtualBox��B[a/�N'�9'5E@���

CD,dX�iD

'�9�c�Sc6
5���

3X��B[a�X*'5''�9�

�B[a�Z<'�9'5�
'�9�
�B[a�J'��'�9E<�M@@8\

�#)X#3����A�
Ѥ�D�B[a�'�9'��E<@@"�

#)�s���X#3Ҡ��1^�
i>%�Ѥ�D�B[a�'��'�9E4�N@@8c

�#)X#3�s����9
Ѥ�Ei>%��B[aH�<'�9''��s

�B[ad�*'��''�9�
'��s
�B[axJ  *'��''�9�

�B[a�L  <'�9''��s
'�9�
�B[a�1k'�9'��E]i�@@�

#)�s���X#3Ҁ��/
i>d@Ѥ�EHey, how do you decrypt this file again?
�B[a=2B'��'�9E4�O@@8b

�#)X#3�s����9
Ѥ��i>d@�B[a�
            R'��'�9ED�P@@8Q

�#)X#3�s����I
ci>d@You're serious?
�B[a
    B'�9'��E4i�@@�(

#)�s��X#3���=
i>��c�B[af�T'�9'��EFi�@@�

#)�s��X#3��␦�
i>��cYeah, I'm serious
�B[a��B'��'�9E4�Q@@8`

�#)X#3�s��"��9
ѥ.i>���B[��'��'�9E��R@@8


�#)X#3�s��"���
ѥ�i>��*sigh* openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
�B[a3�B'�9'��E4i�@@�&

#)�s��"X#45���e
i?h�ѥ��B[a��<'�9''��s

�B[a��*'��''�9�
'��s
�B[a.*'��''�9�

�B[al0<'�9''��s
'�9�
�B[a$�U'�9'��EGi�@@�

#)�s��"X#45��}�
i?��ѥ�Ok, great, thanks.
�B[aD�B'��'�9E4�S@@8^

�#)X#45s��5��9
Ѧ|i?�C[a�dq'��'�9Ec�T@@8.

�#)X#45s��5��h
ѦNJi?��Let's use Discord next time, it's more secure.
C[a�gB'�9'��E4i�@@�$

#)�s��5X#4d���
i?��ѦNJC[a
u'�9'��Egi�@@��

#)�s��5X#4d��r�
i?�xѦNJC'mon, no one knows we use this program like this!
B'��'�9E4�U@@8\

�#)X#4ds��h��9
Ѧ�i?�x[a�E
L'��'�9E>�V@@8Q

�#)X#4ds��h��C
Ѧ��i?�xWhatever.
[aRG
B'�9'��E4i�@@�"

#)�s��hX#4n���
i@�Ѧ��C[af�
G'�9'��E9i�@@�

#)�s��hX#4n����
i@"�Ѧ��Hey.
C[a��
B'��'�9E4�W@@8Z

�#)X#4ns��m��9
Ѧ�Fi@"�$C[ab`H'��'�9E:�X@@8S

�#)X#4ns��m��?
Ѧ�gi@"�Yeah?
$C[a�aB'�9'��E4i�@@�

#)�s��mX#4t��?D
i@3�Ѧ�g1C[aPk'�9'��E]i�@@��

#)�s��mX#4t����
i@g�Ѧ�gCould you transfer the file to me again?
1C[a6PB'��'�9E4�Y@@8X

�#)X#4ts�햀�9
Ѧ�si@g�3C[a�B   JJRT'�9E<��@@��
#�T��P��}����q�
�}�3C[a(�       <'�9�RTE,��ͤ#�T
P�����~`����3C[aZ�      66RT'�9E(��@@��
#�T��P��~�P���]3C[aY�   ��RT'�9E��@@�Q
#�T��P��~�P��ڴGET / HTTP/1.1
Host: connectivity-check.ubuntu.com
Accept: */*
Connection: close

<'�9�RTE(��ͧ#�T
P������P��4C[a���'�9�RTE����#�T
P������P�z�HTTP/1.1 204 No Content
Date: Mon, 04 Oct 2021 18:08:52 GMT
Server: Apache/2.4.18 (Ubuntu)
X-NetworkManager-Status: online
Connection: close

4C[a��66RT'�9E(��@@��
#�T��P���4P�\�]4C[a<'�9�RTE(��ͥ#�T
P��4���P���4C[a�66RT'�9E(��@@��
#�T��P���5P�[�]4C[a�<'�9�RTE(��ͤ#�T
P��5���P���DC[a
['��'�9EM�Z@@8>

�#)X#4ts�햀�R
ѧ:�i@g�Oh great. Ok, over 9002?
DC[aa�
B'�9'��E4i�@@�

#)�s��X#4���@M
<'�9''��s[a$

*'��''�9�
'��s
TC[a��S'�9'��EEi�@@�


#)�s��X#4�����
i@�ѧ:�Yeah, listening.
TC[a4�B'��'�9E4�[@@8V

�#)X#4�s����9
ѧw5i@�[C[aJ'��'�9E<��@@v



2#*^������A�
ѧ��[C[aJ'�9'��E<@@"�

#*�2@_Tl^��Ǡ���~�
iA
  gѧ��[C[aB'��'�9E4��@@v"

�2#*^���@_Tm��9
ѧ��iA
     g[C[r'��'�9Ed��@@u�

�2#*^���@_Tm��i
ѧ��iA
     gSalted__
�%Ē[eC�lRܑ�H{�R�m���P��R/��2���d@[C[a�
                                     B'�9'��E4P@@Ҙ

#*�2@_Tm^������
iA
  hѧ��bC[a6�J'��'�9E<�\@@8M

�#)X#4�s����A
ѧ��i@�Sent it
bC[a�B'�9'��E4i�@@�

#)�s��X#4���X,
iA'9ѧ��gC[a~8B'�9'��E4P␦@@җ

#*�2@_Tm^������<
iA:�ѧ��gC[ag9B'��'�9E4��@@v

�2#*^���@_Tn��9
ѧ�]iA:�gC[a}<B'�9'��E4P@Җ

#*�2@_Tn^�������
iA:�ѧ�]qC[a�xJ'�9'��E<i�@@�

#)�s��X#4����

Aa+ѧ��Got it.
qC[aCzB'��'�9E4�]@@8T

�#)X#4�s����9
ѧ�iAa+rC[a�ddRT'�9EV��@@D�

�w5Bc��connectivity-checkubuntucom)rC[aY␦d'�9�RTEV����

5�wB;��Ё�connectivity-checkubuntucom)��rC[a`ddRT'�9EV��@@D�

�Bc��connectivity-checkubuntucom)rC[a�Xd'�9�RTEV����

5�^I����connectivity-checkubuntucom)��wC[a��**RT''�9�

wC[a��<'�9�RRT5
'�9�
}C[a��  V'��'�9EH�^@@8?

�#)X#4�s����M
Ѩ4iAa+You're unbelievable
}C[a��  B'�9'��E4i�@@�␦

#)�s��X#4����2
iA��Ѩ4�C[a
<'�9''��s

�C[a8|
*'��''�9�
'��s
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ strings capture.flag.pcap
!()*w
focal-VirtualBox
B[a/
#)X#3
#)X#3
Ei>%
B[aH
B[ad
B[axJ
i>d@
EHey, how do you decrypt this file again?
B[a=2
#)X#3
i>d@
#)X#3
ci>d@You're serious?
B[af
cYeah, I'm serious
#)X#3
#)X#3
*sigh* openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
B[a3
"X#45
B[al0
B[a$
"X#45
Ok, great, thanks.
B[aD
#)X#45s
#)X#45s
NJi?
Let's use Discord next time, it's more secure.
5X#4d
5X#4d
NJC'mon, no one knows we use this program like this!
C[aY
#)X#4ds
#)X#4ds
xWhatever.
C[aRG
hX#4n
C[af
hX#4n
Hey.
#)X#4ns
Fi@"
$C[ab`
#)X#4ns
gi@"
Yeah?
$C[a
mX#4t
g1C[a
mX#4t
gCould you transfer the file to me again?
1C[a6P
#)X#4ts
si@g
3C[a
3C[a(
3C[aZ
3C[aY
GET / HTTP/1.1
Host: connectivity-check.ubuntu.com
Accept: */*
Connection: close
3C[a
4C[a
HTTP/1.1 204 No Content
Date: Mon, 04 Oct 2021 18:08:52 GMT
Server: Apache/2.4.18 (Ubuntu)
X-NetworkManager-Status: online
Connection: close
4C[a
4C[a
4C[a
4C[a
DC[a
#)X#4ts
Oh great. Ok, over 9002?
DC[aa
IC[a$
IC[aC
TC[a
Yeah, listening.
TC[a4
#)X#4
w5i@
[C[a)
2#*^
[C[a
2@_Tl^
[C[a
2#*^
@_Tm
g[C[a
2#*^
@_Tm
gSalted__
d@[C[a
2@_Tm^
bC[a6
#)X#4
Sent it
bC[a
iA'9
gC[a~8
2@_Tm^
gC[ag9
2#*^
@_Tn
]iA:
gC[a}<
2@_Tn^
]qC[a
iAa+
Got it.
qC[aCz
#)X#4
iAa+rC[a
connectivity-check
ubuntu
rC[aY
connectivity-check
ubuntu
rC[a`
connectivity-check
ubuntu
rC[a
connectivity-check
ubuntu
wC[a
wC[a
}C[a
#)X#4
4iAa+You're unbelievable
}C[a
C[a8|
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ wireshark capture.flag.pcap
 ** (wireshark:2756) 15:27:03.436020 [GUI WARNING] -- QStandardPaths: wrong permissions on runtime directory /run/user/1000/, 0755 instead of 0700
nl80211 not found.
^C
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ openssl des3 -d -salt -in file.des3 -out file.txt -k
des3: Option -k needs a value
des3: Use -help for summary.
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ ls
capture.flag.pcap  file.des3
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ wireshark capture.flag.pcap
 ** (wireshark:5857) 15:40:03.706955 [GUI WARNING] -- QStandardPaths: wrong permissions on runtime directory /run/user/1000/, 0755 instead of 0700
nl80211 not found.
^C
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ ls
capture.flag.pcap  file.des3  file.txt
porti_04@DESKTOP-8HT902T:~/pico_retos/examen_parcial_2/eavesdrop$ cat file.txt
picoCTF{nc_73115_411_dd54ab67}

flag: picoCTF{nc_73115_411_dd54ab67}
```

## Notas 
```
Se hizo uso de wireshark
```

## Referencias
````

```
