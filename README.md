# File-Encryption-App

This Python application provides secure file encryption, decryption, and password management using two modes:

AES-GCM (AEAD) for authenticated encryption (confidentiality + integrity)

HMAC-SHA256 for integrity-only protection

🚀 Features
Authenticated Encryption (AES-GCM)

128-bit or 256-bit AES

Nonce-based encryption with optional key rotation

HMAC Integrity Protection

SHA-256 based message authentication

Key Derivation

Uses PBKDF2 with salt and configurable iterations

Key Rotation

Optionally re-encrypts data every time it's accessed

Password Management

Change passwords securely without revealing plaintext

Requirements
Python 3.6+

cryptography module

Install required library:

bash
Copy
Edit
pip install cryptography
Usage
Run the application:

bash
Copy
Edit
python encryptor.py
You'll be prompted to:

Encrypt a file

Choose AES-GCM or HMAC

Select a security level (low, medium, high)

Optional key rotation for AEAD

Decrypt a file

Automatically detects mode from metadata

Change password

Secure re-encryption with new password

Security Levels
Level	Key Size	PBKDF2 Iterations
Low	AES-128	50,000
Medium	AES-256	100,000
High	AES-256	200,000

Output
When encrypting, the program generates:

filename.ext.enc: Encrypted file

filename.ext.enc.meta: JSON metadata containing encryption parameters

