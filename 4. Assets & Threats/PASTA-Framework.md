# PASTA Framework: Threat Modeling for Sneaker Marketplace App  

## Process of Attack Simulation and Threat Analysis  

### Scenario  
As part of the security team at **SneakVault**, a growing online sneaker marketplace, you have been tasked with performing a **threat model assessment** for the company’s new **mobile app**. The app will allow sneaker enthusiasts to **buy, sell, and trade** limited-edition sneakers.  

To ensure **secure transactions and data protection**, you will use the **PASTA (Process for Attack Simulation and Threat Analysis) framework** to identify potential threats and vulnerabilities before launch.  

---

## PASTA Framework Components  
The PASTA framework consists of **seven structured stages** to evaluate and mitigate risks:  

1. **Define Business & Security Objectives**  
2. **Define the Technical Scope**  
3. **Decompose the Application (Data Flow Diagram)**  
4. **Threat Analysis**  
5. **Vulnerability Analysis**  
6. **Attack Modeling (Attack Tree)**  
7. **Risk Analysis & Impact Assessment**  

---

## Implementation of PASTA Framework  

### 1. Define Business & Security Objectives  

| **Business Goals** | **Security Objectives** |  
|--------------------|------------------------|  
| Enable secure sneaker transactions | Implement one account per user, one payment method per transaction |  
| Allow users to create personal profiles | Require Multi-Factor Authentication (MFA) for account access |  
| Support multiple payment options | Ensure PCI-DSS compliance for payment security |  
| Manage sneaker listings and inventory | Encrypt user data to prevent unauthorized access |  
| Facilitate customer inquiries and seller interactions | Implement strict access control policies |  

#### Context Diagram  

- **Users**: Browse, purchase, and list sneakers for sale  
- **Admins**: Manage catalog, approve listings, monitor transactions  
- **Payment Gateway**: Processes transactions securely  
- **Support Team**: Handles customer inquiries  

---

### 2. Define the Technical Scope  
The app’s technical architecture must ensure **secure data exchange** and **transaction processing**. Key components include:  

- **RESTful API** for communication between users, database, and payment processor  
- **Public Key Infrastructure (PKI)** for secure authentication and data encryption  
- **SHA-256 Hashing** to protect sensitive data such as passwords  
- **Secure SQL Queries** to prevent injection attacks  

---

### 3. Decompose the Application  
A **Data Flow Diagram (DFD) Level 0 (Context Diagram)** is used to visualize how data moves through the system.  

- **User actions**: Register, login, browse sneakers, purchase items  
- **Payment processing**: Secure API calls to verify transactions  
- **Admin actions**: Manage inventory, resolve disputes  
- **Data storage**: Customer profiles, order history, payment details  

---

### 4. Threat Analysis  
Potential threats that could impact app security include:  

- **SQL Injection** – Malicious actors inserting SQL commands to manipulate the database  
- **Session Hijacking** – Attackers stealing session tokens to impersonate users  
- **Denial-of-Service (DoS) Attacks** – Overloading servers to disrupt availability  
- **Man-in-the-Middle (MITM) Attacks** – Intercepting unencrypted data during transactions  

---

### 5. Vulnerability Analysis  
Common vulnerabilities that need mitigation:  

| **Vulnerability** | **Potential Risk** | **Mitigation Strategy** |  
|------------------|-------------------|------------------------|  
| **Unsecured API Endpoints** | Data exposure due to weak authentication | Require API key authentication & OAuth 2.0 |  
| **Weak Credential Management** | Brute-force attacks on user accounts | Enforce strong password policies & MFA |  
| **Lack of Prepared SQL Statements** | Susceptibility to SQL Injection | Use parameterized queries & ORM frameworks |  
| **Broken API Tokens** | Unauthorized API access | Implement token expiration & refresh mechanisms |  

---

### 6. Attack Modeling (Attack Tree)  

#### Example: SQL Injection Attack Tree  

**Goal**: **Gain unauthorized access to the database**  

- **Step 1**: Identify input fields vulnerable to SQL injection  
  - **Step 1.1**: Locate login page or search bar  
  - **Step 1.2**: Insert malicious SQL payload (`' OR '1'='1' --`)  
- **Step 2**: Exploit vulnerable query execution  
  - **Step 2.1**: Retrieve user credentials from the database  
  - **Step 2.2**: Gain unauthorized admin access  
- **Step 3**: Modify or extract sensitive data  

---

### 7. Risk Analysis & Impact Assessment  

To reduce risks, **security best practices** and **countermeasures** should be implemented:  

- **Use SHA-256 Hashing** to protect stored passwords and sensitive user data  
- **Implement Incident Response Procedures** to mitigate data breaches  
- **Develop a Security Playbook** to standardize security practices  
- **Enforce Strong Password Policies** to prevent credential stuffing attacks  
- **Apply the Principle of Least Privilege (PoLP)** to restrict user access  
- **Adopt a Zero-Trust Security Model** to verify all access attempts  

---

## Conclusion  
The **PASTA framework** provides a **comprehensive method** for identifying and mitigating **security risks** in **SneakVault's** mobile app. By following **structured threat modeling**, implementing **secure coding practices**, and enforcing **strict access controls**, the company can launch a secure and reliable platform for sneaker enthusiasts.
