# THM_Core-SOC-Solutions

## Table of Contents
1. [Introduction to EDR](#introduction-to-edr)

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