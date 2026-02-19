Endpoint Telemetry Pipeline (Windows → Splunk)

This project documents the implementation and validation of a reliable Windows endpoint telemetry pipeline prior to performing detection engineering or alerting.

The objective was not to build detections, but to ensure that endpoint telemetry is complete, stable, and trustworthy before relying on it for security analysis.

Objectives

Deploy Sysmon on a Windows endpoint

Enable Windows audit and PowerShell logging

Configure Splunk Universal Forwarder

Validate reliable event forwarding to Splunk

Identify and resolve ingestion or stability issues

Lab Environment

Host OS: Windows

Guest OS: Windows 10 (VirtualBox VM)

SIEM: Splunk Enterprise (Linux VM)

Endpoint Agent: Splunk Universal Forwarder

Telemetry Sources:

Sysmon

Windows Security logs

PowerShell logging

Windows Audit Policy Configuration

Windows audit policies were configured to ensure generation of meaningful security telemetry, including:

Process Creation

Account Management

Policy Change

<img src="./screenshots/audit-policy-enabled.png" width="850">

This ensured foundational event visibility prior to forwarder configuration.

Sysmon Deployment & Local Telemetry Validation

Sysmon was deployed using a controlled configuration to generate enriched process-level telemetry.

Sysmon Installation Verification
<img src="./screenshots/sysmon-installed-files.png" width="850">
Process Creation Event Validation

A controlled process execution was performed and verified locally to confirm Sysmon event generation.

<img src="./screenshots/sysmon-process-create-event.png" width="850">

This confirmed endpoint telemetry generation before SIEM ingestion testing.

Splunk Universal Forwarder Configuration

The Splunk Universal Forwarder was installed and validated to ensure reliable event forwarding.

<img src="./screenshots/splunk-forwarder-running.png" width="850">

Forwarder service health was confirmed prior to ingestion validation.

Splunk Ingestion Validation

Windows Security and endpoint telemetry were verified inside Splunk to confirm end-to-end visibility.

<img src="./screenshots/splunk-sourcetype-ingestion-overview.png" width="850">

This confirmed successful data flow from endpoint → forwarder → SIEM.

Sysmon Ingestion Note

Sysmon successfully generated enriched endpoint telemetry locally. However, ingestion into Splunk proved inconsistent due to endpoint instability.

The issue was isolated, documented, and resolved through a controlled endpoint rebuild before proceeding to detection engineering.

This reinforced the importance of validating telemetry reliability before building analytics dependent on it.

Validation Activities

Controlled actions were performed on the Windows endpoint and verified in Splunk:

Process execution events

PowerShell command execution

Security log generation

Successful ingestion confirmed end-to-end visibility from endpoint to SIEM.

Issues Identified & Resolved

During implementation, the following issues were identified and addressed:

Time synchronization drift impacting log correlation

Forwarder service instability

Network configuration inconsistencies

System performance degradation from updates

Each issue was validated post-remediation to ensure telemetry stability.

Key Lessons

Reliable detection engineering depends on reliable telemetry

Time synchronization is critical for accurate correlation

Forwarder health must be continuously validated

Telemetry validation must precede detection development