# OpenSSL Lab – Key Generation, Encryption/Decryption, and Digital Signatures

## Overview

In this lab, I learned how to use **OpenSSL** to perform basic public key cryptography tasks.  
The goal was to generate RSA keys, encrypt and decrypt a message, and create and verify a digital signature.

Public key cryptography works using two keys:

- a **public key** that can be shared with others
- a **private key** that must remain secret

Data encrypted with the public key can only be decrypted using the private key.  
Similarly, data signed with the private key can be verified using the public key.

---

## 1. Generating Keys

The first step was generating an RSA key pair.

### Generating the private key

I started by generating a **2048-bit RSA private key** using OpenSSL with the following command:

openssl genrsa -out private_key.pem 2048

This command created a new private key file called **private_key.pem**.  
While generating the key, OpenSSL displayed progress messages in the terminal.

To inspect the private key, I displayed the file contents using:

cat private_key.pem

The output contained a block that started with:

-----BEGIN RSA PRIVATE KEY-----

and ended with:

-----END RSA PRIVATE KEY-----

This file contains the private key and must be kept secret, because anyone with access to it could decrypt encrypted messages or create valid digital signatures.

### Check my progress

Generate private key

![Screenshot 1](screenshots/generate_private_key01.png)

---

### Generating the public key

After generating the private key, I created the **public key** from it. The public key can safely be shared with others so they can encrypt data or verify digital signatures.

I ran the following command:

openssl rsa -in private_key.pem -outform PEM -pubout -out public_key.pem

OpenSSL responded with:

writing RSA key

This command generated a file called **public_key.pem**.

To view the public key, I used:

cat public_key.pem

The output showed a block beginning with:

-----BEGIN PUBLIC KEY-----

and ending with:

-----END PUBLIC KEY-----

Unlike the private key, this key is intended to be distributed publicly.

### Check my progress

Generate public key

![Screenshot 2](screenshots/generate_public_key02.png)

---

## 2. Encrypting and Decrypting a Message

Next, I used the generated keys to encrypt and decrypt a secret message.

### Creating a secret message

First, I created a text file containing a message:

echo 'This is a secret message, for authorized parties only' > secret.txt

This command created a file called **secret.txt** containing the message.

### Encrypting the message

Next, I encrypted the message using the **public key**:

openssl rsautl -encrypt -pubin -inkey public_key.pem -in secret.txt -out secret.enc

This created a new file called **secret.enc**, which contained the encrypted data.

When I opened the encrypted file using:

nano secret.enc

the contents appeared as random or unreadable characters.  
This is normal because encrypted data is not meant to be human-readable.

### Decrypting the message

To recover the original message, I used the **private key**:

openssl rsautl -decrypt -inkey private_key.pem -in secret.enc

The terminal displayed the original message:

This is a secret message, for authorized parties only

This confirmed that the encrypted data could only be decrypted using the matching private key.

### Check my progress

Encrypting and decrypting

![Screenshot 3](screenshots/encrypting03_01.png)

![Screenshot 3](screenshots/nano_fail_reading03_02.png)

![Screenshot 3](screenshots/decrypting03_03.png)

---

## 3. Creating and Verifying a Digital Signature

In the final part of the lab, I created and verified a **digital signature**.

Digital signatures ensure that a file:

- has not been modified
- was created or approved by the owner of the private key

### Creating a signature

I generated a signed hash of the message using SHA-256 and my private key:

openssl dgst -sha256 -sign private_key.pem -out secret.txt.sha256 secret.txt

This created a signature file called **secret.txt.sha256**.

### Verifying the signature

Next, I verified the signature using the public key:

openssl dgst -sha256 -verify public_key.pem -signature secret.txt.sha256 secret.txt

The command returned:

Verified OK

This confirmed that the file had not been modified and that the signature matched the public key.

### Check my progress

Sign and verify

![Screenshot 4](screenshots/sign_verify04.png)

---

## What I Learned

In this lab, I learned how to perform several fundamental cryptographic operations using OpenSSL.

First, I generated an RSA key pair consisting of a **private key** and a **public key**. The private key must remain secure, while the public key can be shared freely.

Next, I used the public key to **encrypt a message** and the private key to **decrypt it**, demonstrating how asymmetric encryption protects sensitive information.

Finally, I created and verified a **digital signature**, which confirmed both the authenticity and integrity of a file.

Overall, this exercise helped me understand how public key cryptography works in practice and how OpenSSL can be used to implement encryption, decryption, and digital signatures in real-world security scenarios.