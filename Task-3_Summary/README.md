Task-2 — Reconnaissance & Information Gathering (OSINT Based Assessment)

Objective:
The purpose of this task was to perform passive intelligence gathering on a selected domain using publicly available tools. This phase helps reveal domain ownership, DNS records, subdomains, SSL information, and server behaviors without directly exploiting the target.

Target Domain:
wikipedia.org

Tools Utilized:
• whois
• dig
• host
• nslookup
• subfinder
• amass
• curl
• openssl

Testing Procedure:

1) Domain Ownership & Registration Lookup
Tool Used: whois
Purpose:
To identify registrar, organization, creation/expiry dates, and domain protection status.
Important Findings:
• Registrar: MarkMonitor Inc.
• Status: ClientTransferProhibited
• Nameservers identified
Screenshot: Screenshots/whois_output.png


2) DNS Enumeration
Tool Used: dig
Purpose:
To retrieve DNS records and analyze how the domain resolves to IP addresses.
Observations:
• A and AAAA records available
• Authority section displayed
Screenshot: Screenshots/dig_output.png


3) DNS Resolution Verification
Tool Used: host
Purpose:
To verify IPv4 and IPv6 addresses, and check for MX records if present.
Screenshot: Screenshots/host_output.png


4) Forward DNS Resolution Testing
Tool Used: nslookup
Purpose:
To validate resolution responses from default DNS servers and verify consistency.
Screenshot: Screenshots/nslookup_output.png


5) Subdomain Enumeration (Passive)
Tool Used: subfinder
Purpose:
To gather publicly visible subdomains without active brute forcing.
Outcome:
Multiple country/language-based subdomains were discovered.
Screenshot: Screenshots/subfinder_output.png


6) Extended Subdomain Enumeration
Tool Used: amass enum
Purpose:
To expand reconnaissance surface using OSINT sources and internet data feeds.
Notes:
Wikipedia ecosystem maintains numerous regional subdomains.
Screenshot: Screenshots/amass_output.png


7) Server Header & Protocol Inspection
Tool Used: curl -I
Purpose:
To identify HTTP response behavior, redirection rules, and header security.
Important Observations:
• Wikipedia enforces HTTPS
• Strict Transport Security (HSTS) enabled
• Multiple redirections present
Screenshot: Screenshots/curl_headers.png


8) SSL/TLS Certificate Inspection
Tool Used: openssl (certificate extraction)
Purpose:
To analyze certificate validity, issuer, signing algorithm, and SAN fields.
Certificate Details Observed:
• Issuer: Let’s Encrypt
• Signature Algorithm: ECDSA SHA-384
• Validity & Expiry present
Screenshot: Screenshots/openssl_cert.png


Findings Summary:
• Strong DNS infrastructure with IPv4 & IPv6 support
• HTTPS enforced with HSTS and secure headers
• Certificate security implemented properly
• Subdomain ecosystem large and distributed
• No direct vulnerabilities identified in passive phase
• Recon confirmed large-scale global infrastructure

Key Takeaways:
• Passive reconnaissance reveals valuable information without exploitation
• Subdomain enumeration improves attack surface understanding
• Certificate inspection is useful for assessing security posture
• Wikipedia maintains strong defense & hardened infrastructure
• Recon is a mandatory step before any active testing phase

Conclusion:
Task-2 demonstrated how passive reconnaissance can reveal technical information about a target including DNS structure, SSL certificates, redirection behavior, and organizational footprint. The target in this case maintains strong security practices with proper HTTPS enforcement and HSTS implementation, making it secure against basic attack attempts at this phase.

Evidence Location:
All screenshots for Task-2 are stored in:
Task-2_Reconnaissance/Screenshots/

