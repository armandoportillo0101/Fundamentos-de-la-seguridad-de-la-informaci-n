## Descripción
```
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
```
## Solución
```
portidell_g3@DESKTOP-28KM9FK:~$ wget https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
--2026-03-27 10:55:01--  https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz
Resolving challenge-files.picoctf.net (challenge-files.picoctf.net)... 3.161.44.84, 3.161.44.103, 3.161.44.22, ...
Connecting to challenge-files.picoctf.net (challenge-files.picoctf.net)|3.161.44.84|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1776 (1.7K) [application/octet-stream]
Saving to: ‘fixme3.tar.gz’

fixme3.tar.gz                 100%[=================================================>]   1.73K  --.-KB/s    in 0s

2026-03-27 10:55:01 (138 MB/s) - ‘fixme3.tar.gz’ saved [1776/1776]

portidell_g3@DESKTOP-28KM9FK:~$ tar -xvzf fixme3.tar.gz
fixme3/
fixme3/Cargo.toml
fixme3/Cargo.lock
fixme3/src/
fixme3/src/main.rs
portidell_g3@DESKTOP-28KM9FK:~$ cd fixme 3
-bash: cd: too many arguments
portidell_g3@DESKTOP-28KM9FK:~$ cd fixme3
portidell_g3@DESKTOP-28KM9FK:~/fixme3$ ls
Cargo.lock  Cargo.toml  src
portidell_g3@DESKTOP-28KM9FK:~/fixme3$ cd src
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ ls
main.rs
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ cat main.rs
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String) {
    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decryption object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return;
    }
    let xrc = res.unwrap();

    // Did you know you have to do "unsafe operations in Rust?
    // https://doc.rust-lang.org/book/ch19-01-unsafe-rust.html
    // Even though we have these memory safe languages, sometimes we need to do things outside of the rules
    // This is where unsafe rust comes in, something that is important to know about in order to keep things in perspective

    // unsafe {
        // Decrypt the flag operations
        let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

        // Creating a pointer
        let decrypted_ptr = decrypted_buffer.as_ptr();
        let decrypted_len = decrypted_buffer.len();

        // Unsafe operation: calling an unsafe function that dereferences a raw pointer
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);

        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
    // }
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "12", "90", "7e", "53", "63", "e1", "01", "35", "7e", "59", "60", "f6", "03", "86", "7f", "56", "41", "29", "30", "6f", "08", "c3", "61", "f9", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: ");
    decrypt(encrypted_buffer, &mut party_foul);
}portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/portidell_g3/fixme3)
error[E0133]: call to unsafe function is unsafe and requires unsafe function or block
  --> src/main.rs:31:31
   |
31 |         let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);
   |                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ call to unsafe function
   |
   = note: consult the function's documentation for information on how to avoid undefined behavior

For more information about this error, try `rustc --explain E0133`.
error: could not compile `rust_proj` (bin "rust_proj") due to previous error
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ nano main.rs
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ cargo build
   Compiling rust_proj v0.1.0 (/home/portidell_g3/fixme3)
    Finished dev [unoptimized + debuginfo] target(s) in 1.29s
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$ cargo run
    Finished dev [unoptimized + debuginfo] target(s) in 0.03s
     Running `/home/portidell_g3/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
portidell_g3@DESKTOP-28KM9FK:~/fixme3/src$

flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

```

## Notas 
```
Aquí esta el codigo corregido: 
use xor_cryptor::XORCryptor;

fn decrypt(encrypted_buffer: Vec<u8>, borrowed_string: &mut String) {
    // Key for decryption
    let key = String::from("CSUCKS");

    // Editing our borrowed value
    borrowed_string.push_str("PARTY FOUL! Here is your flag: ");

    // Create decryption object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return;
    }
    let xrc = res.unwrap();

    // Did you know you have to do "unsafe operations in Rust?
    // https://doc.rust-lang.org/book/ch19-01-unsafe-rust.html
    // Even though we have these memory safe languages, sometimes we need to do things outside of the rules
    // This is where unsafe rust comes in, something that is important to know about in order to keep things in perspective

    // Decrypt the flag operations
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);

    // Creating a pointer
    let decrypted_ptr = decrypted_buffer.as_ptr();
    let decrypted_len = decrypted_buffer.len();

    // Unsafe operation: calling an unsafe function that dereferences a raw pointer
    // Descomentar el bloque unsafe y mover las operaciones dentro
    unsafe {
        let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);
        borrowed_string.push_str(&String::from_utf8_lossy(decrypted_slice));
    }
    
    println!("{}", borrowed_string);
}

fn main() {
    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "12", "90", "7e", "53", "63", "e1", "01", "35", "7e", "59", "60", "f6", "03", "86", "7f", "56", "41", "29", "30", "6f", "08", "c3", "61", "f9", "35"];

    // Convert the hexadecimal strings to bytes and collect them into a vector
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    let mut party_foul = String::from("Using memory unsafe languages is a: ");
    decrypt(encrypted_buffer, &mut party_foul);
}
```

## Referencias
````

```
