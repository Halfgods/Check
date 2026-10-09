For a very brief theory of Shift Ciphers and their analysis, click [here](docs/shiftcipher.pdf) (source: vlab page).

The **Shift Cipher**, also known as the **Caesar Cipher**, is one of the oldest and simplest encryption techniques. It is named after Julius Caesar, who reportedly used it to protect military communications by shifting each letter of a message by a fixed number of positions in the alphabet.

The Shift Cipher is a **monoalphabetic substitution cipher**, meaning that every occurrence of a particular plaintext letter is replaced by the same ciphertext letter throughout the message. Although the Shift Cipher is no longer considered secure for modern communication, it provides an excellent introduction to the fundamental concepts of cryptography, including encryption, decryption, secret keys, key space, modular arithmetic, and cryptanalysis.

### How It Works

The Shift Cipher replaces every alphabetic character in the plaintext with another character obtained by shifting it by a fixed number of positions in the alphabet.

1. **Key Space**

   The secret key is an integer shift value. For the English alphabet, the key can take values from **0** to **25**. Since a shift of **0** leaves the plaintext unchanged, there are **25 effective encryption keys**.

2. **Encryption**

   Each plaintext letter is shifted forward by the key value. Example for **Key = 3**:

   ```
   Plaintext : ABCDEFGHIJKLMNOPQRSTUVWXYZ
   Ciphertext: DEFGHIJKLMNOPQRSTUVWXYZABC
   ```

3. **Decryption**

   Each ciphertext letter is shifted backward by the same key value to recover the original plaintext.

   Example:

   ```
   Ciphertext : KHOOR
   Key        : 3
   Plaintext  : HELLO
   ```

### Mathematical Representation

The Shift Cipher operates on the numerical representation of alphabetic characters.

Assign A=0, B=1, ..., Z=25.

Let:

- P = plaintext character
- C = ciphertext character
- k = secret shift key

Then encryption is performed as:

C = (P + k) mod 26

and decryption is:

P = (C - k) mod 26

where the modulo operation ensures that the alphabet wraps around after **Z**.

**Example**

Encrypt the letter **H** using **k = 3**:

H = 7

C = (7 + 3) mod 26 = 10

which corresponds to the letter **K**.

Similarly,

P = (10 - 3) mod 26 = 7

recovering **H**.

### Security Analysis

The security of an encryption algorithm depends largely on the difficulty of recovering the secret key or plaintext without authorization. The Shift Cipher has several important weaknesses.

1. **Small Key Space**

   For the English alphabet, there are only **25 effective encryption keys**. An attacker can try every possible key within a very short time, making exhaustive key search computationally trivial.

2. **Vulnerable to Brute Force Attack**

   Since every possible key can be tested, the correct plaintext is guaranteed to be found after at most **25 attempts**. The computational complexity of exhaustive key search is O(n), where n is the number of possible keys.

3. **Preserves Letter Frequencies**

   The Shift Cipher changes only the position of letters and does not alter their frequency distribution. Consequently, commonly occurring English letters such as:

   ```
   E, T, A, O, I, N
   ```

   remain the most frequent letters in the ciphertext, although shifted. This property makes the cipher highly vulnerable to statistical analysis.

### Breaking the Cipher

The Shift Cipher can be broken using several cryptanalytic techniques.

1. **Brute Force Attack**

   Every possible key is tried until meaningful plaintext is obtained. Since there are only 25 effective keys, this method always succeeds within a small number of attempts.

2. **Frequency Analysis**

   Natural languages exhibit predictable letter-frequency distributions. By comparing the frequency of letters in the ciphertext with standard English letter frequencies, an attacker can estimate the shift value and recover the plaintext. Frequency analysis becomes more effective as the ciphertext length increases because the observed frequencies more closely resemble the natural language distribution.

3. **Known Plaintext Attack**

   If an attacker knows even one plaintext letter and its corresponding ciphertext letter, the secret shift value can be computed directly. Once the key is known, the entire ciphertext can be decrypted immediately.

---

Although the Shift Cipher is cryptographically insecure, it remains one of the most important educational examples in classical cryptography. It introduces fundamental concepts such as substitution ciphers, secret keys, modular arithmetic, key space, and cryptanalysis, which form the basis for understanding more advanced encryption algorithms. Modern cryptographic systems such as AES employ significantly larger key spaces and more sophisticated mathematical transformations, making them resistant to brute-force and statistical attacks that easily compromise the Shift Cipher.


![cat diagram](images/cat1.png)
![cat square](images/cat2.jpg)
![cat tall](images/cat3.jpg)
