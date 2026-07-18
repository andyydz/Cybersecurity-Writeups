# Cryptography

![Status](https://img.shields.io/badge/Status-Completed-brightgreen)
![Platform](https://img.shields.io/badge/Platform-TryHackMe-red)
![Difficulty](https://img.shields.io/badge/Difficulty-Easy--Medium-yellow)
![Category](https://img.shields.io/badge/Category-Cryptography-purple)

> **Key finding:** RSA isn't magic — it's math. Once you understand that its security is based entirely on how hard it is to factor large prime numbers, everything else (certificates, HTTPS, SSH keys) starts to make sense.

---

## Overview

Cryptography is the backbone of nearly every secure protocol in use today. This writeup covers two TryHackMe rooms — **Cryptography Basics** and **Public Key Cryptography Basics** — documenting what I learned about encryption types, RSA, Diffie-Hellman, digital signatures, and PGP/GPG, and how each shows up in real SOC work.

🔗 [Cryptography Basics](https://tryhackme.com/room/cryptographybasics)
🔗 [Public Key Cryptography Basics](https://tryhackme.com/room/publickeycrypto)

---

## What I Actually Found

| Concept | Key Insight |
|---|---|
| Symmetric encryption | Same key encrypts and decrypts — fast, but key sharing is the weak point |
| Asymmetric encryption | Public key encrypts, private key decrypts — solves the key distribution problem |
| RSA | Security depends on difficulty of factoring large primes — 2048-bit minimum today |
| Diffie-Hellman | Two parties derive the same shared secret without ever sending the key |
| Digital signatures | Proves data came from who it claims, and wasn't tampered with in transit |
| Certificates | How browsers verify a website is legitimate — basis of HTTPS trust |
| PGP / GPG | Still used professionally for encrypting files and emails |

---

## Challenges & Real Lessons

**1. RSA clicked only when I thought about the math**
The concept of public/private keys felt abstract until I understood why it works — factoring the product of two huge prime numbers is computationally infeasible. That's it. That's the whole security model. Once that clicked, RSA made complete sense.

**2. Diffie-Hellman is elegant**
Two people can agree on a shared secret over a completely public channel without ever sending the secret itself. Neither side transmits the key — both independently derive the same value. This is what powers TLS handshakes in HTTPS every time you open a browser.

**3. Certificates aren't just for HTTPS**
I assumed certificates were only a browser thing. But they're used in email signing, code signing, VPN authentication, and SSH. In SOC work, expired or self-signed certificates on internal services are red flags worth investigating.

---

## Hands-On Activities

### Cryptography Basics
- Traced the journey from plaintext to ciphertext using historical ciphers
- Compared symmetric vs asymmetric encryption — use cases and limitations
- Understood the mathematical foundations behind modern encryption
- Identified why key distribution is the core problem symmetric encryption can't solve alone

### RSA
- Studied how RSA uses two large prime numbers to generate public/private key pairs
- Understood why breaking RSA requires factoring the product of those primes
- Practiced generating RSA key pairs using OpenSSL

### Diffie-Hellman Key Exchange
- Understood how two parties derive a shared secret without transmitting it
- Connected this concept to TLS/HTTPS handshake behavior
- Recognized DH as the reason forward secrecy is possible in modern TLS

### Digital Signatures & Certificates
- Learned how digital signatures prove authenticity and integrity
- Understood the role of Certificate Authorities (CAs) in the trust chain
- Connected certificates to MITM attack detection in SOC work

### PGP / GPG
- Practiced encrypting and decrypting files using GPG
- Understood how PGP combines symmetric and asymmetric encryption together
- Recognized GPG as a tool still used in professional environments

---

## Key Findings & Tasks

- Traced the full journey from plaintext to ciphertext using historical cipher examples
- Identified the core difference between symmetric and asymmetric encryption and when each is used
- Understood why RSA works — security is based on the infeasibility of factoring large prime products
- Generated RSA key pairs using OpenSSL and inspected both public and private key files
- Analyzed how Diffie-Hellman allows two parties to derive a shared secret over a public channel
- Understood how digital signatures verify both authenticity and integrity of data
- Explored how Certificate Authorities (CAs) form the trust chain behind HTTPS
- Practiced encrypting and decrypting files using GPG
- Connected all concepts to real protocols — HTTPS, SSH, VPN, email signing

---

## What I Learned

- RSA isn't complicated once you see the math — two large primes, multiply them, and factoring that product is what makes it secure
- Diffie-Hellman solves a real problem elegantly — two people agreeing on a secret without ever sending the secret itself
- Every HTTPS connection uses both asymmetric (for key exchange) and symmetric (for actual data) encryption — they work together, not separately
- Digital certificates are how your browser decides to trust a website — understanding this makes MITM attacks make a lot more sense
- Expired or self-signed certificates on internal services are a SOC red flag — not just a browser warning
- GPG/PGP are not outdated — they're still used in professional environments for secure file transfer and email signing
- Cryptography isn't just theory — it's behind every tool a SOC analyst uses daily

---

## Key Commands Used

```bash
# Generate RSA private key
openssl genrsa -out private.key 2048

# Extract public key from private key
openssl rsa -in private.key -pubout -out public.key

# Encrypt a file with GPG
gpg --encrypt --recipient "user@example.com" file.txt

# Decrypt a file with GPG
gpg --decrypt file.txt.gpg

# Generate SSH key pair
ssh-keygen -t rsa -b 4096

# View certificate details
openssl x509 -in cert.pem -text -noout
```
