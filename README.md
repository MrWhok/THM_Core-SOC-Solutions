# THM_Core-SOC-Solutions

## Table of Contents
1. [Introduction to EDR](#introduction-to-edr)
2. [Introduction to SIEM](#introduction-to-siem)

## Introduction to EDR
### What is EDR?
1. Which feature of EDR provides a complete context for all the detections?

    The answer is `Visibility`.

2. Which process spawned sc.exe?

    The answer is `cmd.exe`.

### Beyond the Antivirus
1. In the given analogy, what presents an AV?

    The answer is `immigration check`.

2. Which legitimate process was hijacked by the attacker in the scenario?

    The answer is `svchost.exe`.

3. Which security solution might mark this activity as clean?

    The answer is `Antivirus`.

### How an EDR Works
1. Which component of the EDR is responsible for collecting telemetry from the endpoints?

    The answer is `Agents`.

2. An EDR agent is also known as a?

    The answer is `Sensor`.

### EDR Telemetry
1. Which telemetry data helps in detecting C2 communications?

    The answer is `Network Connections`.

2. Where are the configuration settings of a Windows system primarily stored?

    The answer is `Registry`.

### Detection and Response Capabilities
1. Which feature of the EDR helps you identify threats based on known malicious behaviours? 

    The answer is `IOC Matching`.

### Investigate an Alert on EDR
1. Which tool was launched by CMD.exe to download the payload on DESKTOP-HR01?

    The answer is `CURL.exe`.

2. What is the absolute path to the downloaded malware on the DESKTOP-HR01 machine?

    The answer is `C:\Users\Public\install.exe`.

3. What is the absolute path to the suspicious syncsvc.exe on the WIN-ENG-LAPTOP03 machine?

    The answer is `C:\Users\haris.khan\AppData\Local\Temp\syncsvc.exe`.

4. On which URL was the exfiltration attempt being made on WIN-ENG-LAPTOP03?

    The answer is `https://files-wetransfer.com/upload/session/ab12cd34ef56/dump_2025.dmp`.

5. What was UpdateAgent.exe labelled by Threat Intel on DESKTOP-DEV01?

    The answer is `Known internal IT utility tool`.

## Introduction to SIEM
### Introduction
1. What does SIEM stand for?

    The answer is `Security Information and Event Management system`.

### Logs Everywhere, Answers Nowhere
1. Is Registry-related activity host-centric or network-centric?

    The answer is `Host-centric`.

2. Is VPN-related activity host-centric or network-centric?

    The answer is `Network-centric`.

### Log Sources and Ingestion
1. In which location within a Linux environment are HTTP logs stored?

    The answer is `/var/log/httpd/`.

### Alerting Process and Analysis
1. Which Event ID is generated when event logs are removed?

    The answer is `104`.

2. What type of alert may require tuning?

    The answer is `False Positive`.

### Lab Work
1. After clicking on the Start Suspicious Activity button, which process caused the alert?

    The answer is `cudominer.exe`.

2. Find the event that caused the alert and identify the user responsible for the process execution.

    The answer is `Chris`.

3. What is the hostname of the suspect user?

    The answer is `HR_02`.

4. Examine the rule and the suspicious process; which term matched the rule that caused the alert?

    The answer is `miner`.

5. Which option best represents the event? Choose from the following:

    - False Positive

    - True Positive

    The answer is `True Positive`.

6. Selecting the right ACTION will display the FLAG. What is the FLAG?

    The answer is `THM{000_SIEM_INTRO}`.
