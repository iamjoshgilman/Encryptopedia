---
creation date: August 26th 2023
last modified date: August 26th 2023
aliases: []
tags: #📖
---

Primary Categories: [[000 - Global Index]] 
Secondary Categories: [[02 - Foundations]] 
Links: [[Encryption Algorithms]] [[Data Integrity]] [[Authentication Methods]] 
Search Tag: #📖  

# [[03 - Encryption]]  

___
# Overview

Encryption is the technique of converting data into an unreadable format to prevent unauthorized access. The main purpose is to ensure the confidentiality of data, ensuring that only intended recipients can interpret the information.
## Key Capabilities

1. **Authentication:** Verifies the origin of the message for the recipient.
2. **Integrity:** Provides proof that the content of the message hasn't been altered post-transmission.
3. **Non-repudiation:** Ensures that the sender can't deny sending the message.
## Essential Components for Encryption

To encrypt data:
1. **Unencrypted Data:** The original data you aim to encrypt.
2. **Encryption Key:** A special key that will be employed for encryption.
3. **Encryption Algorithm:** A mathematical function that uses the unencrypted data and the key to produce encrypted data.

For decryption, the requirements are similar:
1. **Encrypted Data:** The scrambled data.
2. **Decryption Key:** A key to revert the encrypted data to its original form.
3. **Encryption Algorithm:** The specific mathematical function used in the encryption process.
## Strong Encryption

Good encryption algorithms are public, transparent, and have endured and passed scrutiny from top mathematicians. Depending solely on algorithm secrecy is a sign of weak encryption. Time-tested algorithms with no discovered flaws are the most trustworthy.

**Recommendation:** Avoid older encryption methods like DES, which can be deciphered using modern computing power due to its limited key size.
## Breaking Encryption

There are two primary approaches to breaching encryption:
1. **Flaw Exploitation:** Identifying and exploiting vulnerabilities in the encryption algorithm. It's uncommon for mature algorithms to have unaddressed flaws.
2. **Key Guessing:** Attempting to determine the encryption key. This approach is effective only with outdated algorithms like DES, which have a small encryption key size. For instance, DES, from the 1970s, had a maximum key size of 56 bits, making it vulnerable to brute-force attacks on modern computers.

---
# Symmetric Encryption Study Notes

## Definition

**Symmetric Encryption** is a method where the same key is used for both encrypting and decrypting data.
## Historical Context

- **Caesar Cipher**: An ancient form of symmetric encryption used by Romans.
  - **Working**: Letters in a message are shifted by a specific number of places.
  - **Key**: The number by which letters are shifted.
  - **Example**: 
    - **Plaintext**: "Caesar Cipher in action"
    - **Key**: 8
    - **Encrypted**: "Kimaiz Kqxpmz qv ikbqwv"
    - **Decrypted**: Shift the letters 8 places left to retrieve "Caesar Cipher in action".
  - **Flaw**: Only 26 possible shifts, making it easily breakable today.
## Modern Symmetric Encryption

- **AES (Advanced Encryption Standard)**:
  - Prominent modern symmetric encryption algorithm.
  - Supports keys of sizes: 128, 192, or 256 bits.
  - **Key Size Significance**:
    - A 256-bit key has \(2^{256}\) or \(1.1579 \times 10^{77}\) possible combinations. This is an astronomically large number, providing immense security.
  - **Encryption Speed**:
    - A balance between speed and security is crucial. Encryption shouldn't be so slow that it's impractical, but if decryption is too fast, brute force attacks become feasible.

---
# Hashing
## Definition

**Hashing** is a one-way encryption technique where data is transformed into a fixed-size value, known as a hash. This technique is irreversible, meaning one cannot retrieve the original data from the hash.
## Key Properties

1. **Deterministic**: Same input will always produce the same hash.
2. **High Sensitivity**: A minuscule change in input will result in a vastly different hash.
3. **Uniqueness**: Different inputs should not produce the same hash. When this does happen, it's called a "collision".
4. **Fixed Length**: Regardless of input size, the hash size remains consistent.
## Applications

1. **Data Integrity**:
    - Verifying if files are identical by comparing their hashes.
    - In computer forensics, ensuring evidence remains unaltered.
  
2. **Password Storage**:
    - Storing password hashes instead of plain text passwords for security.
    - During login, a user's input is hashed and matched against stored hash.
## Common Hashing Algorithms

- **MD5**: Older and now considered broken due to vulnerabilities.
- **SHA1**: A successor to MD5, also considered broken and insecure.
- **SHA2, SHA3**: Modern, more secure hashing algorithms.
- **SHA256, SHA512**: Variants specifying the bit-length of the hash.
## Philosophical Note

Given the constraints of hash algorithms, it's possible (though statistically improbable with good algorithms) for two different inputs to produce the same hash (a **collision**). This is especially conceivable when considering a large dataset being represented by a significantly smaller hash value. While rare, these collisions can affect use cases where unique representation is crucial.



___

## Resources:

| Hyperlink | Info |
| --------- | ---- |


Created Date: August 26th 2023 (01:36 pm) 
Last Modified Date: August 26th 2023 (01:36 pm)
