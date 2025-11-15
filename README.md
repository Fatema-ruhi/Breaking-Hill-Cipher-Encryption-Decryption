## Breaking Hill Cipher Encryption/Decryption Using Linear Algebra
A cryptanalysis project demonstrating vulnerabilities in the classical Hill Cipher and its modified variants using known plaintext attacks and linear algebra techniques.
### Overview
The Hill Cipher is a polygraphic substitution cipher invented by Lester S. Hill in 1929. While it was innovative for its time, utilizing linear algebra and modular arithmetic, this project demonstrates its fundamental vulnerability to known plaintext attacks due to its linearity property.
### Project Goals
Implement classical Hill Cipher encryption and decryption
Demonstrate known plaintext attack to recover encryption keys
Analyze the security of two modified Hill Cipher variants
Investigate whether modified methods can resist cryptanalytic attacks
### Key Findings
#### Classical Hill Cipher Vulnerability:
The cipher encrypts identical plaintext blocks to identical ciphertext blocks
Once attackers know plaintext-ciphertext pairs, the key can be recovered through matrix operations
The linearity property makes it susceptible to known plaintext attacks
#### Modified Variants Analysis:
Hill Cipher with XOR and Radix64 Encoding - Still vulnerable as the first three steps can be reversed without the key
Hill Cipher with Circulant Matrices - Marginally better but still breakable due to inherent linearity
### Conclusion
Hill Cipher cryptography remains fundamentally insecure regardless of modifications, as long as the linearity property persists.
