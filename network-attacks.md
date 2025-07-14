# Activity Overview

You are a security analyst working at a travel agency that advertises promotions on its website. Employees access the site daily to search vacation packages for clients. One afternoon, your monitoring system detects an issue with the web server. You try to visit the website but encounter a connection timeout error.

After using a packet sniffer to examine traffic, you observe a high volume of TCP SYN requests originating from an unfamiliar IP address. The server is overwhelmed and unable to respond properly, indicating a potential attack. You take the server offline to stabilize it and block the source IP via the firewall. However, you know the attacker can spoof other IPs. You must now report this incident, explain what type of attack occurred, how it impacted the organization, and suggest ways to prevent future attacks.

---

## Wireshark Log Snippet
The following data was captured using a packet sniffer tool and illustrates network activity leading to the service disruption. Notable patterns include repeated TCP SYN requests from 203.0.113.0 to port 443, indicating the likely presence of a TCP SYN flood attack.
| No. | Time      | Source         | Destination   | Protocol | Info                                   |
|-----|-----------|----------------|---------------|----------|----------------------------------------|
| 47  | 3.144521  | 198.51.100.23  | 192.0.2.1     | TCP      | 42584->443 [SYN] Seq=0 Win=5792 Len=120 |
| 48  | 3.195755  | 192.0.2.1      | 198.51.100.23 | TCP      | 443->42584 [SYN, ACK] Seq=0 Win=5792 Len=120 |
| 49  | 3.246989  | 198.51.100.23  | 192.0.2.1     | TCP      | 42584->443 [ACK] Seq=1 Win=5792 Len=120 |
| 50  | 3.298223  | 198.51.100.23  | 192.0.2.1     | HTTP     | GET /sales.html HTTP/1.1               |
| 51  | 3.349457  | 192.0.2.1      | 198.51.100.23 | HTTP     | HTTP/1.1 200 OK (text/html)            |
| 52  | 3.390692  | 203.0.113.0    | 192.0.2.1     | TCP      | 54770->443 [SYN] Seq=0 Win=5792 Len=0   |
| 53  | 3.441926  | 192.0.2.1      | 203.0.113.0   | TCP      | 443->54770 [SYN, ACK] Seq=0 Win=5792 Len=120 |
| 54  | 3.493160  | 203.0.113.0    | 192.0.2.1     | TCP      | 54770->443 [ACK] Seq=1 Win=5792 Len=0   |
| 55  | 3.544394  | 198.51.100.14  | 192.0.2.1     | TCP      | 14785->443 [SYN] Seq=0 Win=5792 Len=120 |

## Screenshot of Wireshark TCP/HTTP log
![SYN Flood Screenshot](screenshots/syn-flood-log.png)
> Captured SYN flood activity in Wireshark, showing repeated TCP SYN packets from attacker IP 203.0.113.0 targeting port 443

![17](https://github.com/user-attachments/assets/2b058a90-fd0a-4713-b2fd-d26b663d6d55)

---

## Syn Flood Incident Report — Cybersecurity Incident Report

## My Contributions

#### Section 1: Attack Identification

The symptoms and traffic patterns observed in this incident are consistent with a **TCP SYN Flood attack**, a type of **Denial of Service (DoS)**. In a SYN flood, the attacker sends a large number of SYN (synchronization) requests to initiate a TCP handshake without completing it. The target server allocates resources to these half-open connections, leading to resource exhaustion and unresponsiveness. The unfamiliar IP generating massive SYN requests overwhelmed the server, making it unable to respond to legitimate traffic.

The connection timeout experienced by employees and customers is a direct result of the server being saturated with incomplete TCP requests. This type of attack does not require the attacker to compromise the server itself—just flooding it with traffic is enough to temporarily disrupt availability. If executed across many IPs simultaneously, the attack can evolve into a **Distributed Denial of Service (DDoS)**.

#### Section 2: Impact and Prevention

This SYN flood significantly disrupted the organization’s operations. Employees were unable to access the promotional web page used to service clients, and potential customers may have perceived the company as unreliable due to the outage. Downtime affects user trust, operational continuity, and can lead to financial losses.

The attacker exploited the TCP protocol by exploiting open connections, overwhelming the server’s connection queue. While blocking the originating IP helped temporarily, attackers often rotate or spoof IP addresses to circumvent firewalls.

To mitigate future threats, the organization should:
- Configure **SYN cookies** on the server to resist incomplete TCP handshakes
- Use intrusion prevention systems (IPS)** to detect anomalies
- Consider implementing a **Web Application Firewall (WAF)** or a **DDoS protection service** to absorb malicious traffic
- Monitor connection logs more proactively and simulate attacks for resilience testing

---

## Screenshot of Completed Report  
![SYN Flood Screenshot](screenshots/syn-flood-log.png)
> This image captures the full response submitted as part of the Google Cybersecurity Certificate incident report activity.
<img width="581" height="777" alt="18" src="https://github.com/user-attachments/assets/f3a6e4d6-6d9e-4687-970d-da55636a3d01" />
