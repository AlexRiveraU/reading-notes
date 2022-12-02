# Cryptography

This topic matters as it relates to learning what is cryptography, how it works and its importance for security purposes when working online.

---

## Encryption, Decryption, Hacking & Caesar Cipher

One of the earliest encryption techniques is the Caesar Cipher, invented by Julius Caesar more than two thousand years ago to communicate messages to his allies. In cryptography, a Caesar cipher, aka Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques. It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet. It is often incorporated as part of more complex schemes, and still has modern application in the ROT13 system. It is easily broken and in modern practice offers essentially no communications security.

* **Encryption -** Process of making text secret. Scrambling the data according to a secret key.
* **Decryption -** Process of reversing encryption. Recovering the original data from scrambled data by using the secret key.
* **Code cracking:** Uncovering the original data without knowing the secret, by using a variety of clever techniques.

- [*source_1*](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)
- [*source_2*](https://en.wikipedia.org/wiki/Caesar_cipher)

---

## Cryptography Crash Course

There is no such thing as a perfectly, 100% secure, computer system. There will always be bugs. 

 * **Defense in Depth -** Strategy that uses many layers of varying security mechanisms to frustrate attackers.
 * **Cryptography -** One of the most common forms of computer security. The term comes from the roots: *crypto* = *secret*, and *graphy* = *writing*. 
 * **Cipher -** Algorithm that converts plain text into a ciphertext. It is gibberish to us unless we have a key that lets us undo the cipher. 

>Class of Techniques:

* **Substitution Ciphers -** Replaces every letter in a message with something else according to a translation. The downside is that letter frequencies are preserved.
* **Permutation Ciphers -** A *columnar transposition cipher* fills letters into a grid and reads characters in a different order. This new letter order is called **permutation**, which is the encrypted message. The ordering directing and the grid-size is the **Key**.

#### Data Encryption Standard (DES) 

One of the earliest software cipher to become widespread, developed by IBM and the NSA in 1977. Uses binary keys. Soon after regular computers were able to crack DES easily.

#### Advanced Encryption Standard (AES) 

Finalized in 2001. Designed to use much bigger keys - 128, 192 or 256 bits in size. Chops data into 16-byte blocks and applies a series of substitutions and permutations, based on the key value, plus some other operations to obscure the message. This is what is use currently everywhere.

#### Key Exchange

An algorithm that lets two computers agree on a key without ever sending one. We do this with **one-way functions**, which are mathematical operations that are easy to do it in one direction, but hard to reverse.

#### Diffie-Hellman Key Exchange

In this key exchange the one-way function is modular exponentiation, which means that it takes one number, *the base*, to power of another number, *the exponent*, and taking the remainder when dividing by a third number, *the modulus*. We get symmetric keys, because the key is the same on both sides.

* **Symmetric Encryption -** When the key is the same on both sides.
* **Asymmetric Encryption -** Where there are two different keys. Usually one is public and the other one is private.

The padlock in our browser next to the url, means that the website has used public key cryptography to verify the server, key exchange to establish a secret temporary key, and symmetric encryption to protect all the back-and-forth communication.

[*source*](https://www.youtube.com/watch?v=jhXCTbFnK8o)

---

### Things I want to know more about

* I would like to know more about how to implement symmetric and asymmetric encryption and when it is recommended to use each one of them. 

---

[-back](https://alexriverau.github.io/reading-notes/code401)
