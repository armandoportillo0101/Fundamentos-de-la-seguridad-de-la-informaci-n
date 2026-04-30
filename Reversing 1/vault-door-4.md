## Descripción
```
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/vd4$ wget https://jupiter.challenges.picoctf.org/static/09d3002ae349631324a17e2255ae8df2/VaultDoor4.java
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/vd4$ cat VaultDoor4.java
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
    }

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 0143, 061 ,
            '9' , '4' , 'f' , '7' , '4' , '5' , '8' , 'e' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/vd4$

flag: picoCTF{jU5t_4_bUnCh_0f_bYt3s_c194f7458e}
```

## Notas 
```
public boolean checkPassword(String password) {
    byte[] passBytes = password.getBytes();
    byte[] myBytes = {
        106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
        0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
        0142, 0131, 0164, 063 , 0163, 0137, 0143, 061 ,
        '9' , '4' , 'f' , '7' , '4' , '5' , '8' , 'e' ,
    };
    

Esa parte contiene la bandera y lo decodificamos usando cyberchef, son 3 tipos: decimal, hexadeciamal y octal. La cuarta linea solo se tiene que quitar las coma, comillas y espacios.
```

## Referencias
````
[https://gchq.github.io/CyberChef/#input=JzknICwgJzQnICwgJ2YnICwgJzcnICwgJzQnICwgJzUnICwgJzgnICwgJ2UnDQogICAgICAgICAgIA&ieol=CRLF&oeol=CRLF](https://gchq.github.io/CyberChef/#input=JzknICwgJzQnICwgJ2YnICwgJzcnICwgJzQnICwgJzUnICwgJzgnICwgJ2UnDQogICAgICAgICAgIA&ieol=CRLF&oeol=CRLF)
```