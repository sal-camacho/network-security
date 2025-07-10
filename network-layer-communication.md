## 🧠 DNS and ICMP Traffic Analysis — Cybersecurity Incident Report

This report investigates a DNS resolution issue where traffic to port 53 failed, resulting in ICMP error messages. The analysis uses `tcpdump` to identify protocol behavior and provide incident insights.

---

### 📝 Written Summary

#### 🔍 Part 1: Summary of the Problem in the DNS and ICMP Traffic Log

During the investigation of a reported website accessibility issue, the tcpdump network analysis revealed a consistent pattern of DNS resolution failures. The client’s browser attempted to query the DNS server using the UDP protocol on port 53, which is standard for DNS operations. However, instead of receiving proper DNS responses, the system returned repeated ICMP error messages, specifically stating “UDP port 53 unreachable.” These errors indicate that the DNS service associated with that port was either not responding, misconfigured, or blocked. The log data supported this conclusion by showing valid UDP queries initiated by the client and ICMP responses returned with error flags. The presence of the DNS record request flag “A?” further confirms that the client was trying to map a domain to an IP address as expected. Altogether, these findings suggest an issue on the receiving DNS server’s end, not with the client’s outbound request.

---

#### 🛠️ Part 2: Analysis of the Data and Possible Cause of the Incident

The incident was reported at 1:24 p.m., when several customers experienced an error message: “destination port unreachable” while attempting to access the website `yummyrecipesforme.com`. To understand the cause, the IT team replicated the error and launched a packet capture using tcpdump. The captured traffic showed that the browser sent a DNS query using UDP to retrieve the IP address for the website domain. Instead of a successful response, the system received ICMP packets with the error message “UDP port 53 unreachable.” This indicated that traffic to the DNS server was being rejected or not answered. The most likely explanation is that the DNS server was experiencing service interruption—either due to a misconfiguration, an outage, or possibly a Denial of Service (DoS) attack targeting port 53. Further investigation should focus on verifying whether the DNS service is operational and whether firewall rules or external threats are affecting connectivity.

### 📸 Screenshot of Completed Report  
![DNS Incident Report Screenshot](screenshots/dns-icmp-report.png)  
> This image captures the full response submitted as part of the Google Cybersecurity Certificate incident report activity.
![15](https://github.com/user-attachments/assets/3c5fa83b-7c9c-4088-bc29-942d02aa406b)
