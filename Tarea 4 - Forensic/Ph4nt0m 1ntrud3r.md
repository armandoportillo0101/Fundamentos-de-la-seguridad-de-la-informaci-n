## Descripción
```
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/3fe089c41615b9413666bedca922e07bf6ad8894a3dabd2737735143ad2396cf/myNetworkTraffic.pcap) and try to get the flag.
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3fe089c41615b9413666bedca922e07bf6ad8894a3dabd2737735143ad2396cf/myNetworkTraffic.pcap
--2026-03-29 19:18:12--  https://challenge-files.picoctf.net/c_verbal_sleep/3fe089c41615b9413666bedca922e07bf6ad8894a3dabd2737735143ad2396cf/myNetworkTraffic.pcap
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.61, 3.161.44.84, 3.161.44.103, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1452 (1.4K) [application/octet-stream]
Saving to: ‘myNetworkTraffic.pcap’

myNetworkTraffic.pcap         100%[=================================================>]   1.42K  --.-KB/s    in 0s

2026-03-29 19:18:13 (82.9 MB/s) - ‘myNetworkTraffic.pcap’ saved [1452/1452]
portidell_g3@DESKTOP-28KM9FK:~$ tshark -r myNetworkTraffic.pcap
    1   0.000000  192.168.0.2 → 192.168.1.2  TCP 48 20 → 80 [SYN] Seq=0 Win=8192 Len=8 [TCP segment of a reassembled PDU]
    2   0.003558  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] [Illegal Segments]
    3   0.001685  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
    4   0.004344  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=12
    5   0.003324  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=12
    6  -0.000716  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
    7   0.000744  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
    8   0.003893  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=12
    9   0.000478  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   10   0.000973  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   11   0.001205  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   12   0.002624  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   13   0.002153  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   14   0.002383  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   15   0.003102  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=12
   16   0.004117  192.168.0.2 → 192.168.1.2  TCP 52 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=12
   17   0.001922  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   18   0.002861  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   19   0.001444  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   20   0.004564  192.168.0.2 → 192.168.1.2  TCP 44 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=4
   21  -0.000250  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
   22   0.000241  192.168.0.2 → 192.168.1.2  TCP 48 [TCP Retransmission] 20 → 80 [SYN] Seq=0 Win=8192 Len=8
portidell_g3@DESKTOP-28KM9FK:~$ tshark -r myNetworkTraffic.pcap -x
0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 a9 e6 00 00 54 63 6c 67 2f 33 73 3d   P. .....Tclg/3s=

Frame (52 bytes):
0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 eb 52 00 00 62 6e 52 66 64 47 67 30   P. ..R..bnRfdGg0
0030  64 41 3d 3d                                       dA==
Reassembled TCP (12 bytes):
0000  54 63 6c 67 2f 33 73 3d 64 41 3d 3d               Tclg/3s=dA==

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 99 e0 00 00 52 48 78 68 74 53 34 3d   P. .....RHxhtS4=

0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 35 ef 00 00 4e 6a 5a 6b 4d 47 4a 6d   P. .5...NjZkMGJm
0030  59 67 3d 3d                                       Yg==

0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 05 5b 00 00 65 7a 46 30 58 33 63 30   P. ..[..ezF0X3c0
0030  63 77 3d 3d                                       cw==

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 85 17 00 00 52 4d 71 2b 77 54 4d 3d   P. .....RMq+wTM=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 c6 bf 00 00 37 75 44 43 63 6c 67 3d   P. .....7uDCclg=

0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 f6 5a 00 00 58 7a 4d 30 63 33 6c 66   P. ..Z..XzM0c3lf
0030  64 41 3d 3d                                       dA==

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 d9 d7 00 00 4f 77 46 65 50 30 4d 3d   P. .....OwFeP0M=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 96 c6 00 00 34 70 63 59 77 54 67 3d   P. .....4pcYwTg=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 0e f5 00 00 32 64 37 31 4b 5a 49 3d   P. .....2d71KZI=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 a4 fc 00 00 6f 46 70 5a 50 47 38 3d   P. .....oFpZPG8=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 98 9a 00 00 71 6f 39 71 70 69 59 3d   P. .....qo9qpiY=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 b3 18 00 00 4a 62 47 32 51 37 77 3d   P. .....JbG2Q7w=

0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 fd 41 00 00 63 47 6c 6a 62 30 4e 55   P. ..A..cGljb0NU
0030  52 67 3d 3d                                       Rg==

0000  45 00 00 34 00 01 00 00 40 06 f8 6e c0 a8 00 02   E..4....@..n....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 26 0d 00 00 59 6d 68 66 4e 48 4a 66   P. .&...YmhfNHJf
0030  4f 51 3d 3d                                       OQ==

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 86 e4 00 00 5a 31 47 64 79 6a 6b 3d   P. .....Z1Gdyjk=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 a1 f7 00 00 68 4b 76 5a 4b 47 41 3d   P. .....hKvZKGA=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 21 00 00 00 36 77 34 36 51 37 30 3d   P. .!...6w46Q70=

0000  45 00 00 2c 00 01 00 00 40 06 f8 76 c0 a8 00 02   E..,....@..v....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 69 97 00 00 66 51 3d 3d               P. .i...fQ==

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 bf eb 00 00 39 44 70 49 62 6b 41 3d   P. .....9DpIbkA=

0000  45 00 00 30 00 01 00 00 40 06 f8 72 c0 a8 00 02   E..0....@..r....
0010  c0 a8 01 02 00 14 00 50 00 00 00 00 00 00 00 00   .......P........
0020  50 02 20 00 86 27 00 00 51 4b 7a 46 58 2b 63 3d   P. ..'..QKzFX+c=
portidell_g3@DESKTOP-28KM9FK:~$ tshark -r myNetworkTraffic.pcap -Y "tcp.len==12 || tcp.len==4" -T fields  -e frame.time
-e tcp.segment_data | sort -k4 | awk '{print $6}' | xxd -p -r | base64 -d
picoCTF{1t_w4snt_th4t_34sy_tbh_4r_966d0bfb}


flag: picoCTF{1t_w4snt_th4t_34sy_tbh_4r_966d0bfb}

```

## Notas 
```

```

## Referencias
````

```
