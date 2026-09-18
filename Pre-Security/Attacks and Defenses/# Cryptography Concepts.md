# Cryptography Concepts

## What is Cryptography?

**Cryptography** is the practice of protecting information by transforming it so that only authorized people can understand it.

It is used to provide:

* **Confidentiality** → only authorized people can read the data
* **Integrity** → data has not been changed
* **Authentication** → verify who someone is
* **Non-repudiation** → prove that a message/signature came from a particular source

---

## Plaintext and Ciphertext

**Plaintext** = original readable data.

**Ciphertext** = encrypted/unreadable data.

Basic process:

```text
Plaintext
   ↓
Encryption
   ↓
Ciphertext
   ↓
Decryption
   ↓
Plaintext
```

---

## Encryption

Encryption transforms readable data into ciphertext using an **encryption algorithm and a key**.

Example:

```text
Plaintext:  Hello
     ↓
Encryption + Key
     ↓
Ciphertext: x7F9a...
```

The goal is that someone without the correct key cannot understand the original data.

---

## Symmetric Encryption

**Symmetric encryption uses the same key for encryption and decryption.**

```text
             Same Key
                ↓
Plaintext → Encryption → Ciphertext
                              ↓
                         Decryption
                              ↓
                           Plaintext
```

Examples:

* AES
* ChaCha20

### Main
