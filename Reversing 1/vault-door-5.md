## Descripción
```
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)
```
## Solución
```
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/vd5$ wget https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java
porti_04@DESKTOP-8HT902T:~/pico_retos/reversing/vd5$ cat VaultDoor5.java
import java.net.URLDecoder;
import java.util.*;

class VaultDoor5 {
    public static void main(String args[]) {
        VaultDoor5 vaultDoor = new VaultDoor5();
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

    // Minion #7781 used base 8 and base 16, but this is base 64, which is
    // like... eight times stronger, right? Riiigghtt? Well that's what my twin
    // brother Minion #2415 says, anyway.
    //
    // -Minion #2414
    public String base64Encode(byte[] input) {
        return Base64.getEncoder().encodeToString(input);
    }

    // URL encoding is meant for web pages, so any double agent spies who steal
    // our source code will think this is a web site or something, defintely not
    // vault door! Oh wait, should I have not said that in a source code
    // comment?
    //
    // -Minion #2415
    public String urlEncode(byte[] input) {
        StringBuffer buf = new StringBuffer();
        for (int i=0; i<input.length; i++) {
            buf.append(String.format("%%%2x", input[i]));
        }
        return buf.toString();
    }

    public boolean checkPassword(String password) {
        String urlEncoded = urlEncode(password.getBytes());
        String base64Encoded = base64Encode(urlEncoded.getBytes());
        String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
                        + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
                        + "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";
        return base64Encoded.equals(expected);
    }
}

flag: picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}
```

## Notas 
```
La bandera se encuentra en esta parte: public boolean checkPassword(String password) { String urlEncoded = urlEncode(password.getBytes()); String base64Encoded = base64Encode(urlEncoded.getBytes()); String expected = "JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm" + "JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2" + "JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";

Tienes que acomodarla asi y despues ponerla en cyberchef para descifrarla: JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2 JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0
```

## Referencias
````
[https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true,false)URL_Decode()&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm0NCkpUWTJKVGN5SlRNd0pUWmtKVFZtSlRZeUpUWXhKVE0xSlRZMUpUVm1KVE0yDQpKVE0wSlRWbUpUWTFKVE16SlRNeEpUTTFKVE15SlRZeUpUWTJKVE0w&ieol=CRLF&oeol=CRLF](https://gchq.github.io/CyberChef/#recipe=From_Base64\('A-Za-z0-9%2B/%3D',true,false\)URL_Decode\(\)&input=SlRZekpUTXdKVFpsSlRjMkpUTXpKVGN5SlRjMEpUTXhKVFpsSlRZM0pUVm0NCkpUWTJKVGN5SlRNd0pUWmtKVFZtSlRZeUpUWXhKVE0xSlRZMUpUVm1KVE0yDQpKVE0wSlRWbUpUWTFKVE16SlRNeEpUTTFKVE15SlRZeUpUWTJKVE0w&ieol=CRLF&oeol=CRLF)
```