# Activity Overview

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of one client reported that they were not able to access the client company's website, `www.yummyrecipesforme.com`, and saw the error “destination port unreachable” after waiting for the page to load.

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. You attempt to visit the website and receive the same error. To troubleshoot, you load your network analyzer tool, `tcpdump`, and reload the page. Your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the domain name—this is part of the DNS protocol. Then, your browser uses that IP address to send an HTTPS request to the web server to display the webpage. The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: **“udp port 53 unreachable.”**

---

## Screenshot of tcpdump Output  
![DNS Log Screenshot](screenshots/dns-tcpdump-log.png)  
> This log data captured from `tcpdump` supports the error investigation. It shows outbound DNS queries via UDP and incoming ICMP responses that confirm DNS traffic failure on port 53.

![15](https://github.com/user-attachments/assets/5774eb91-1463-4934-9dbf-1287a3c5d0c8)

---

## Network Layer Communication — Cybersecurity Incident Report

This report investigates a DNS resolution issue where traffic to port 53 failed, resulting in ICMP error messages. The analysis uses `tcpdump` to identify protocol behavior and provide incident insights.

## My Contributions

#### Part 1: Summary of the Problem in the DNS and ICMP Traffic Log

During the investigation of a reported website accessibility issue, the tcpdump network analysis revealed a consistent pattern of DNS resolution failures. The client’s browser attempted to query the DNS server using the UDP protocol on port 53, which is standard for DNS operations. However, instead of receiving proper DNS responses, the system returned repeated ICMP error messages, specifically stating “UDP port 53 unreachable.” These errors indicate that the DNS service associated with that port was either not responding, misconfigured, or blocked. The log data supported this conclusion by showing valid UDP queries initiated by the client and ICMP responses returned with error flags. The presence of the DNS record request flag “A?” further confirms that the client was trying to map a domain to an IP address as expected. Altogether, these findings suggest an issue on the receiving DNS server’s end, not with the client’s outbound request.



#### Part 2: Analysis of the Data and Possible Cause of the Incident

The incident was reported at 1:24 p.m., when several customers experienced an error message: “destination port unreachable” while attempting to access the website `yummyrecipesforme.com`. To understand the cause, the IT team replicated the error and launched a packet capture using tcpdump. The captured traffic showed that the browser sent a DNS query using UDP to retrieve the IP address for the website domain. Instead of a successful response, the system received ICMP packets with the error message “UDP port 53 unreachable.” This indicated that traffic to the DNS server was being rejected or not answered. The most likely explanation is that the DNS server was experiencing service interruption—either due to a misconfiguration, an outage, or possibly a Denial of Service (DoS) attack targeting port 53. Further investigation should focus on verifying whether the DNS service is operational and whether firewall rules or external threats are affecting connectivity.

---

## Screenshot of Completed Report  
![DNS Incident Report Screenshot](screenshots/dns-icmp-report.png)  
> This image captures the full response submitted as part of the Google Cybersecurity Certificate incident report activity.

<img width="584" height="777" alt="16" src="https://github.com/user-attachments/assets/acf239a3-32a1-4f85-85cd-906750f25e97" />
