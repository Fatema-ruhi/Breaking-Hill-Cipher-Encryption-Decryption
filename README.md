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
### Algorithm:
#### Classical Hill Cipher Encryption:
C = (K × P) mod 26
Where,
C = Ciphertext matrix
K = Key matrix (must be invertible mod 26)
P = Plaintext matrix
Operations performed modulo 26 (for alphabet)
#### Decryption:
P = (K⁻¹ × C) mod 26
Where K⁻¹ is the modular multiplicative inverse of K.
Known Plaintext Attack
Given plaintext-ciphertext pairs:
#### Organize Data:
Create plaintext matrix P with linearly independent columns
Create corresponding ciphertext matrix C
#### Solve for Key:
   C = K × P (mod 26)
   C × P⁻¹ = K (mod 26)
#### Verify:
Test the recovered key on additional plaintext-ciphertext pairs
Check if decryption produces correct plaintext
#### Example: SpongeBob SquarePants Theme Song
The project includes a complete demonstration using the SpongeBob SquarePants theme song lyrics as plaintext to show how the known plaintext attack successfully recovers encryption keys.
### Technical Details
#### Matrix Requirements
Key matrix must be invertible in modulo 26
Determinant must be coprime with 26 (gcd(det(K), 26) = 1)
For attack: plaintext columns must be linearly independent
#### Modular Arithmetic
All operations performed in Z₂₆ (integers modulo 26)
Uses extended Euclidean algorithm for modular inverse computation
Matrix inversion follows standard linear algebra with modular constraints
### Mathematical Foundation
The security weakness stems from the encryption being a linear transformation:
E(aP₁ + bP₂) = aE(P₁) + bE(P₂)
This linearity allows attackers to:
Set up systems of linear equations from known plaintext-ciphertext pairs
Solve for the key matrix using standard linear algebra
Bypass the intended security without brute force
### Security Implications
This project demonstrates why:
Hill Cipher should NOT be used for real-world encryption
Linear encryption schemes are fundamentally vulnerable
Modern cryptography requires non-linear transformations
Kerckhoffs's Principle: "Security should depend solely on the secrecy of the key, not the algorithm"

### References
1. Jessie Paragas, Ariel M. Sison, Ruji Medina, "Hill Cipher Modification: A Simplified Approach", 2019 IEEE 11th International Conference on Communication Software and Networks (ICCSN)
2. K. Adinarayana Reddy, B. Vishnuvardhan, Madhuviswanatham, A.V.N. Krishna, "A Modified Hill Cipher Based on Circulant Matrices", ELSEVIER, Volume 4, 2012, Pages 114-118
3. Hill Cipher - Wikipedia
4. Kerckhoffs's Principle

#### Author
Fatema Yesmen Ruhi, 
MA 545 Linear Algebra Project, 
Date: April 29, 2022
##### License
This project is for educational purposes only. See LICENSE file for details
