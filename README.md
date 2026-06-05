# SOC-Automation-Lab

## Objective

The main objective of this project is to build a fully functional Security Operations Center (SOC) home lab from scratch to gain practical, hands-on experience in cybersecurity operations.

### Skills Learned

- **Security Architecture Design:** Creating logical diagrams to map out network components and visualize how data flows between systems
- **Endpoint Log Configuration:** Configuring endpoints to collect specific security events using tools like Sysmon and modifying configuration files to route those logs correctly
- **Custom Threat Detection:** Writing custom detection rules to identify specific malicious activities, such as credential dumping
- **Security Automation (SOAR):** Building automated workflows to handle repetitive analyst tasks, like extracting indicators of compromise (IOCs) using regular expressions
- **Threat Intelligence Gathering:** Automatically enriching alert data by querying open-source intelligence (OSINT) databases
- **Case Management:** Configuring systems to automatically generate detailed security alert tickets for analysts to review

### Tools Used

- **Windows 11 & Ubuntu Linux:** The operating systems used for the victim client machine and the security servers
- **Sysmon:** A Windows system service used to monitor and log detailed system activity
- **Wazuh:** An open-source security platform (SIEM/XDR) used to collect logs, monitor the endpoint, and trigger security alerts
- **Mimikatz:** A post-exploitation tool used in this lab to simulate a real-world cyber attack and generate malicious logs
- **Shuffle:** A Security Orchestration, Automation, and Response (SOAR) platform used to build the automated workflows
- **VirusTotal:** A threat intelligence service used via API to analyze and enrich file hashes
- **The Hive:** A scalable security incident response and case management platform used to track the alerts
- **Draw.io:** A diagramming tool used to visually map out the lab environment and automation workflow

## Steps

1: Logical Diagram

Key Components:

| Windows 11 Client (Wazuh Agent) |
Wazuh (SIEM and XDR) |
Shuffle (SOAR) |
The Hive (Case Management) |

1. Windows 11 send events to Wazuh Manager
2. Wazuh Manager receives the events
3. Wazuh Manager creates an alert and sends it to shuffle
4. When shuffle receives alert, shuffle performs osint to enrich IOCS
5. Shuffle will then send an alert to The Hive to create alert in case management
6. Shuffle will also send an email to the SOC Analyst
7. The SOC Analyst sends response actions to the Wazuh Manager through shuffle
8. Wazuh will instruct the agent to preform the responsive action

<img width="500" height="524" alt="socautomation" src="https://github.com/user-attachments/assets/778849b6-a549-40f1-b9b9-2894333d9648" />
