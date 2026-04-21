SOC log analysis using Splunk and Windows Event Logs
# Windows Event Log Analysis (SOC Lab)

## Objective
This project focuses on analyzing Windows Security Event Logs using Splunk to identify potential reconnaissance activities, specifically local group enumeration.

## Tools Used
* **Splunk Enterprise** (SIEM)
* **Windows 10/11** (Target Machine)
* **PowerShell** (For event generation)

## Technical Analysis: Event Code 4798
The screenshot below captures **Event Code 4798**, which triggers when a user's local group membership is enumerated. In a real-world scenario, attackers use this to find accounts with administrative privileges.

<img width="1118" height="600" alt="all-logs" src="https://github.com/user-attachments/assets/3fb089cf-3cdf-4174-b1e8-1f5e0b76faa4" />

### Splunk Search Query
To find these specific events, I used the following SPL:
`index="main" EventCode=4798 | table _time, ComputerName, Subject_Account_Name, Message`

## Key Observations
* **Account Name:** [Redacted] performed the enumeration.
* **Process Name:** `C:\Windows\explorer.exe`
* **Significance:** Frequent 4798 events from an unusual user account can indicate a "Discovery" phase of the MITRE ATT&CK framework.
