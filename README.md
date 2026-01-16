\# Endpoint Telemetry Pipeline (Windows → Splunk)



This project documents the process of building a \*\*reliable Windows endpoint telemetry pipeline\*\* prior to performing any detection engineering or alerting.



The focus of this lab was not on creating detections, but on ensuring that \*\*endpoint telemetry is complete, trustworthy, and observable\*\* before relying on it for security analysis.



\## Objectives

\- Deploy Sysmon on a Windows endpoint

\- Enable key Windows audit and PowerShell logging

\- Forward logs reliably to Splunk

\- Validate end-to-end telemetry

\- Identify and resolve common ingestion and stability issues



\## Lab Environment

\- \*\*Host OS:\*\* Windows

\- \*\*Guest OS:\*\* Windows 10 (VirtualBox)

\- \*\*SIEM:\*\* Splunk Enterprise (Linux VM)

\- \*\*Endpoint Agent:\*\* Splunk Universal Forwarder

\- \*\*Telemetry Sources:\*\* Sysmon, Windows Security logs, PowerShell logging



\## Validation

Controlled actions were performed on the Windows endpoint and validated in Splunk, including:

\- Process execution

\- PowerShell command execution

\- Security event generation



Successful ingestion confirmed \*\*end-to-end visibility\*\* from endpoint to SIEM.



\## Issues Encountered \& Resolutions

Common lab issues were encountered and resolved, including:

\- Time drift affecting log correlation

\- Forwarder service instability

\- Network configuration confusion

\- Performance degradation from system updates



\## Lessons Learned

\- Reliable detection depends on reliable telemetry

\- Time synchronization is critical for log analysis

\- Forwarder stability must be verified, not assumed



\## Next Steps

This foundation will be used to:

\- Detect authentication abuse patterns

\- Transition into Linux-based monitoring

\- Deploy and monitor a Cowrie SSH honeypot



