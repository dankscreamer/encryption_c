# Simple XOR Encryption Tool (C)

A beginner-level encryption/decryption program written in C to explore how basic stream ciphers work using bitwise XOR operations and Unix-style input/output redirection.

This project was created as a learning exercise after studying low-level I/O, command-line arguments, and bitwise operations in C.

---

## Overview

This program implements a **very simple symmetric encryption scheme** based on the XOR operation.

The same program can be used for:
- **Encryption**
- **Decryption**

as long as the same key is used.

This works because of a fundamental XOR property:




---

## How the Program Works

1. A key is provided as a command-line argument.
2. The key is converted into a numeric bitmask by summing the ASCII values of its characters.
3. Input is read **byte-by-byte** from standard input (`stdin`).
4. Each byte is XORed with the bitmask.
5. The transformed byte is written to standard output (`stdout`).

The program does not store the entire file in memory, making it a **stream-based** transformation.

---

## Code Structure

- `get_bitmask()`
  Converts the key string into an integer by summing ASCII values.

- `encrypt()`
  Applies XOR between a single byte and the bitmask.

- `main()`
  Reads input from `stdin`, applies encryption byte-by-byte, and writes to `stdout`.

---

## Compilation

Use `gcc` to compile:

```bash
gcc enc.c -o enc


Usage
Encrypt a file
./enc mykey < secret.txt > encrypted.txt

Decrypt the file
./enc mykey < encrypted.txt > decrypted.txt


Because XOR is symmetric, the same command decrypts the data when applied again with the same key.
