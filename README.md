# PENETRATION TESTING REPORT

## INFORMATION GATHERING, FOOTPRINTING & NETWORK SCANNING

W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS

| Particulars       | Details                                                                     |
| ----------------- | --------------------------------------------------------------------------- |
| Pentester Name    | Vruti prajapati                                                             |
| Program/Batch     | B084                                                                        |
| Date              | 12 November 2026                                                            |
| Internship        | Cyber Security Internship                                                   |
| Modules Completed | Information Gathering and Reconnaissance                                    |
| Operating System  | Kali Linux and Windows                                                      |
| Tools Used        | WHOIS, WhatWeb, NSLookup, cURL, WAFW00F, DNSRecon, TheHarvester and Nmap    |
| Phases Covered    | Phase 1: Reconnaissance and Footprinting; Phase 2: Network Discovery        |

## 1. Liability Disclaimer

I have performed these activities for educational and cybersecurity learning purposes. All scanning and testing activities must be conducted only on systems, devices, domains, and networks that I own or for which I have received proper authorization.

The information in this report is intended for learning and research purposes only. Unauthorized access, scanning, or misuse of information may violate applicable laws. The author, instructor, and Networkwalks are not responsible for any misuse of the information presented in this report.

## 2. Introduction

This report covers the practical activities performed during Week 2 of my Cyber Security Internship at Networkwalks.

The main objective of this practical was to understand information gathering, footprinting, DNS enumeration, website technology identification, and network discovery using different cybersecurity tools.

I used Kali Linux to perform reconnaissance activities against the Networkwalks domain and practiced TheHarvester with Microsoft domain information. I also used Windows CMD to check network configuration and Nmap to discover active hosts in a private lab network.

These activities helped me understand how cybersecurity professionals collect information about domains, websites, and networks during the initial stages of a security assessment.

## 3. Tools Used

The following tools were used during the practical activities.

| Tool         | Purpose                                            |
| ------------ | -------------------------------------------------- |
| Kali Linux   | Operating system used for cybersecurity practicals |
| WHOIS        | Collect domain registration information            |
| WhatWeb      | Identify website technologies                      |
| NSLookup     | Resolve domain names into IP addresses             |
| cURL         | Inspect HTTP response headers                      |
| WAFW00F      | Identify Web Application Firewalls                 |
| DNSRecon     | Collect DNS records                                |
| TheHarvester | Collect publicly available information             |
| Nmap         | Discover active hosts on a network                 |
| Windows CMD  | Check local network configuration                  |

## 4. Activities Performed

### 4.1 Footprinting and Reconnaissance

I performed domain reconnaissance using different Kali Linux tools. Each tool was used to collect a different type of information about the target domain.

1). WHOIS – Domain Information Gathering

Command:
whois networkwalks.com

I used WHOIS to collect publicly available domain registration information.

The output provided:

- Domain registrar information.
- Domain creation and expiration dates.
- Name server information.
- Domain status details.
- DNSSEC status.

This activity helped me understand how domain registration information can be collected.

2). WhatWeb – Website Technology Identification

Command:
whatweb networkwalks.com

I used WhatWeb to identify the technologies used by the website.

The results identified:

- Apache web server.
- WordPress CMS.
- Bootstrap.
- jQuery.
- WordPress Download Manager.

This activity helped me understand how website technologies can be identified during reconnaissance.

3). NSLookup – DNS Resolution

Command:
nslookup networkwalks.com

I used NSLookup to resolve the domain name into its corresponding IP address.

Observation:

The command successfully resolved the domain and returned its IP address.

This helped me understand how DNS translates domain names into IP addresses.

4). cURL – HTTP Header Analysis

Command:
curl -I https://networkwalks.com

I used cURL with the '-I' option to inspect the HTTP response headers.

Observation:

- The website returned an HTTP 200 response.
- Apache server information was visible.
- WordPress-related response headers were identified.
- WordPress REST API information was present in the response.

This activity helped me understand how HTTP headers provide technical information about a web application.

5). WAFW00F – Firewall Detection

Command:
wafw00f networkwalks.com

I used WAFW00F to identify whether the website was protected by a Web Application Firewall.

Observation:

The tool detected ModSecurity (SpiderLabs) as the Web Application Firewall.

This helped me understand how WAF detection works during website reconnaissance.

6). DNSRecon – DNS Enumeration

Command:
dnsrecon -d networkwalks.com

I used DNSRecon to collect DNS-related information about the domain.

The results included:

- Name server records.
- Mail exchange records.
- A records.
- TXT records.
- SPF information.
- Service records.

This activity helped me understand how DNS enumeration provides information about domain infrastructure.

### 4.2 Information Gathering Using TheHarvester

I used TheHarvester to collect publicly available information from different search sources.

Commands:

theHarvester -d microsoft.com -l 1000 -b baidu
theHarvester -d microsoft.com -l 50 -b all

TheHarvester was used to identify publicly indexed information associated with the specified domain.

The results included:

- ASN information.
- Interesting URLs.
- IP address information.
- Publicly indexed email addresses.
- Hostnames.

Observation:

The Baidu search did not return IP addresses. The second search collected additional publicly indexed information from available sources.

This activity helped me understand the concept of Open Source Intelligence (OSINT) and how publicly available information can be collected.

### 4.3 Network Configuration Using Windows CMD

Command:

```
ipconfig
```

I used the Windows 'ipconfig' command to check the network configuration of my computer.

The output displayed:

- Network adapter information.
- IPv4 configuration.
- Subnet mask information.
- Default gateway information.

This activity helped me understand how to identify the network configuration of a Windows system.

### 4.4 Network Discovery Using Nmap

Command:

nmap -sn 10.20.186.184/24

I used Nmap with the '-sn' option to perform a ping scan and discover active hosts in the private lab network.

Observation:

The scan identified 2 active hosts out of 256 possible addresses in the scanned subnet.

This activity helped me understand how Nmap performs host discovery without conducting a port scan.

## 5. Risk Analysis / Impact

Based on the information collected during the practical activities, I identified the following potential risks.

| No. | Risk / Finding                             | Evidence / Observation                                 | Potential Impact                                                                  | Risk Level |
| --- | ------------------------------------------ | ------------------------------------------------------ | --------------------------------------------------------------------------------- | ---------- |
| 1   | Website technology information exposed     | WhatWeb identified WordPress and other technologies    | Technology details may help attackers identify software requiring security review | Medium     |
| 2   | Domain information publicly available      | WHOIS displayed registration and name server details   | May help build a profile of the domain infrastructure                             | Low        |
| 3   | Server information exposed                 | NSLookup resolved the domain to an IP address          | Provides information about the web server's network location                      | Low        |
| 4   | HTTP technical information exposed         | cURL displayed HTTP response headers                   | May assist further technology identification                                      | Low        |
| 5   | WAF technology identifiable                | WAFW00F detected ModSecurity                           | Reveals information about the website's security architecture                     | Low        |
| 6   | DNS infrastructure information exposed     | DNSRecon identified DNS, mail and service records      | May help build a broader infrastructure profile                                   | Medium     |
| 7   | Public information available through OSINT | TheHarvester collected indexed host and IP information | Public information may be combined to create a wider target profile               | Medium     |
| 8   | Active hosts discovered                    | Nmap identified two active hosts in the lab network    | Unknown devices may require investigation                                         | Medium     |

Risk level key: Critical / High / Medium / Low.

The above findings are observations from information gathering and network discovery. They are not confirmed vulnerabilities. No exploitation or vulnerability validation was performed as part of these activities.

## 6. Recommendations

Based on the observations, I recommend the following security improvements:

1\. Review Publicly Exposed Website Information

Organizations should regularly review the technical information exposed by their websites.

2\. Keep Website Technologies Updated

CMS platforms, plugins, libraries, and web servers should be updated regularly.

3\. Review HTTP Response Headers

Unnecessary technical information should be reviewed and minimized where appropriate.

4\. Monitor DNS Records

DNS records should be checked regularly to ensure that only required information and services are publicly exposed.

5\. Configure and Monitor the WAF

Web Application Firewalls should be properly configured, updated, and monitored.

6\. Review Publicly Available Information

Organizations should understand what information about their infrastructure is publicly indexed.

7\. Perform Regular Network Discovery

Organizations should periodically scan their own networks to identify active devices.

8\. Investigate Unknown Devices

Unexpected devices discovered during network scanning should be investigated.

9\. Follow Authorized Testing Practices

All reconnaissance and scanning activities should be performed only with proper authorization.

## 7. Conclusion

During Week 2 of my Cyber Security Internship at Networkwalks, I completed practical activities related to information gathering, footprinting, reconnaissance, and network discovery.

I used WHOIS to collect domain registration information, WhatWeb to identify website technologies, NSLookup to resolve domain names, cURL to inspect HTTP response headers, WAFW00F to detect a Web Application Firewall, and DNSRecon to collect DNS records.

I also practiced TheHarvester to understand OSINT techniques, used Windows CMD to check network configuration, and used Nmap to discover active hosts in a private lab network.

These practical activities improved my understanding of reconnaissance and the importance of information gathering in cybersecurity. I also learned how to use different command-line tools and document their results.

Overall, this week's practical experience helped me develop basic hands-on skills in cybersecurity and ethical hacking.

## 8. Evidences Collected

The following screenshots were captured during the practical activities and can be attached to the GitHub repository.

| Screenshot          | Description                               |
| ------------------- | ----------------------------------------- |
| <img width="1920" height="1080" alt="Screenshot (599)" src="https://github.com/user-attachments/assets/8421154a-fff3-4356-a9d8-f3302793cbe3" />      | WHOIS domain information                  |
| <img width="1920" height="1080" alt="Screenshot (601)" src="https://github.com/user-attachments/assets/46a990ff-271f-4112-9cbd-db5e5493af87" />
     | WhatWeb website technology identification |
| <img width="1920" height="1080" alt="Screenshot (602)" src="https://github.com/user-attachments/assets/7cc3cc94-a91c-4537-b6c9-2c9247a4b794" />
     | NSLookup DNS resolution                   |
| <img width="1920" height="1080" alt="Screenshot (603)" src="https://github.com/user-attachments/assets/5768944d-9a83-43b6-8a34-f96cf60da137" />
     | cURL HTTP response headers                |
| <img width="1920" height="1080" alt="Screenshot (604)" src="https://github.com/user-attachments/assets/4372c56e-5e14-48ce-80b5-2604e4c4b473" />
     | WAFW00F firewall detection                |
| <img width="1920" height="1080" alt="Screenshot (605)" src="https://github.com/user-attachments/assets/a9281f77-af21-4dae-b3c6-f3ebe1f5da8a" />
      | DNSRecon DNS enumeration                  |
| <img width="1920" height="1080" alt="Screenshot (607)" src="https://github.com/user-attachments/assets/2f8b2606-37c2-421b-9641-98fc8a6d01f2" />
<img width="1920" height="1080" alt="Screenshot (608)" src="https://github.com/user-attachments/assets/7a1b8ad0-73ef-44da-9456-be6191fbb7a2" />
<img width="1920" height="1080" alt="Screenshot (609)" src="https://github.com/user-attachments/assets/f0c0b07e-d4e8-43f0-a2ea-23431d68c5ab" />
<img width="1920" height="1080" alt="Screenshot (611)" src="https://github.com/user-attachments/assets/8e20f940-a2d3-4c65-92e3-dad57bfc1090" />
| TheHarvester OSINT results                |
| <img width="1920" height="1080" alt="Screenshot (612)" src="https://github.com/user-attachments/assets/24ae2288-8798-4049-8ee8-012d3be364f7" />
     | Windows IP configuration                  |
| <img width="1920" height="1080" alt="Screenshot (613)" src="https://github.com/user-attachments/assets/5b611921-528c-47ef-a1bd-ff107311a2c3" />
<img width="1920" height="1080" alt="Screenshot (614)" src="https://github.com/user-attachments/assets/876ec7fe-7b2f-4651-a14f-0a4de2164197" />
     | Nmap network discovery                    |


— End of Report —

Project Information

- Program Name: Cyber Security Internship
- Organization: Networkwalks
- Week: 02
- Project: Information Gathering and Reconnaissance
- Repository: GitHub
