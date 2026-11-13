# NETWORKWALKS-MUJAHID-MUKTAR-B084-WK2-P-CYBERSECURITY-LAB-SETUP
---

## 📄 Penetration Testing Report

**Author:** Mujahid Muktar

**Program:** Network Walks Cybersecurity Internship

**Batch:** B084

**Report Date:** 13 November 2026

### Official Report

📥 [View Full Penetration Testing Report (PDF)](Mujahid_Muktar_Professional_Final_Report_Updated_13_Nov_2026.pdf)

---

*Learn • Practise • Secure • Improve*

🛡️ PENETRATION TESTING REPORT

FOOTPRINTING & RECONNAISSANCE ACTIVITIES

Educational Cybersecurity Project

---

📋 PROJECT INFORMATION

Details| Information
Author / Tester| Mujahid Muktar
Programme| Network Walks Cybersecurity Internship
Batch| B084
Instructor| Waqas Karim
Report Date| 13 November 2026
Evidence Collection Date| 12 November 2026
Target Domain| google.com
Operating Environment| Kali Linux

---

1. DISCLAIMER & AUTHORIZATION

This report documents educational cybersecurity reconnaissance activities.

The activities described are limited to publicly observable information, DNS enumeration, HTTP response inspection, technology fingerprinting and basic host discovery.

Important: No written authorization from Google was provided. This report does not claim that Google authorized security testing.

No exploitation, password attacks, authenticated testing, or unauthorized access to internal systems was performed or demonstrated in the supplied evidence.

Any further testing must be conducted only with explicit written permission from the system owner.

---

2. INTRODUCTION

This project demonstrates practical knowledge of cybersecurity footprinting and reconnaissance using Kali Linux.

The objective was to understand how security professionals collect publicly available information about a domain and interpret basic network and web-server responses.

Seven cybersecurity tools were used:

1. WHOIS
2. WhatWeb
3. Nslookup
4. cURL
5. Wafw00f
6. DNSRecon
7. Nmap / Zenmap

---

3. TOOLS AND THEIR PURPOSES

Tool| Purpose
WHOIS| Domain registration information
WhatWeb| Website technology fingerprinting
Nslookup| DNS resolution
cURL| HTTP response and header inspection
Wafw00f| Generic Web Application Firewall detection
DNSRecon| DNS record enumeration
Nmap / Zenmap| Basic host discovery

---

4. RECONNAISSANCE ACTIVITIES & RESULTS

4.1 WHOIS – Domain Information

Command:

whois google.com

Observations:

- Domain identified as GOOGLE.COM.
- Registrar identified as MarkMonitor Inc.
- Creation date: 15 September 1997.
- Registry expiry date: 14 September 2028.
- Four Google name servers were listed.
- Registrant contact information was redacted.

Assessment: Informational. Public registration information does not establish a security vulnerability.

4.2 WHATWEB – Website Fingerprinting

Command:

whatweb google.com

Results:

- HTTP 301 redirects were observed.
- The www.google.com destination returned HTTP 200 OK.
- Web server identified as "gws".
- HTML5 technology was detected.
- Google page titles were identified.
- Cookie information was observed.
- Multiple IP addresses were returned.

Assessment: The results demonstrate basic website fingerprinting and HTTP response identification.

4.3 NSLOOKUP – DNS Resolution

Command:

nslookup google.com

DNS Server:

8.8.8.8

Results:

IPv4 addresses included:

142.250.129.100
142.250.129.139
142.250.129.101
142.250.129.113
142.250.129.102
142.250.129.138

IPv6 addresses included:

2a00:1450:4009:c15::8a
2a00:1450:4009:c15::65
2a00:1450:4009:c15::64
2a00:1450:4009:c15::8b

Assessment: Multiple IPv4 and IPv6 addresses were successfully resolved.

4.4 cURL – HTTP Header Inspection

Command:

curl -i google.com

Observed response:

HTTP/1.1 301 Moved Permanently
Location: http://www.google.com/
Content-Type: text/html; charset=UTF-8
Server: gws
Cache-Control: public, max-age=2592000
X-Frame-Options: SAMEORIGIN

Observations:

- HTTP 301 response received.
- A redirect location was provided.
- Server information was returned.
- Security-related HTTP headers were observed.
- An HTML redirect response was displayed.

Assessment: The response demonstrates HTTP redirection and header inspection. A redirect is not itself a vulnerability.

4.5 WAFW00F – Firewall Fingerprinting

Command:

wafw00f google.com

Tool Version:

WAFW00F v2.4.2

Result:

Checking https://google.com

Generic Detection Results:

No WAF detected by the generic detection.

Number of requests: 7

Assessment:

The tool did not identify a Web Application Firewall through its generic detection method.

This does not prove that Google has no firewall or other protective security infrastructure.

4.6 DNSRECON – DNS Enumeration

Command:

dnsrecon -d google.com

Results:

DNSRecon successfully enumerated several DNS record categories:

Record| Observation
SOA| ns1.google.com
NS| ns1.google.com through ns4.google.com
MX| smtp.google.com
A| Multiple IPv4 addresses
AAAA| Multiple IPv6 addresses
TXT| Public verification and configuration records
DMARC| Policy identified as p=reject
SRV| LDAP, CalDAVS and CardDAVS records

Additional observation:

ERROR No answer for DNSSEC query for google.com

Final output:

12 Records Found
Completed enumeration for domain: google.com

Assessment:

DNSRecon provided useful information about publicly published DNS records.

The DNSSEC query error alone does not establish a security vulnerability.

4.7 NMAP / ZENMAP – Host Discovery

Tool Version:

Nmap 7.991

Target:

google.com

Observed result:

Nmap scan report for google.com (142.251.208.142)

Host is up.

Other addresses for google.com (not scanned):
2a00:1450:4006:821::200e

rDNS record:
ncmrsb-ao-in-f14.1e100.net

Nmap done:
1 IP address (1 host up) scanned in 0.34 seconds

Assessment:

The selected IPv4 address responded to the basic host-discovery scan.

The scan did not enumerate ports, services, operating systems or vulnerabilities. The additional IPv6 address was not scanned.

---

5. RISK ANALYSIS & FINDINGS

Observation| Assessment| Interpretation
WHOIS information retrieved| Low| Public registration information
Multiple DNS addresses returned| Informational| Normal DNS behaviour
HTTP 301 redirect observed| Informational| Website redirection
Security-related headers observed| Informational| Requires configuration context
WAF not identified| Unconfirmed| Does not prove absence of protection
DNS records enumerated| Informational| Public DNS configuration
Host reported as up| Informational| Confirms reachability at scan time

Overall Finding:

The supplied results did not establish any confirmed security vulnerability.

---

6. SECURITY RECOMMENDATIONS

1. Always obtain written authorization before conducting security testing.
2. Maintain proper documentation of reconnaissance activities.
3. Review DNS configurations regularly on systems you own or are authorized to assess.
4. Follow secure HTTP header configuration practices.
5. Do not assume that a WAF is absent based on one fingerprinting result.
6. Preserve screenshots, timestamps and command outputs.
7. Perform additional vulnerability assessments only within an explicitly authorized environment.

---

7. CONCLUSION

This educational project provided practical experience with seven cybersecurity tools in Kali Linux.

The exercise covered domain information gathering, website fingerprinting, DNS resolution, HTTP response inspection, WAF fingerprinting, DNS enumeration and basic host discovery.

The results improved my understanding of how cybersecurity professionals collect and interpret publicly observable information during the reconnaissance phase.

No confirmed vulnerability was identified in the supplied results.

This project represents an important step in my cybersecurity learning journey and practical development.

---

8. SCREENSHOT EVIDENCE

The following evidence was collected and included in the updated project report:

No.| Evidence| Tool
1| Domain registration lookup| WHOIS
2| Website fingerprinting| WhatWeb
3| DNS resolution| Nslookup
4| HTTP response inspection| cURL
5| Firewall fingerprinting| Wafw00f
6| DNS enumeration – Part 1| DNSRecon
7| DNS enumeration – Part 2| DNSRecon
8| Network topology| Zenmap
9| Host discovery output| Nmap / Zenmap

---

9. SKILLS DEVELOPED

Through this project, I gained practical experience in:

- Linux command-line operations.
- Domain reconnaissance.
- DNS fundamentals and enumeration.
- Website technology identification.
- HTTP response analysis.
- Firewall fingerprinting concepts.
- Basic network host discovery.
- Cybersecurity documentation.
- Ethical hacking principles.

---

10. PROJECT INFORMATION

Project Title: Footprinting & Reconnaissance Activities

Author: Mujahid Muktar

Programme: Network Walks Cybersecurity Internship

Batch: B084

Instructor: Waqas Karim

Report Date: 13 November 2026

Environment: Kali Linux

---
screenshots
