# Hashing and Digital Signatures

## Cryptographic Keys (Ciphers)

Keep them private: you dont want the public knowing how to decipher your messages

The key determines the output: Many different types of a key, some keys are one-way keys and cannot be undone

Trust the process: Sometimes the algorithm is weill known, however, the public does not know the individual key

## Key basics

- Do not use short keys
    - helps prevent against brute force attacks
    - 128 bit or higher keys are common
    - A lot of keys use very high prime numbers
- How to exchange keys (across an unsecure medium)?
    - key must remain a secret
    - trusted domains help protect the keys
        - Diffie-Hellman is a common key exchange
    - Encrypt and protect the key exchange

## Famous ciphers:
Pigpen Cipher:
    - Used by Freemason's in the 1700's
        - Letters represented by symbols

Engigma Machine
    - Used by germans in the WW2
        - "Cracked" by some of the allies


## Hashes

Collisions is what its called when two different inputs generate the same output.

One way algorithm
    - Encryption can only work one way, can not be reversed
    - Thus, you can not recover the original password
    - This helps keep password confidentialty
Common uses
    - Verify a downlaoded data is the same as the original data

Digital signatures

## Hash examples

- SHA224 (224 bits)
- MD5 (128 bits)

## Collision

COllision is two different inputs have the same output. Hashing should never have two different passwords have the same hash.
There are some examples where hashes give same output, buts its very rare (1 in a million if/when they are found)

## Salt, IV, Nonce

Salt is a random data used for additional input to a hashing algorithm (or one way algorithm)

IV (initialization Vector) is mainly used for wireless connections

A nonce is a salt that only used once

## Practical Hashing

1. Storing passwords
    - Hash is stored instead of actual password
    - Hashes will be compared instead of password
    - Original password cant be retrieved
2. Verifying a downloadable file
    - Website provides the hash
    - If hash is the same, the document hasnt been finished


## Elliptic Curve Cryptography (ECC)

- Asymmetric encryption
    - Extremely large numbers (integers) that are made from two or more extremely large prime numbers
- ECC uses cursed instead of integers
    - Add two points together on a curve to get a third point
    - Can be "hacked", but more resistant


## Traditional web server encryption

- SSL/TLS
    - Uses encryption keys to protect web server communication
    - Traditionally, based on the web server's RSA key pair
- Downfall?
    - This server's private key

- One single point of failure