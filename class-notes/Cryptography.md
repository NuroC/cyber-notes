# Modern Cryptography

## Threats to Confidentiality and Integrity

Confidentiality: ensuring information is disclosed to only to those authorized to know it.

Integrity: ensuring information is only modified by authorized parties.

Threats to consider:
    - Data in motion
        - Packet sniffing / wiretap / surveillance
        - Man-in-the-middle (MITM)
    - Data in transit
        - Email sitting in a mail server
        - Web Proxy
    - Data at rest (DAR)
        - File grabbing from a compromised system
        - Stolen laptop

## What can we enforce? `PAIN`

- `Privacy` - Transactions cannot be viewed by an unauthorized party.
- `Authorization` - assurance that an entity's identity claim is valid
- `Integrity` - the assurance that data has not been altered either intentionally or unintentionally
- `Non-repudiation` - Incontrovertible evidence of what occured and who was involved.

## Cryptography Concepts

- `Plaintext` The original message, not necessarily text.
- `Ciphertext` The transformed (encrypted) message, should resemble random noise
- `Encryption Algorithm` Takes a plaintext plus an encryption key and returns a ciphertext
- `Decription Algorithm` Takes a ciphertext and a decryption key and returns the plaintext
- `Kerchoff's Principle` The security of the system cannot rely on keeping the algorithms secret.

## Symmetric and Asymmetric Cryptography

Symmetric cryptography uses only one key for decoding and encoding.

Asymmetric uses one public key and one private key.

### Symmetric Key

We use symmetric keys to share keys for assymetric keys.

- Both sides use the same key to encrypt and decrypt

Advantages:
    - String for shorter key lengths
    - Fast - suitable for real time and bulk encryption of high speed communication systems

Disadvantages:
    - Key distribution
    - Key management

Digital Encryption Standard (DES), 3DES, Advanced Enryption Standard (AES)

### Assymetric key

It solves the key distribution problem!!

We use different (but related) keys encryption and decryption
    - Sender encrypts with receives public key
    - receiver decrypts with receives private key

RSA Algorithm, Elliptic curve cryptography

Advantages:
    - Key distribution: Only the private key must be kept secret, the public key can be shared freely.
    - Also suppports authentication and non-repudiation via digital signatures.

Disadvantages:
- Strings is dependent on the infeasivillity of solving certain hard (as in NP) problems
    - e.g. Discrete logarithm, factoring large numbers, the knapsack problems.
        - What is the product of 3456 * 7890?
        - What are my two factors that have the product 15,104,434
    - A mathematical breakthrough could provide a feasible way to solve the problem and break the encryption
    - Faster computers, quantum computers, etc. could facilitate breaking encryption.
- Much slower than symmetric key. Not suitable for real time or bulk encryption
    - We use assymetric methods for gitital signatures, for exchanging symmetric keys and for key agreement


##  PKI

The issuer digitally signs the certificates, allowing us to verify their authenticity and integrity. There may be multiple layers of certificates verifying others in a `tree of trust` or `web of trust`. A CA has one or more `root certificates` that we must trust implicitly.

Certificates have an expiration date. The CA may issue a certificate revocation list (CRL) of certificates that have not expired but should not be trusted.


## Key exchange

Two aprties with no prior knowledge... Establish a shared secret key... Over an insecure communication channel





