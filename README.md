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
