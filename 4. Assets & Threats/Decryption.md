# Decryption Task: Recovering Encrypted Files

## Scenario
Your home directory has been compromised, and all critical files have been encrypted. Your objective is to decrypt them using Linux commands.

Here’s the process:
1. **Explore the directory** and examine any available files.
2. **Locate hidden files** and decipher the encrypted text using the **Caesar cipher**.
3. **Decrypt a fully encrypted file** to restore its contents.

---

## Solution

### Step 1: Inspect the Home Directory
Start by listing all available files in your home directory:
```bash
ls /home/analyst
```
Look for a README file that may contain clues. To read its contents:
```bash
cat README.txt
```
The README file suggests checking the **"cipher"** subdirectory for hidden files.

---

### Step 2: Locate and Decrypt a Hidden File
Navigate to the **cipher** directory and list all files, including hidden ones:
```bash
cd cipher
ls -a
```
You’ll notice a hidden file, **".shiftLeft3"**, which contains scrambled text encrypted using a **Caesar cipher** (shift of 3). To view its contents:
```bash
cat .shiftLeft3
```
The text appears unreadable. The Caesar cipher works by shifting letters left or right. In this case, each letter has been shifted **three places to the left** (e.g., **D → A, E → B**).

To decrypt the text, use the **tr** (translate) command:
```bash
cat .shiftLeft3 | tr "d-za-cD-ZA-C" "a-zA-Z"
```
This restores the original text, revealing a hidden message.

---

### Step 3: Decrypt an Encrypted File
Return to the **home directory** and attempt to decrypt a fully encrypted file:
```bash
cd /home/analyst
openssl aes-256-cbc -pbkdf2 -a -d -in encrypted_file.enc -out decrypted_file.txt -k securepass123
```
**Explanation of the command:**
- **`openssl aes-256-cbc`** → Uses AES-256-CBC encryption.
- **`-pbkdf2`** → Enhances security using key derivation.
- **`-a -d`** → `-a` ensures base64 encoding, `-d` means decrypt.
- **`-in`** → Specifies the encrypted input file.
- **`-out`** → Specifies the decrypted output file.
- **`-k securepass123`** → The decryption password (you would normally retrieve this securely).

Verify the decrypted file by listing its contents:
```bash
ls
cat decrypted_file.txt
```

---

## Conclusion
By following these steps, you successfully:
✅ Identified hidden encrypted files.  
✅ Deciphered a **Caesar cipher** manually.  
✅ Used **OpenSSL** to decrypt sensitive files.

This process demonstrates fundamental cryptographic techniques and security practices in Linux.
