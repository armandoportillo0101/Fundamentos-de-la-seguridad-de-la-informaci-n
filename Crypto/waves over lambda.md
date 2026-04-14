## Descripción
```
We made a lot of substitutions to encrypt this. Can you decrypt it? Connect with `nc jupiter.challenges.picoctf.org 13758`.
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ nc jupiter.challenges.picoctf.org 13758
porti_04@DESKTOP-8HT902T:~/pico_retos/crypto$ nc jupiter.challenges.picoctf.org 13758
-------------------------------------------------------------------------------
pwajksbz dgkg fz ewok mysj - mkgcogape_fz_p_wlgk_ysrhns_nalbmkbseo
-------------------------------------------------------------------------------
dslfaj dsn zwrg bfrg sb re nfziwzsy xdga fa ywanwa, f dsn lfzfbgn bdg hkfbfzd rozgor, san rsng zgskpd srwaj bdg hwwqz san rsiz fa bdg yfhkske kgjsknfaj bksazeylsafs; fb dsn zbkopq rg bdsb zwrg mwkgqawxygnjg wm bdg pwoabke pwoyn dsknye msfy bw dslg zwrg friwkbsapg fa ngsyfaj xfbd s awhygrsa wm bdsb pwoabke. f mfan bdsb bdg nfzbkfpb dg asrgn fz fa bdg gvbkgrg gszb wm bdg pwoabke, uozb wa bdg hwkngkz wm bdkgg zbsbgz, bksazeylsafs, rwynslfs san hoqwlfas, fa bdg rfnzb wm bdg pskisbdfsa rwoabsfaz; wag wm bdg xfyngzb san ygszb qawxa iwkbfwaz wm gokwig. f xsz awb shyg bw yfjdb wa sae rsi wk xwkq jflfaj bdg gvspb ywpsyfbe wm bdg pszbyg nkspoys, sz bdgkg skg aw rsiz wm bdfz pwoabke sz egb bw pwriskg xfbd wok wxa wknasapg zoklge rsiz; hob f mwoan bdsb hfzbkfbt, bdg iwzb bwxa asrgn he pwoab nkspoys, fz s msfkye xgyy-qawxa iyspg. f zdsyy gabgk dgkg zwrg wm re awbgz, sz bdge rse kgmkgzd re rgrwke xdga f bsyq wlgk re bkslgyz xfbd rfas.
```

## Notas 
```
Para desencriptar el mensaje usamos substitutions solver y cyberchef.

Resultado de substitution solver:
|   |   |
|---|---|
|Key|abcdefghijklmnopqrstuvwxyz     This clear text ...  <br>**ntqhyiebpgrvfduckmazjxowls**     ... maps to this cipher text|
-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_dnvtfrtayu
-------------------------------------------------------------------------------
having had some time at my disposal when in london, i had visited the british museum, and made search among the books and maps in the library regarding transylvania; it had struck me that some foreknowledge of the country could hardly fail to have some importance in dealing with a nobleman of that country. i find that the district he named is in the extreme east of the country, just on the borders of three states, transylvania, moldavia and bukovina, in the midst of the carpathian mountains; one of the wildest and least known portions of europe. i was not able to light on any map or work giving the exact locality of the castle dracula, as there are no maps of this country as yet to compare with our own ordnance survey maps; but i found that bistritz, the post town named by count dracula, is a fairly well-known place. i shall enter here some of my notes, as they may refresh my memory when i talk over my travels with mina.

En cyberchef usamos: substitute y nos dio
Warning: Plaintext and Ciphertext lengths differ

-------------------------------------------------------------------------------
congrats here is your flag - frequency_is_c_over_lambda_dnvtfrtayu
-------------------------------------------------------------------------------
having had some time at my disposal when in london, i had visited the british museum, and made search among the books and maps in the library regarding transylvania; it had struck me that some foreknowledge of the country could hardly fail to have some importance in dealing with a nobleman of that country. i find that the district he named is in the extreme east of the country, just on the borders of three states, transylvania, moldavia and bukovina, in the midst of the carpathian mountains; one of the wildest and least known portions of europe. i was not able to light on any map or work giving the exact locality of the castle dracula, as there are no maps of this country as yet to compare with our own ordnance survey maps; but i found that bistritz, the post town named by count dracula, is a fairly well-known place. i shall enter here some of my notes, as they may refresh my memory when i talk over my travels with mina.

y esta la bandera sera en este formato: frequency_is_c_over_lambda_dnvtfrtayu


```

## Referencias
````
[https://www.guballa.de/substitution-solver](https://www.guballa.de/substitution-solver) [https://gchq.github.io/CyberChef/#recipe=Substitute('ABCDEFGHIJKLMNOPQRSTUVWXYZ','ntqhyiebpgrvfduckmazjxowls%20%20%20',false)&input=LS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLQ0KY29uZ3JhdHMgaGVyZSBpcyB5b3VyIGZsYWcgLSBmcmVxdWVuY3lfaXNfY19vdmVyX2xhbWJkYV9kbnZ0ZnJ0YXl1DQotLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tDQpoYXZpbmcgaGFkIHNvbWUgdGltZSBhdCBteSBkaXNwb3NhbCB3aGVuIGluIGxvbmRvbiwgaSBoYWQgdmlzaXRlZCB0aGUgYnJpdGlzaCBtdXNldW0sIGFuZCBtYWRlIHNlYXJjaCBhbW9uZyB0aGUgYm9va3MgYW5kIG1hcHMgaW4gdGhlIGxpYnJhcnkgcmVnYXJkaW5nIHRyYW5zeWx2YW5pYTsgaXQgaGFkIHN0cnVjayBtZSB0aGF0IHNvbWUgZm9yZWtub3dsZWRnZSBvZiB0aGUgY291bnRyeSBjb3VsZCBoYXJkbHkgZmFpbCB0byBoYXZlIHNvbWUgaW1wb3J0YW5jZSBpbiBkZWFsaW5nIHdpdGggYSBub2JsZW1hbiBvZiB0aGF0IGNvdW50cnkuIGkgZmluZCB0aGF0IHRoZSBkaXN0cmljdCBoZSBuYW1lZCBpcyBpbiB0aGUgZXh0cmVtZSBlYXN0IG9mIHRoZSBjb3VudHJ5LCBqdXN0IG9uIHRoZSBib3JkZXJzIG9mIHRocmVlIHN0YXRlcywgdHJhbnN5bHZhbmlhLCBtb2xkYXZpYSBhbmQgYnVrb3ZpbmEsIGluIHRoZSBtaWRzdCBvZiB0aGUgY2FycGF0aGlhbiBtb3VudGFpbnM7IG9uZSBvZiB0aGUgd2lsZGVzdCBhbmQgbGVhc3Qga25vd24gcG9ydGlvbnMgb2YgZXVyb3BlLiBpIHdhcyBub3QgYWJsZSB0byBsaWdodCBvbiBhbnkgbWFwIG9yIHdvcmsgZ2l2aW5nIHRoZSBleGFjdCBsb2NhbGl0eSBvZiB0aGUgY2FzdGxlIGRyYWN1bGEsIGFzIHRoZXJlIGFyZSBubyBtYXBzIG9mIHRoaXMgY291bnRyeSBhcyB5ZXQgdG8gY29tcGFyZSB3aXRoIG91ciBvd24gb3JkbmFuY2Ugc3VydmV5IG1hcHM7IGJ1dCBpIGZvdW5kIHRoYXQgYmlzdHJpdHosIHRoZSBwb3N0IHRvd24gbmFtZWQgYnkgY291bnQgZHJhY3VsYSwgaXMgYSBmYWlybHkgd2VsbC1rbm93biBwbGFjZS4gaSBzaGFsbCBlbnRlciBoZXJlIHNvbWUgb2YgbXkgbm90ZXMsIGFzIHRoZXkgbWF5IHJlZnJlc2ggbXkgbWVtb3J5IHdoZW4gaSB0YWxrIG92ZXIgbXkgdHJhdmVscyB3aXRoIG1pbmEuDQoNCg&oenc=65001&ieol=CRLF&oeol=CRLF](https://gchq.github.io/CyberChef/#recipe=Substitute\('ABCDEFGHIJKLMNOPQRSTUVWXYZ','ntqhyiebpgrvfduckmazjxowls%20%20%20',false\)&input=LS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLQ0KY29uZ3JhdHMgaGVyZSBpcyB5b3VyIGZsYWcgLSBmcmVxdWVuY3lfaXNfY19vdmVyX2xhbWJkYV9kbnZ0ZnJ0YXl1DQotLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tLS0tDQpoYXZpbmcgaGFkIHNvbWUgdGltZSBhdCBteSBkaXNwb3NhbCB3aGVuIGluIGxvbmRvbiwgaSBoYWQgdmlzaXRlZCB0aGUgYnJpdGlzaCBtdXNldW0sIGFuZCBtYWRlIHNlYXJjaCBhbW9uZyB0aGUgYm9va3MgYW5kIG1hcHMgaW4gdGhlIGxpYnJhcnkgcmVnYXJkaW5nIHRyYW5zeWx2YW5pYTsgaXQgaGFkIHN0cnVjayBtZSB0aGF0IHNvbWUgZm9yZWtub3dsZWRnZSBvZiB0aGUgY291bnRyeSBjb3VsZCBoYXJkbHkgZmFpbCB0byBoYXZlIHNvbWUgaW1wb3J0YW5jZSBpbiBkZWFsaW5nIHdpdGggYSBub2JsZW1hbiBvZiB0aGF0IGNvdW50cnkuIGkgZmluZCB0aGF0IHRoZSBkaXN0cmljdCBoZSBuYW1lZCBpcyBpbiB0aGUgZXh0cmVtZSBlYXN0IG9mIHRoZSBjb3VudHJ5LCBqdXN0IG9uIHRoZSBib3JkZXJzIG9mIHRocmVlIHN0YXRlcywgdHJhbnN5bHZhbmlhLCBtb2xkYXZpYSBhbmQgYnVrb3ZpbmEsIGluIHRoZSBtaWRzdCBvZiB0aGUgY2FycGF0aGlhbiBtb3VudGFpbnM7IG9uZSBvZiB0aGUgd2lsZGVzdCBhbmQgbGVhc3Qga25vd24gcG9ydGlvbnMgb2YgZXVyb3BlLiBpIHdhcyBub3QgYWJsZSB0byBsaWdodCBvbiBhbnkgbWFwIG9yIHdvcmsgZ2l2aW5nIHRoZSBleGFjdCBsb2NhbGl0eSBvZiB0aGUgY2FzdGxlIGRyYWN1bGEsIGFzIHRoZXJlIGFyZSBubyBtYXBzIG9mIHRoaXMgY291bnRyeSBhcyB5ZXQgdG8gY29tcGFyZSB3aXRoIG91ciBvd24gb3JkbmFuY2Ugc3VydmV5IG1hcHM7IGJ1dCBpIGZvdW5kIHRoYXQgYmlzdHJpdHosIHRoZSBwb3N0IHRvd24gbmFtZWQgYnkgY291bnQgZHJhY3VsYSwgaXMgYSBmYWlybHkgd2VsbC1rbm93biBwbGFjZS4gaSBzaGFsbCBlbnRlciBoZXJlIHNvbWUgb2YgbXkgbm90ZXMsIGFzIHRoZXkgbWF5IHJlZnJlc2ggbXkgbWVtb3J5IHdoZW4gaSB0YWxrIG92ZXIgbXkgdHJhdmVscyB3aXRoIG1pbmEuDQoNCg&oenc=65001&ieol=CRLF&oeol=CRLF)
```
