# Conduct a Security Audit  
## Case Study  

### **Company Overview**  
**ShieldTech Solutions** is a fast-growing cybersecurity consulting firm that provides security solutions to small and medium-sized enterprises (SMEs). Recently, **Zentra Electronics**, an international electronics retailer, hired ShieldTech Solutions to conduct an internal security audit.  

Zentra Electronics operates both physical stores and a large e-commerce platform. With increasing cyber threats, the company’s **IT security team is concerned about potential vulnerabilities** in their network, compliance gaps, and overall security posture.  

ShieldTech Solutions was brought in to **assess Zentra Electronics' cybersecurity framework, identify risks, and recommend mitigation strategies** to ensure compliance with industry standards such as **NIST CSF, PCI DSS, and GDPR**.  

---

## **Audit Scope, Goals, and Risk Assessment**  

### **Scope**  
The audit will cover:  
- IT infrastructure (on-premises and cloud)  
- Network security, including firewalls and access controls  
- Employee devices (laptops, workstations, mobile devices)  
- E-commerce website security  
- Data protection and compliance policies  
- Incident detection and response mechanisms  

### **Goals**  
- Identify security gaps in Zentra Electronics’ infrastructure  
- Evaluate compliance with NIST CSF, PCI DSS, and GDPR  
- Assess risk levels and prioritize security improvements  
- Provide a detailed security audit report with recommendations  

---

## **Current Assets & Risk Assessment**  

### **Assets Under Review**  
- **Network Infrastructure**: Firewalls, VPN, IDS/IPS, routers  
- **Cloud Services**: AWS-hosted applications, storage solutions  
- **Employee Devices**: Workstations, smartphones, remote access tools  
- **Customer Data**: Payment processing systems, databases  
- **Security Tools**: SIEM (Splunk), endpoint detection (CrowdStrike)  

### **Risk Assessment**  

#### **Identified Risks**  
- **Lack of Proper Access Controls**: Some employees have **excessive privileges**, increasing the risk of insider threats.  
- **Weak Password Policies**: Passwords do not meet complexity requirements, making accounts vulnerable to brute force attacks.  
- **Unencrypted Sensitive Data**: Customer credit card information is stored **without encryption**, violating PCI DSS compliance.  
- **Outdated Software & Patch Management**: Several critical systems have **unpatched vulnerabilities**.  
- **Insufficient Monitoring & Logging**: Security events are **not logged effectively**, making it harder to detect threats.  

#### **Risk Score (1-10 Scale)**  
- **Overall Risk Score: 8 (High)**  
- **Potential Impact:** Data breaches, compliance violations, financial penalties  

---

## **Controls Assessment Checklist**  

| Control | Status | Explanation |  
|---------|--------|------------|  
| Least Privilege | ❌ No | Employees have unnecessary access to sensitive data. |  
| Multi-Factor Authentication (MFA) | ✅ Yes | Enabled for some accounts, but not enforced organization-wide. |  
| Disaster Recovery Plan | ❌ No | No clear strategy for handling cyber incidents. |  
| Firewalls | ✅ Yes | Network firewalls are in place but require rule updates. |  
| Endpoint Security (EDR) | ✅ Yes | Active on company devices using CrowdStrike. |  
| Intrusion Detection System (IDS) | ❌ No | No IDS in place to detect network threats. |  
| Encryption (Data at Rest) | ❌ No | Customer payment data is stored without encryption. |  
| Regular Security Audits | ❌ No | Last audit was conducted more than a year ago. |  

---

## **Compliance Checklist**  

| Compliance Standard | Status | Explanation |  
|---------------------|--------|------------|  
| **NIST Cybersecurity Framework (CSF)** | ⚠️ Partial | Implemented but lacks consistent risk management processes. |  
| **Payment Card Industry Data Security Standard (PCI DSS)** | ❌ No | Customer credit card information is **not encrypted**. |  
| **General Data Protection Regulation (GDPR)** | ❌ No | EU customer data **not handled according to GDPR requirements**. |  
| **System & Organization Controls (SOC 2)** | ❌ No | No formal policies for access control and data security. |  

---

## **Recommendations & Mitigation Strategies**  

To improve Zentra Electronics’ security posture, ShieldTech Solutions recommends:  

### **1. Implement Strong Access Controls**  
- Apply the **principle of least privilege (PoLP)**.  
- Restrict access to sensitive customer data **only to authorized personnel**.  

### **2. Enforce Multi-Factor Authentication (MFA)**  
- **Require MFA** for all employees accessing critical systems.  
- Implement **hardware security keys for administrators**.  

### **3. Encrypt Sensitive Data**  
- Use **AES-256 encryption** for customer payment data.  
- Ensure **SSL/TLS is enforced** for all web transactions.  

### **4. Strengthen Network Security**  
- Deploy an **Intrusion Detection System (IDS)** (e.g., Suricata).  
- **Regularly update firewall rules** to block suspicious traffic.  

### **5. Improve Threat Detection & Response**  
- Configure **SIEM (Splunk, Chronicle)** for centralized logging.  
- Automate security incident detection using **Python scripts**.  

### **6. Conduct Regular Security Audits**  
- Schedule audits **every 6 months** to identify emerging risks.  
- Perform **penetration testing** to validate security controls.  

---

## **Conclusion**  

The security audit of **Zentra Electronics** identified key vulnerabilities that pose a high risk to the organization’s data and compliance. By implementing **enhanced security controls, proper encryption, and better threat detection mechanisms**, the company can significantly improve its cybersecurity resilience and regulatory compliance.  

This report serves as a baseline for **ongoing security improvements** and highlights the importance of continuous monitoring and proactive threat management.  

---

### **Author:**  
**Folajimi Adeyemi** | Cybersecurity Analyst
