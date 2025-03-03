### **Data Leak Worksheet**  

#### **Incident Summary**  
A **financial analyst** at a major investment firm prepared a confidential report detailing upcoming stock recommendations, merger strategies, and internal revenue projections. The analyst uploaded the report to a shared **cloud storage folder** used by their team.  

During a virtual meeting, a junior team member accessed the report and, in an attempt to share specific insights with a client, **mistakenly attached the entire confidential document to an email instead of a summary file**. The client, assuming the information was public, forwarded it to multiple investors. Within hours, **fragments of the report were circulating on financial news forums**, potentially affecting stock market movements and violating compliance regulations.  

#### **Control Implemented: Least Privilege**  

| **Issue(s)** | **Details** |
|-------------|------------|
| **Overexposed access** | The shared folder contained **sensitive financial projections**, but access was not restricted to senior staff only. |
| **Unrestricted sharing** | The junior employee had **full access** to confidential reports and **could share without restrictions**. |
| **Lack of file expiration controls** | The confidential document remained accessible indefinitely instead of having an **auto-expiration policy**. |
| **No external recipient restrictions** | Email systems did not have **DLP (Data Loss Prevention) policies** in place to prevent external sharing of sensitive data. |

#### **Review: NIST SP 800-53 AC-6**  
NIST SP 800-53 **AC-6** outlines **least privilege** as a best practice for protecting sensitive data. It recommends **limiting access** based on user roles and enforcing **security controls** to prevent accidental exposure.  

#### **Recommendation(s)**  

1. **Enforce Role-Based Access Control (RBAC)**  
   - Restrict **highly sensitive files** to senior financial analysts and compliance officers.  
   - Require **manager approval** for access requests.  

2. **Implement File Access Expiration & DLP Policies**  
   - Set **auto-expiration** for access links after a defined period.  
   - Configure **Data Loss Prevention (DLP) rules** to block unauthorized email sharing of financial reports.  

3. **Enable External Sharing Restrictions**  
   - Prevent users from sharing confidential documents with **external recipients** unless explicitly authorized.  
   - Deploy **email filtering rules** to scan attachments for sensitive financial keywords.  

4. **Mandatory Security Awareness Training**  
   - Educate employees on **handling sensitive data** and **consequences of unintentional leaks**.  
   - Conduct **simulated phishing and data leak exercises**.  

#### **Justification**  
Applying **least privilege** and **automated security controls** reduces the risk of **accidental data leaks**. Restricting access, enforcing expiration policies, and deploying **Data Loss Prevention (DLP) measures** ensure sensitive financial documents remain protected from **unauthorized sharing and regulatory violations**.  

#### **Reference: NIST Cybersecurity Framework (CSF)**  

| **Function** | **Category** | **Subcategory** | **Reference** |
|-------------|-------------|----------------|--------------|
| **Protect** | **PR.DS: Data Security** | **PR.DS-5: Protections against data leaks** | **NIST SP 800-53: AC-6** |

NIST SP 800-53 provides a **comprehensive framework** for protecting sensitive information, enforcing **least privilege**, and implementing **advanced security controls** to prevent **unauthorized data exposure**.  

By implementing these measures, organizations can **mitigate financial data breaches** and ensure **regulatory compliance with industry standards**.
