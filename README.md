# Lab-Exercise---7---Implement-DES-Encryption-and-Decryption
## Aim
To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## Procedure
1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program
```from Crypto.Cipher import DES
from Crypto.Util.Padding import pad, unpad

key = b'12345678' # DES key must be 8 bytes
cipher = DES.new(key, DES.MODE_ECB)

text = b"HelloDES!" # bytes

# PKCS7 padding to 8-byte DES block
padded_text = pad(text, 8)

encrypted = cipher.encrypt(padded_text)

# decrypt
decrypted_padded = cipher.decrypt(encrypted)
decrypted = unpad(decrypted_padded, 8)

print("Original:", text)
print("Encrypted:", encrypted)
print("Decrypted:", decrypted)
```
## Output
<img width="1617" height="907" alt="Screenshot 2026-11-21 143139" src="https://github.com/user-attachments/assets/538c1016-0811-4371-9e88-bcf4ff1c487f" />

## Result
The program run successfully.
