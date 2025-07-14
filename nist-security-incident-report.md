# Activity Overview
You are a cybersecurity analyst working for a multimedia company that offers web design services, graphic design, and social media marketing solutions to small businesses. Your organization recently experienced a DDoS attack, which compromised the internal network for two hours until it was resolved.

During the attack, your organization’s network services suddenly stopped responding due to an incoming flood of ICMP packets. Normal internal network traffic could not access any network resources. The incident management team responded by blocking incoming ICMP packets, stopping all non-critical network services offline, and restoring critical network services. 

The company’s cybersecurity team then investigated the security event. They found that a malicious actor had sent a flood of ICMP pings into the company’s network through an unconfigured firewall. This vulnerability allowed the malicious attacker to overwhelm the company’s network through a distributed denial of service (DDoS) attack. 

To address this security event, the network security team implemented: 

A new firewall rule to limit the rate of incoming ICMP packets

Source IP address verification on the firewall to check for spoofed IP addresses on incoming ICMP packets

Network monitoring software to detect abnormal traffic patterns

An IDS/IPS system to filter out some ICMP traffic based on suspicious characteristics

As a cybersecurity analyst, you are tasked with using this security event to create a plan to improve your company’s network security, following the National Institute of Standards and Technology (NIST) Cybersecurity Framework (CSF). You will use the CSF to help you navigate through the different steps of analyzing this cybersecurity event and integrate your analysis into a general security strategy.

---

NIST Security —
## My Contributions
### Summary
The organization experienced a Distributed Denial of Service (DDoS) attack that disrupted internal network services for approximately two hours. A malicious actor exploited an unconfigured firewall by flooding the network with ICMP packets, overwhelming traffic flow. The incident management team responded by blocking the attack and prioritizing the restoration of critical services.

### Identify
The organization was targeted by an ICMP flood—an attack that impacted the entire internal network and halted normal operations. The compromised firewall allowed unauthorized packets to enter, creating a vulnerability that disrupted essential business functions.

### Protect
The network security team implemented multiple controls to prevent future incidents:
- Added a firewall rule to limit ICMP packet rate
- Enabled source IP verification to detect spoofed addresses
- Deployed an IDS/IPS system to filter suspicious ICMP traffic
- Installed network monitoring software to track abnormal behavior

### Detect
To improve threat detection:
- Network traffic is now monitored using an IDS and logging tools
- Firewall rules log suspicious packet sources
- Abnormal traffic patterns are tracked for analysis. These measures help catch external threats earlier and support faster response times.


### Respond
If future attacks occur, the team will:
- Immediately isolate affected devices and services
- Analyze network logs for indicators of compromise
- Use SIEM tools to monitor and correlate events
- Report incidents to management and legal teams as required

### Recover
Recovery efforts focused on restoring access to essential services. Going forward:
- Firewalls will be regularly updated
- OS hardening techniques will be applied to strengthen system configurations
- A phased restoration plan prioritizes critical services first, followed by non-critical systems once traffic normalizes

### Reflections / Notes
This incident highlighted the importance of firewall configuration, early detection, and procedural coordination during an attack. Going forward, audits and continuous monitoring will play a key role in maintaining resilience.

---
## Screenshot of Completed Report
![Incident Report Example](incident-report-example.png)
> This image captures the full response submitted as part of the Google Cybersecurity Certificate incident report activity.

![13](https://github.com/user-attachments/assets/5ac97519-7424-4189-9563-10c5fa1780bf)
![14](https://github.com/user-attachments/assets/84f89b6e-2086-4ed9-a16b-474f868bf158)
