### **Compare Hash Values**

#### **Description**  
As a cybersecurity analyst, verifying **file integrity** is crucial in detecting **tampering, corruption, or malicious modifications**. One way to achieve this is through **hashing**, which generates a **unique identifier (hash value or digest)** for a file.  

Even a **single character change** in a file results in a **completely different hash**, making it an effective method to detect **unauthorized modifications or disguised malware**.  

For example, an attacker could **alter a legitimate software update** to include **malicious code**. By comparing hash values before and after transmission, security teams can confirm whether a file has been altered.  

---

### **Generating Hashes**  
First, list the files in a directory using the `ls` command. We will compare **two text files** to verify their integrity.  

```bash
ls
file1.txt  file2.txt
```

Next, we display the contents of both files to visually inspect them:  

```bash
cat file1.txt  
Hello, this is a test file.  

cat file2.txt  
Hello, this is a test file.  
```

At first glance, both files appear **identical**. However, to confirm whether they are truly the same, we **generate hash values** using SHA-256.  

```bash
sha256sum file1.txt  
a3f5e21b6d8c9f3e76b8d5d8cfd2a1b6db5b3a3c5e7d6f8e9c1b2d3f4a5b6c7d  file1.txt  

sha256sum file2.txt  
b9d7e6c3a5f4b2d1c8f7e6a3d5c4b2a1e9d8c7f6b5a4d3c2e1f0a9b8d7c6e5f  file2.txt  
```

The **different hash values confirm** that the two files are **not identical**, despite appearing the same.  

---

### **Comparing Hashes in Stored Files**  
To automate integrity verification, we can **store hash values** in separate files and compare them later.  

1. Generate and save the hashes:  

```bash
sha256sum file1.txt > file1hash.txt  
sha256sum file2.txt > file2hash.txt  
```

2. View the stored hash values:  

```bash
cat file1hash.txt  
a3f5e21b6d8c9f3e76b8d5d8cfd2a1b6db5b3a3c5e7d6f8e9c1b2d3f4a5b6c7d  file1.txt  

cat file2hash.txt  
b9d7e6c3a5f4b2d1c8f7e6a3d5c4b2a1e9d8c7f6b5a4d3c2e1f0a9b8d7c6e5f  file2.txt  
```

3. Use the `cmp` command to directly compare files:  

```bash
cmp file1.txt file2.txt  
file1.txt file2.txt differ: byte 17, line 1  
```

---

### **Summary**  
Even if two files **look identical**, their **hash values** provide an **unbiased verification method** to detect changes. Security teams use hashing techniques to:  

✅ **Detect unauthorized file modifications**  
✅ **Validate software authenticity** before installation  
✅ **Identify malware disguised as legitimate software**  
✅ **Ensure secure data transmission** over networks  

Regularly checking file hashes is a **best practice** in cybersecurity, ensuring **data integrity and authenticity** across systems.
