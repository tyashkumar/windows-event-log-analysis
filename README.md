# windows-event-log-analysis
SOC project analyzing Windows logs using Splunk

Analyzing Windows logs to detect suspicious login activity.

## 🔍 Investigation

* Collected logs from Windows Event Viewer
* Imported logs into Splunk
* Focused on Event ID 4625 (failed logins)

## 🚨 Detection

Used Splunk query:
EventCode=4625

Identified multiple failed login attempts from the same source.

## 📌 Conclusion

Detected possible brute-force attack based on repeated failed login attempts.

## 🛠️ Tools Used

* Splunk
* Windows Event Viewer

## 📸 Screenshots


