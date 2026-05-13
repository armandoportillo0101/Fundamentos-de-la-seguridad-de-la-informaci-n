## Descripción
```
What does asm3(0xd73346ed,0xd48672ae,0xd3c8b139) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/17c5620fcffa388fe518d31cb4dd99a0/test.S)
```
## Solución
```
push 0xd3c8b139	
push 0xd48672ae
push 0xd73346ed
call asm3
	
asm3:
		push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xa]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xc]
        add    ah,BYTE PTR [ebp+0xd]
        xor    ax,WORD PTR [ebp+0x10]
        nop
        pop    ebp
        ret

flag: 0xC36B
```

## Notas 
```
Simulamos el corrimiento del codigo la página que está en las referencias
```

## Referencias
````
[https://carlosrafaelgn.com.br/Asm86/](https://carlosrafaelgn.com.br/Asm86/)
```
