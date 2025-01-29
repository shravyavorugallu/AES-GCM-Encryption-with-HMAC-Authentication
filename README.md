# AES-GCM Encryption with HMAC Authentication

## Description
This project implements a secure communication system using **AES-GCM encryption** combined with **HMAC-based message authentication**. It ensures both confidentiality and integrity of messages, where:
1. **AES-GCM** encrypts the plaintext message, producing a ciphertext, nonce, and authentication tag.
2. **HMAC** generates a tag to authenticate the ciphertext, preventing tampering.

The receiver verifies the HMAC tag before decrypting the ciphertext. If verification fails, the decryption step is skipped to ensure data integrity.

## Features
- **AES-GCM encryption** for confidentiality and integrity.
- **HMAC authentication** for tamper detection.
- Prevents unauthorized decryption by validating the HMAC tag.

## Prerequisites
- Python 3.x installed.
- `pycryptodome` library installed.

## Installation
Install the required library using pip:
```bash
pip install pycryptodome
```
## Usage
Save the script as YourLastName-HMAC-AES-GCM.py (replace YourLastName with your actual last name).
Run the script:
```bash
python HMAC-AES-GCM.py
Example Output
plaintext
Original Text: Hello, this is a secure message.
Encrypted (hex): 3a1f4b9c...
HMAC (hex): 5e2f3a4b...
HMAC verified successfully.
Decrypted Text: Hello, this is a secure message.
```
How It Works
Encryption:

AES-GCM generates a ciphertext, nonce, and AES tag for the plaintext.
HMAC computes an authentication tag using the ciphertext and a separate HMAC key.

Authentication:
The HMAC tag ensures the ciphertext hasn't been tampered with.
If HMAC verification fails, decryption is skipped to prevent unauthorized access.

Decryption:
The receiver decrypts the ciphertext only if the HMAC tag is valid, ensuring the integrity and authenticity of the message.

## Code Overview

The script includes:

aes_gcm_encrypt(plaintext, aes_key): Encrypts a plaintext message using AES-GCM.
aes_gcm_decrypt(nonce, ciphertext, aes_tag, aes_key): Decrypts the ciphertext if the AES tag is valid.
generate_hmac(ciphertext, hmac_key): Generates an HMAC tag for the ciphertext.
verify_hmac(ciphertext, hmac_key, hmac_tag): Verifies the HMAC tag for the ciphertext.

## Acknowledgments
This implementation uses:

The PyCryptodome library for AES-GCM encryption and HMAC computation.
Cryptographic best practices inspired by PyCryptodome's documentation and standard message authentication protocols.
License
This project is licensed under the MIT License.
