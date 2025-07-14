# Activity Overview

## Security Risk Assessment Report

Following a major data breach, a social media organization has uncovered four critical network vulnerabilities. This report analyzes those issues and proposes key hardening tools and methods to strengthen the organization’s security posture and prevent future incidents.

---
## My Contributions
### Part 1: Recommended Hardening Tools & Methods

#### Tools
- **Multi-Factor Authentication (MFA):**  
  Requires two or more verification methods (e.g., passwords, fingerprints, OTPs), adding depth to identity validation.

- **Password Policies:**  
  Enforce complexity, uniqueness, rotation schedules (e.g., every 90 days), and lockout thresholds to deter brute force attacks.

- **Firewall Maintenance:**  
  Regular rule reviews and traffic filtering prevent unauthorized access and block suspicious activity.

#### Methods
- **Security Information and Event Management (SIEM):**  
  Monitors network-wide activity for anomalies and supports incident response. Enables daily inspection and analysis of logs.

- **Operating System (OS) Hardening:**  
  Applies secure configuration settings, reduces attack surfaces, and enforces access control across hosts.

- **Network Hardening:**  
  Includes port filtering, encryption standards, and access privilege management to secure traffic and limit unauthorized exposure.

### Part 2: Justification of Recommendations

- **MFA** reduces attack surface by requiring more than just a password, which helps block brute force and minimizes internal misuse.
- **Password Policies** address multiple vulnerabilities: shared credentials, default passwords, and weak login behavior. Regular updates (every 90 days) support secure access.
- **Firewall Maintenance** ensures rules are aligned with evolving threats. Daily monitoring allows the team to act swiftly when network behavior deviates.
- **SIEM tools** give visibility into unusual patterns, allowing analysts to inspect incidents in real time and trace breach timelines.
- **OS Hardening** builds a foundation of security by eliminating default settings and tightening administrative controls.
- **Network Hardening** reinforces perimeter defense by restricting traffic and protecting encrypted channels.

---

## Screenshot — Home Asset Inventory Overview
![Home Asset Inventory](images/home-asset-inventory
