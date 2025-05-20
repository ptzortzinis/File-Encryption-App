# File-Encryption-App
This is a Python application for file encryption, decryption, and password management. It supports both authenticated encryption using AES-GCM and integrity-only protection using HMAC-SHA256.

Encryption Options
You can choose between two security goals: full encryption with integrity (AES-GCM) or integrity-only protection (HMAC). AES-GCM uses a random nonce for every encryption and supports optional key rotation on file access.

Security Levels
Three security levels are available: low (AES-128, 50,000 iterations), medium (AES-256, 100,000 iterations), and high (AES-256, 200,000 iterations). These affect the key length and PBKDF2 iteration count.

Key Derivation
Passwords are strengthened using PBKDF2 with SHA-256, salt, and configurable iteration counts. This helps defend against brute-force attacks and ensures key uniqueness.

Output Files
Each encryption generates two files: the encrypted file (filename.ext.enc) and a metadata file (filename.ext.enc.meta) that stores cryptographic parameters like salt, nonce, and iteration count.

Decryption and Verification
The app automatically detects the encryption mode from the metadata and decrypts or verifies the file accordingly. AES-GCM decrypts the data, while HMAC checks the file’s integrity.

Password Change
Passwords can be changed securely without exposing the original data. The file is verified using the old password and re-protected with the new one, including new salt and metadata.

Requirements
Python 3.6 or newer is required. Install the cryptography library with:

pip install cryptography  
