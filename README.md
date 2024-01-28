The body of work that is showcased in this repo contain some projects that are undertaking in my role as a Security Operations Engineer or Cybersecurity Analyst or Systems Engineer or DevOps Engineer. It also extends to some personal development projects, in which some simulations are carried out to display understanding and retainership of the knowledge that is gained.

For every single project, there is a problem statement and a solution that presents the processes and implementation of methods that are executed to achieve the solution.

There is a link to the specific directory or file that provides detailed information on each project that is in this repo.
This repo contains a couple of years of projects in the making. It shines light on projects that involve threat, vulnerability, risk, data security in transit or at rest, IDR, SIEM, detection, analysis, and others.

There is a wide range of technology that has been utilized over time for the implementation of all these projects. Some of the technologies include Splunk. Tenable, Cybereason, Microsoft Defender, Microsoft Entra, IAM, CloudTrail, CloudWatch, AWS Configs, SSL/ TLS, Metasploit, Impacket, Pfsense, Security Onion, Python, Security Onion, Security Onion, Cisco, Harvester, Wireshark, SQL, Microsoft O365.

In no order, the below encapsulates each project as they appear in the repo:

#Splunk Project

#Problem Statement: There is no observatory or visibility on sign-in logs and audit logs in SIEM tool. It is imperative to be able to investigate or analyze any event related to user sign-ins and audit the logs in general in our Active Directory environment.

#Solution: Integrate the necessary components or technologies that will enable the forwarding of logs from AD to Splunk.

#Overview: 
Implemented this project to enable the ingestion of sign-in and audit logs from AD environment into Splunk, to complement the existing logs being forwarded for SIEM and improve the visibility into a previously non-integrated environment.

Link to the project-https://github.com/Needium66/Cybersecurity/blob/main/Splunk/azuread_audit_log_forwarding.yaml

Tools/Technologies Utilized:

Splunk|
Azure AD|
IAM|
0365 Add-on|
AWS Cloud Add-On|

#################

#Incident Response and Tabletop Project (Cloud):

#Problem Statement: Out of date or outdated IR plan in the cloud for our environments

#Solution: Review and Update according to regulatory and international best practices

#Overview: Updated our incident response (IP) playbook for the cloud based on compliance and international best practices. Implemented improvements on the IR plan document including the roles and responsibilities, communications, phases, and severity of events.

Updated the architecture designs with a more centralized architecture, accommodating latest AWS environments and infrastructures, SCPs, authentication and authorization patterns, logging and monitoring, network topology.

Updated the steps in our tabletop simulations to reflect current trends and events.

Updated our forensic capabilities to exhibit architectural and technology landscape in our system using the four CEAR phases.

Carried out an optimal operational improvement on our IR by using the 5 phases of DECAR (Detection, Analysis, Containment, Eradication and Recovery)

All these enabled me to be remarkably proficient in cloud security, especially in AWS and this translated to my being the operational lead for our tabletop simulations for 2 years in a row.

A more detailed overview of this project can be found in my ir file-https://github.com/Needium66/Cybersecurity/blob/main/All%20AWS%20Sec/ir_file.yaml

Tools: 
CloudTrail |VPC Flow Logs | Load Balancer| Route 53| Lambda| Event Hub| Security Hub|  GuardDuty| CloudWatch Log| AWS Configs| IAM Access Analyzer|  SNS| Network Access Analyzer| Event Bridge| IAM etc.

##############

#TLS/SSL Project

#Problem Statement: Deprecated TLS 1.0 and 1.1

#Solution: Cleanout all TLS running on this version in our AWS environments

#Overview: Some apps are still using the deprecated tls versions. The intent of this project is to find those apps that are using that or wherever there is a configuration using the old version in the system and remove it.
With the integration of CloudTrail and other services in AWS, you should be able to execute a query and then analyze the logs obtained, to get the locations of where the appropriate strings to be removed are.

This project led me to the appropriate configurations and files that had the old tls versions.
Subsequently cleaned those out.

Validated the absence of the older versions of tls in our AWS environments with another query.

Link to the file- https://github.com/Needium66/Cybersecurity/blob/main/All%20AWS%20Sec/tls.yaml

Tools: 
Data events for CloudTrail| S3| SQL|

###############

#Risky Logging Playbook

#Problem Statement: A user might inadvertently click on a link that results in risky logging alert. Create a playbook that ensures the identification, investigation, and resolution of an attack like this.

#Solution: Configure/ enable the risky logging alert in Microsoft Defender, that integrates with an email or contact number and an AD environment.

#Overview: This explains steps to be undertaking to be able to take care of a risky logging event by an operation person. A user mistakenly clicking on a malicious link will trigger the alert through an email or a tool like pager duty, where a person responsible e.g me, to manage this, will take action in the investigation of event and subsequently following procedures to resolve it

The link to the steps that can be followed can be found in the ad_lab file-https://github.com/Needium66/Cybersecurity/blob/main/ADLAB/ad_lab.yaml

Tools:
Microsoft Office 365| Microsoft Defender| Microsoft Outlook| PagerDuty| Contact Number

############

#LLMNR Project Link-Local Multicast Name Resolution (LLMNR Lab)

#Problem statement: Worked on a project to investigate usage of LLMNR in Windows servers in all environments in the system.

#Solution: Disable it and effectively implement usage of DNS

#Overview: After the project, I went further to do a LAB on LLMNR poisoning using the cybermentor module. An attacker executes the responder scriptThe script listens quietly to events and LLMNR queries taking place in the network.
When a communication/connection does occur or gets established with a target, it SENDS poisoned response to them.
If the SPOOFING ATTACKS turn successful, the username and password hash of the target will be displayed by the responder.
1.	Execute a responder script.
2.	Responder listens silently to events and LLMNR queries.
3.	If a target is hit successfully, credentials get spoofed.
4.	Responder displays username and password hash.
5.	Exploit it more.

#Lessons Learnt: It cannot be overemphasized, don’t use services that are not secure. Improve your security posture by using secure services e.g DNS as against LLMNR.

1. Disable or get rid of insecure services e.g LLMNR
2. Ensure you investigate the use of this in your system.

You can automate a script to scan your network for use of LLMNR if you don’t have tools that scan your network for services like that. But if you use a tool like Tenable, it should automatically scan for vulnerabilities like this.

Link- https://github.com/Needium66/Cybersecurity/blob/main/ADLAB/ad_lab.yaml

Did another lab in “Hack-a-box” for the ad attack

Tools:
HTB account
Kali linux
PC
Tools utilized:
Metasploit|
Crackmapexec|
Meterpreter|
Gpmc|
Nmap|
Kerberoasting|
Smb|

###############

#Personal project- 

#Problem statement: Find a way to improvement of our security posture of our CICD pipeline.

#Solution: Take necessary actions to prevent a successful PPE attack

#PPE simulation: Updated our change documentation to always integrate our already established security controls and policies to any extension of pipeline. No rulebook or guidelines in the implementation of a pipeline extension prior to this.

Link-https://github.com/Needium66/Cybersecurity/blob/main/All%20AWS%20Sec/cicd_pipeline.yaml
