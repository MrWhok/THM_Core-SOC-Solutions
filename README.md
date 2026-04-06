# THM_Core-SOC-Solutions

## Table of Contents
1. [Introduction to EDR](#introduction-to-edr)
2. [Introduction to SIEM](#introduction-to-siem)
3. [Splunk: The Basics](#splunk-the-basics)
4. [Elastic Stack: The Basics](#elastic-stack-the-basics)

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

## Splunk: The Basics
### Splunk Components
1. Which component is used to collect and send data over the Splunk instance?

    The answer is `Forwarder`.

### Navigating Splunk
1. In the Add Data tab, which option is used to collect data from files and ports?

    The answer is `Monitor`.

### Adding Data
1. Upload the data attached to this task and create an index "VPN_Logs". How many events are present in the log file?

    The answer is `2862`.

2. How many log events are captured by the user Maleena?

    We can use this filter to find the answer: 

    ```json
    source="VPN-logs-1663593355154.json" host="ip-10-10-40-195" sourcetype="_json" UserName=Maleena
    ```
    The answer is `60`.

3. What is the username associated with IP 107.14.182.38?

    We can use this filter to find the answer: 

    ```json
    source="VPN-logs-1663593355154.json" host="ip-10-10-40-195" sourcetype="_json" Source_ip=107.14.182.38
    ```
    The answer is `Smith`.

4. What is the number of events that originated from all countries except France?

    We can use this filter to find the answer: 

    ```json
    source="VPN-logs-1663593355154.json" host="ip-10-10-40-195" sourcetype="_json" NOT Source_Country=France
    ```
    The answer is `2814`.

5. How many VPN events were associated with the IP 107.3.206.58?

    We can use this filter to find the answer: 

    ```json
    source="VPN-logs-1663593355154.json" host="ip-10-10-40-195" sourcetype="_json" Source_ip=107.3.206.58
    ```

    The answer is `14`.


## Elastic Stack: The Basics
### Elastic Stack Overview
1. Logstash is used to visualize the data. (yay / nay)

    The answer is `nay`. Logstash is used to collect data from various source (one of the is beats), parse, and store data to the Elasticsearch database. 

2. Elasticstash supports all data formats apart from JSON. (yay / nay)

    The answer is `nay`. 

### Discover Tab
1. Select the index vpn_connections and filter from 31st December 2021 to 2nd Feb 2022. How many hits are returned?

    The answer is `2861`.

2. Which IP address has the maximum number of connections?

    The answer is `238.163.231.224`.

3. Which user is responsible for the overall maximum traffic?

    The answer is `James`.

4. Apply Filter on UserName Emanda; which SourceIP has max hits?

    The answer is `107.14.1.247`.

5. On 11th Jan, which IP caused the spike observed in the time chart?

    The answer is `172.201.60.191`.

6. How many connections were observed from IP 238.163.231.224, excluding the New York state?

    The answer is `48`.

### KQL Overview
1. Create a search query to filter the logs where Source_Country is the United States and show logs from User James or Albert. How many records were returned?

    We can use this filter to find the answer: 

    ```kql
    Source_Country: "United States"  AND (UserName: "James" OR "Albert")
    ```
    The answer is `161`.

2. A user Johny Brown was terminated on the 1st of January, 2022. Create a search query to determine how many times a VPN connection was observed after his termination.

    We can use this filter to find the answer: 

    ```kql
    UserName: "Johny Brown" AND action: "built" AND @timestamp >= "2022-01-01T00:00:00Z"
    ```
    action: "built" is used to filter the logs where a connection was established. The answer is `1`.

### Creating Visualizations
1. Which user was observed with the greatest number of failed attempts?

    We can go to `visualize library` and apply the following filters to find the answer:

    ```kql
    action: "failed"
    ```
    Then, we can drag username. The answer is `Simon`.

2. How many wrong VPN connection attempts were observed in January?

    The answer is `274`.
