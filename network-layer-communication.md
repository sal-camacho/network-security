## 🧠 Cybersecurity Incident Report: DNS and ICMP Traffic Analysis
# 🔍 Part 1: Summary of the Problem in the tcpdump Log
Network analysis revealed an issue in the DNS resolution process. A DNS query was sent via the UDP protocol to port 53 on the DNS server, but it failed. The system responded with repeated ICMP error messages: “UDP port 53 unreachable.” This means the DNS server was either down, misconfigured, or blocking traffic on that port. Since port 53 is reserved for DNS service, its unavailability prevented the browser from resolving the domain name yummyrecipesforme.com. The presence of flags in the UDP packet—such as the query identification number and “A?” DNS record request—indicates the client was functioning properly, but no valid response was returned. The DNS service on the receiving end was likely unreachable at the time of the request.

# 🛠️ Part 2: Data Analysis and Likely Cause of the Incident
The incident occurred at 1:24 p.m., as seen in the tcpdump timestamp. Several customers of the client company reported that they couldn’t access the website and saw the error: “destination port unreachable.” To investigate, the IT team attempted to replicate the issue, confirmed the same error, and initiated packet capture using tcpdump. During analysis, they saw that the client machine sent UDP packets to the DNS server to retrieve the site’s IP address—but received ICMP error responses indicating that UDP port 53 was not reachable. This port is critical for DNS communication.

The investigation suggests that the DNS server’s port 53 was either:

Blocked by firewall rules

Misconfigured

Experiencing a DNS service outage

Or affected by a denial-of-service (DoS) attack preventing normal operation

To resolve the issue, the next step is to confirm whether DNS services are running correctly and that firewall rules allow traffic on port 53. Depending on those findings, further mitigation might include restarting DNS services, adjusting access controls, or implementing protections against DoS threats.
