# Activity Overview
You are a cybersecurity analyst for yummyrecipesforme.com, a website that sells recipes and cookbooks. A former employee has decided to lure users to a fake website with malware.

The former employee/hacker executed a brute force attack to gain access to the web host. They repeatedly entered several known default passwords for the administrative account until they correctly guessed the right one. After they obtained the login credentials, they were able to access the admin panel and change the website’s source code. They embedded a JavaScript function in the source code that prompted visitors to download and run a file upon visiting the website. After embedding the malware, the hacker changed the password to the administrative account. When customers download the file, they are redirected to a fake version of the website that contains the malware.

Several hours after the attack, multiple customers emailed yummyrecipesforme’s helpdesk. They complained that the company’s website had prompted them to download a file to access free recipes. The customers claimed that, after running the file, the address of the website changed and their personal computers began running more slowly.

In response to this incident, the website owner tries to log in to the admin panel but is unable to, so they reach out to the website hosting provider. You and other cybersecurity analysts are tasked with investigating this security event.

To address the incident, you create a sandbox environment to observe the suspicious website behavior. You run the network protocol analyzer tcpdump, then type in the URL for the website, yummyrecipesforme.com. As soon as the website loads, you are prompted to download an executable file to update your browser. You accept the download and allow the file to run. You then observe that your browser redirects you to a different URL, greatrecipesforme.com, which contains the malware.

---

## Packet Capture Summary
The logs show the following process:

The browser initiates a DNS request: It requests the IP address of the yummyrecipesforme.com URL from the DNS server.

The DNS replies with the correct IP address.

The browser initiates an HTTP request: It requests the yummyrecipesforme.com webpage using the IP address sent by the DNS server.

The browser initiates the download of the malware.

The browser initiates a DNS request for greatrecipesforme.com..

The DNS server responds with the IP address for greatrecipesforme.com..

The browser initiates an HTTP request to the IP address for greatrecipesforme.com..

---

## Analyst Notes
A senior analyst confirms that the website was compromised. The analyst checks the source code for the website and notices that JavaScript code had been added to prompt website visitors to download an executable file. Analysis of the downloaded file found a script that redirects the visitors’ browsers from yummyrecipesforme.com to greatrecipesforme.com..

The cybersecurity team reports that the web server was impacted by a brute force attack. The disgruntled hacker was able to guess the password easily because the admin password was still set to the default password. Additionally, there were no controls in place to prevent a brute force attack.

Your job is to document the incident in detail, identify the network protocols used to establish the connection between the user and the website, and recommend one security action to help prevent brute force attacks in the future

---

## OS Hardening Techniques — Security Incident Report 
## My Contributions

#### Section 1: Identify the Network Protocol Involved in the Incident
The network protocols involved in the incident are DNS (Domain Name System) and HTTP (Hypertext Transfer Protocol). Both operate at the application layer of the TCP/IP model. DNS was used to resolve domain names (yummyrecipesforme.com and greatrecipesforme.com) into IP addresses, while HTTP was used to transmit the web content—including the malicious file download and redirection.

- The tcpdump traffic log confirms these actions:

- DNS requests and replies for both domains

- HTTP requests made to retrieve website data and deliver the malicious file

- A redirection to a fake website via an HTTP GET request

- These protocols played a key role in enabling the attack and confirming how the web traffic was manipulated.

#### Section 2: Document the Incident
Several customers reported suspicious behavior after visiting yummyrecipesforme.com. They described being prompted to download a file offering free recipes, which redirected their browser to greatrecipesforme.com. After running the file, their devices began to slow down—indicating malware infection. The website owner attempted to access the admin panel to investigate but was locked out of the account.

A cybersecurity analyst launched an investigation in a sandboxed environment to safely reproduce the behavior. The analyst ran tcpdump to capture network traffic and visited the affected website. Upon loading, the site prompted a download of an executable file, which was accepted and executed. The browser then issued a new DNS request for greatrecipesforme.com, followed by an HTTP connection to the malicious site.

The analyst reviewed the tcpdump log, confirming DNS resolution and HTTP traffic for both domains. These patterns matched the scenario described by users and highlighted how the attacker had embedded JavaScript to prompt file downloads and redirect browser activity.

Further investigation by the security team and senior analyst revealed that the attacker had gained access through a brute force attack, exploiting a default administrative password. Once inside, they altered the site’s source code to initiate malicious downloads and redirection, leading to compromised user systems and denial of access for the website owner.

#### Section 3: Recommend One Remediation for Brute Force Attacks
To defend against brute force attacks like the one used in this incident, the organization should implement a strong password policy. This policy should enforce:

- Minimum password complexity and length (e.g., 15 characters or more)

- Restrictions on reusing previous passwords, including default credentials

- Periodic password updates

- A limit on the number of login attempts before account lockout

- Combined with two-factor authentication (2FA), these measures would significantly reduce the risk of unauthorized access. Enforcing such controls is a critical step toward OS hardening, helping prevent future compromises and securing administrative access points.

---

## Screenshot of Completed Report  
![os-hardening-report.png](screenshots/os-hardening-report.png)  

> This image captures the full response submitted as part of the Google Cybersecurity Certificate incident report activity.

<img width="573" height="785" alt="19" src="https://github.com/user-attachments/assets/a989d593-67a5-40aa-bec2-4bb9dd709c50" />

<img width="594" height="774" alt="20" src="https://github.com/user-attachments/assets/9accffb8-dee4-4c14-8ab1-60de4f466997" />

<img width="580" height="836" alt="21" src="https://github.com/user-attachments/assets/f7a69a43-a75a-4eef-91c9-679a51ba1335" />
