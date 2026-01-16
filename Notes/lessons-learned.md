# Lessons Learned – Endpoint Telemetry Pipeline

## Why this phase mattered

Before building detections, it was critical to ensure that endpoint telemetry was reliable, complete, and observable. Without trustworthy data, detections lose meaning.

## Key challenges encountered

* Time drift affected confidence in log correlation
* Forwarder stability required validation, not assumption
* Network configuration mistakes slowed troubleshooting
* Windows updates introduced unexpected performance issues

## What this reinforced

* Telemetry reliability is a prerequisite for detection
* Small infrastructure issues can cascade into major blind spots
* Troubleshooting builds stronger intuition than “happy path” setups

## How this informs next steps

This foundation will be used to detect authentication abuse patterns and later monitor a Cowrie SSH honeypot from a Linux host.

