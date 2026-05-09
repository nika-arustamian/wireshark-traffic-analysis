Wireshark Traffic Analysis Labs
Overview

This repository contains practical Wireshark labs focused on network traffic analysis, protocol inspection, and identifying insecure data transmission.

The goal of these exercises was to practice:

Capturing live network traffic
Analyzing HTTP and SMTP protocols
Identifying background network activity
Extracting transmitted credentials from intercepted traffic
Lab 1 — Capturing Unencrypted HTTP Traffic
Objective

Capture and analyze unencrypted HTTP traffic in Wireshark.

Actions Performed
Started Wireshark capture on the Wi-Fi interface
Opened an insecure HTTP website (http://neverssl.com)
Inspected HTTP packets and request headers
Findings

The captured traffic contained readable HTTP requests including:

GET / HTTP/1.1
Host
User-Agent
Accept

This demonstrates how unencrypted HTTP traffic can expose sensitive information in plaintext.

Screenshot

<img width="1204" height="1004" alt="1" src="https://github.com/user-attachments/assets/1cea0767-982f-48a4-a379-bde2c4009770" />


Lab 2 — SMTP Traffic Analysis
Objective

Analyze SMTP traffic and inspect email communication commands.

Actions Performed
Generated SMTP traffic using a local SMTP testing setup
Captured packets in Wireshark
Followed the TCP stream to inspect the full SMTP conversation
Findings

The following SMTP commands were identified:

HELO
MAIL FROM
RCPT TO
DATA

The email content was also visible in plaintext.

This demonstrates how insecure or unencrypted email communication may expose message contents and metadata.

Screenshot

<img width="1766" height="748" alt="2" src="https://github.com/user-attachments/assets/baed5645-e8d3-4c98-ab18-1f979cd7fbaa" />


Lab 3 — Detecting Unexpected Network Activity
Objective

Inspect network traffic to identify background or potentially suspicious activity.

Actions Performed
Captured live network traffic
Analyzed TLS and QUIC connections
Reviewed destination domains and protocols
Findings

The analysis revealed multiple background connections including:

Google services
Grammarly
Opera telemetry traffic

Observed protocols:

TLSv1.2
TLSv1.3
QUIC

No malicious activity was identified, but the exercise demonstrated how modern applications continuously generate background network traffic.

Screenshot

<img width="1268" height="1004" alt="3" src="https://github.com/user-attachments/assets/8fadb22d-197d-4bcf-b9ab-a9ea76285ae1" />


Lab 4 — Extracting Credentials from Captured Traffic
Objective

Identify transmitted login credentials in captured network traffic.

Actions Performed
Visited http://testphp.vulnweb.com
Submitted login credentials
Captured POST request traffic
Inspected HTTP form data
Findings

The intercepted request contained readable credentials:

uid = admin
passw = admin

This demonstrates the security risks of transmitting authentication data over insecure or improperly protected connections.

Screenshot

<img width="1475" height="1004" alt="4" src="https://github.com/user-attachments/assets/4bd9493f-a9c4-4a63-9e6b-57387a64bc8b" />


Tools Used
Wireshark
macOS
Local SMTP test server
HTTP test environments
Skills Practiced
Packet capture
HTTP analysis
SMTP inspection
TCP stream analysis
TLS traffic observation
Credential extraction
Network monitoring
Disclaimer

All activities were performed in controlled lab environments for educational and ethical cybersecurity training purposes only.
