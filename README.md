Advanced Incident Response Investigation & Triage Report

Deep-dive IR investigation into a multi-stage intrusion impacting Frothly's cloud and on-prem infrastructure. This sprint analyzed phishing-based compromise, cryptomining, persistence mechanisms, AWS key leakage, C2 communication, account abuse, and lateral movement using Splunk, CloudTrail, Sysmon, Suricata, and OSINT.



This project emulates an attack chain that includes a macro-enabled malicious spreadsheet, endpoint compromise, AWS credential theft, cryptocurrency mining, unauthorized resource creation, cloud misconfigurations, and attempts at email exfiltration. Events were mapped during the investigation across endpoint, cloud logs, and network telemetry in order to present a triage report with complete alignment to MITRE ATT&CK.



Confirmed True Positive compromise via malicious XLSM file Frothly-Brewery-Financial-Planning-FY2019-Draft.xlsm dropping HxTsr.exe, followed by attacker persistence and reconnaissance.


IR Triage Report 

It detected cloud abuse by leaked IAM key AKIAJOGCDXJ5NW5PXUPA, including attempted EC2 launches with Ubuntu xenial and public S3 bucket misuse: frothlywebcode.


Investigation notes

Monero cryptomining was detected on the endpoints, notably bstoll-l using 100% CPU and calling out to six mining destinations using SEP signature ID 30358 for first detection.


Investigation notes

Identified attacker persistence by the creation of a privileged user named svcvnc on FYODOR-L, password Password123!


Investigation notes

Email exfiltration setup observed through transport rule SOX, along with malicious uploads using the Naenara browser user-agent.


IR Triage Report

Mapped adversary tactics to MITRE ATT&CK including:

T1566.001 - Spearphishing Attachment

T1204.002 - Malicious File Execution

T1078 – Valid Accounts

T1105 - Ingress Tool Transfer

T1496 – Resource Hijacking (cryptomining)

T1090.001 - Proxy C2 (199.66.91.253)

T1036 - Masquerading

T1071.001 - Web C2 channel


IR Triage Report

Data Sources & Tools

Splunk - CloudTrail, VPC Flow Logs, Sysmon, O365, Web, Stream

Suricata IDS

Windows Event Logs

OSINT, CVE lookup, domain/IP pivoting


Skills Demonstrated

Advanced incident investigation

Cloud Compromise Analysis

SIEM correlation & alert triage

MITRE ATT&CK mapping

Threat intelligence enrichment

Persistence & C2 detection

Cryptomining investigation

AWS key leakage analysis



Stephen Ettienne
Security+ Certified | Cybersecurity Analyst 
