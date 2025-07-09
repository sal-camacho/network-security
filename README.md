# 🛡️ NIST CSF-Based Security Incident Report Analysis — ICMP DDoS Attack
As part of the Google Cybersecurity Course, this report analyzes a network security incident using the NIST Cybersecurity Framework (CSF). The framework is used to guide response and improvement across five key domains: Identify, Protect, Detect, Respond, and Recover.

## 📝 Summary
The organization experienced a Distributed Denial of Service (DDoS) attack that disrupted internal network services for approximately two hours. A malicious actor exploited an unconfigured firewall by flooding the network with ICMP packets, overwhelming traffic flow. The incident management team responded by blocking the attack and prioritizing the restoration of critical services.

## 🔍 Identify
The organization was targeted by an ICMP flood—an attack that impacted the entire internal network and halted normal operations. The compromised firewall allowed unauthorized packets to enter, creating a vulnerability that disrupted essential business functions.

## 🔐 Protect
The network security team implemented multiple controls to prevent future incidents:
- Added a firewall rule to limit ICMP packet rate
- Enabled source IP verification to detect spoofed addresses
- Deployed an IDS/IPS system to filter suspicious ICMP traffic
- Installed network monitoring software to track abnormal behavior

## 📡 Detect
To improve threat detection:
- Network traffic is now monitored using an IDS and logging tools
- Firewall rules log suspicious packet sources
- Abnormal traffic patterns are tracked for analysis. These measures help catch external threats earlier and support faster response times.


## ⚠️ Respond
If future attacks occur, the team will:
- Immediately isolate affected devices and services
- Analyze network logs for indicators of compromise
- Use SIEM tools to monitor and correlate events
- Report incidents to management and legal teams as required

## 🔁 Recover
Recovery efforts focused on restoring access to essential services. Going forward:
- Firewalls will be regularly updated
- OS hardening techniques will be applied to strengthen system configurations
- A phased restoration plan prioritizes critical services first, followed by non-critical systems once traffic normalizes

## 💡 Reflections / Notes
This incident highlighted the importance of firewall configuration, early detection, and procedural coordination during an attack. Going forward, audits and continuous monitoring will play a key role in maintaining resilience.

![Incident Report Example](incident-report-example.png)
> Screenshot of completed incident report analysis following NIST CSF guidelines.
![13](https://github.com/user-attachments/assets/5ac97519-7424-4189-9563-10c5fa1780bf)
![14](https://github.com/user-attachments/assets/84f89b6e-2086-4ed9-a16b-474f868bf158)
