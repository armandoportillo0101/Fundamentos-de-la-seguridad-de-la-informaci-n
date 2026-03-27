## Descripción
```
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
--2026-03-25 22:02:07--  https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.103, 3.161.44.22, 3.161.44.61, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.103|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1415 (1.4K) [application/octet-stream]
Saving to: ‘fixme1.tar.gz’

fixme1.tar.gz                 100%[=================================================>]   1.38K  --.-KB/s    in 0s

2026-03-25 22:02:09 (103 MB/s) - ‘fixme1.tar.gz’ saved [1415/1415]

portidell_g3@DESKTOP-28KM9FK:~$ tar -xvzf fixme1.tar.gz
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
portidell_g3@DESKTOP-28KM9FK:~$ cd fixme1
portidell_g3@DESKTOP-28KM9FK:~/fixme1$ cd src
portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$ ls
main.rs
portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$ cat main.rs
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS") // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        ret; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        ":?", // How do we print out a variable in the println function?
        String::from_utf8_lossy(&decrypted_buffer)
    );
}portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$ nano main.rs
portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/portidell_g3/fixme1)
    Finished dev [unoptimized + debuginfo] target(s) in 5.33s
portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.03s
     Running `/home/portidell_g3/fixme1/target/debug/rust_proj`
Flag decifrada: picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

Bytes decifrados (hex):
[0]: 0x70 ('p')
[1]: 0x69 ('i')
[2]: 0x63 ('c')
[3]: 0x6f ('o')
[4]: 0x43 ('C')
[5]: 0x54 ('T')
[6]: 0x46 ('F')
[7]: 0x7b ('{')
[8]: 0x34 ('4')
[9]: 0x72 ('r')
[10]: 0x33 ('3')
[11]: 0x5f ('_')
[12]: 0x79 ('y')
[13]: 0x30 ('0')
[14]: 0x75 ('u')
[15]: 0x5f ('_')
[16]: 0x34 ('4')
[17]: 0x5f ('_')
[18]: 0x72 ('r')
[19]: 0x75 ('u')
[20]: 0x24 ('$')
[21]: 0x74 ('t')
[22]: 0x34 ('4')
[23]: 0x63 ('c')
[24]: 0x33 ('3')
[25]: 0x30 ('0')
[26]: 0x6e ('n')
[27]: 0x5f ('_')
[28]: 0x6e ('n')
[29]: 0x30 ('0')
[30]: 0x77 ('w')
[31]: 0x3f ('?')
[32]: 0x7d ('}')

✅ La flag comienza correctamente!
portidell_g3@DESKTOP-28KM9FK:~/fixme1/src$

flag: picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}

```

## Notas 
```
Este es el archivo main.rs corregido: 
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS");

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", "1c", "7e", "59", "63", "e1", "61", "25", "7f", "5a", "60", "50", "11", "38", "1f", "3a", "60", "e9", "62", "20", "0c", "e6", "50", "d3", "35"];

    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let res = XORCryptor::new(&key);
    if res.is_err() {
        println!("Error creating XORCryptor");
        return;
    }
    let xrc = res.unwrap();

    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    
    // Imprimir como string
    let result = String::from_utf8_lossy(&decrypted_buffer);
    println!("Flag decifrada: {}", result);
    
    // Imprimir bytes individuales para depuración
    println!("\nBytes decifrados (hex):");
    for (i, byte) in decrypted_buffer.iter().enumerate() {
        println!("[{}]: 0x{:02x} ('{}')", i, byte, *byte as char);
    }
    
    // Verificar si empieza con "picoCTF{"
    if result.starts_with("picoCTF{") {
        println!("\n✅ La flag comienza correctamente!");
    } else {
        println!("\n❌ La flag NO comienza con 'picoCTF{{'");
        println!("Primeros caracteres: {:?}", &result[0..result.len().min(10)]);
    }
}
```

## Referencias
````

```
