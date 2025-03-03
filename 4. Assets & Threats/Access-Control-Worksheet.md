# Access Control Incident Report

## Scenario
On **April 12, 2024**, the finance department at **BrightStone Financial** noticed irregular activity in the payroll system. A routine security audit revealed that an administrator account belonging to a **former contractor** had accessed sensitive financial data. Upon further investigation, security logs showed that the login originated from an **unrecognized IP address (152.207.255.255)**, and the user role was listed as **Legal/Administrator**—even though the individual’s contract had ended **two years prior**.

This incident highlights a **failure in access control policies**, specifically in **account deactivation** and **authorization management**.

---

## Incident Findings

| **Category**            | **Details**               |
|------------------------|-------------------------|
| **Event Date**         | April 12, 2024          |
| **User Role**          | Legal/Administrator     |
| **IP Address**         | 152.207.255.255         |
| **Account Status**     | Active, despite contract termination in 2022 |
| **Unauthorized Access** | Former contractor accessed payroll system without authorization |

---

## Issues Identified

| **Issue** | **Description** |
|-----------|---------------|
| **Expired Credentials Not Revoked** | The user, **Robert Taylor Jr**, was an **administrator** whose contract ended in **2022**, yet his account remained active in **2024**. |
| **Unauthorized Payroll Access** | The former contractor accessed **financial records** without a valid business purpose. |

---

## Recommendations

| **Recommendation** | **Action** |
|--------------------|------------|
| **Automatic Account Expiration** | Implement a policy where **contractor accounts** automatically expire **30 days after contract termination**. |
| **Role-Based Access Control (RBAC)** | Ensure that **non-permanent employees** have **limited access** to critical business systems. |
| **Multi-Factor Authentication (MFA)** | Enforce **MFA for all admin-level accounts** to add an extra layer of security. |
| **Regular Access Reviews** | Conduct **quarterly audits** of user accounts to remove **inactive or unauthorized users**. |

---

By implementing these **preventative measures**, BrightStone Financial can **reduce the risk** of unauthorized access, **protect sensitive data**, and ensure compliance with industry security standards.
