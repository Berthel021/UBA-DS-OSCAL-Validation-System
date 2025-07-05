# UBA-DS OSCAL Validation System with CrowdStrike & Multi-SIEM Integration

![CI/CD Status](https://github.com/yourorg/uba-ds-oscal-crowdstrike/actions/workflows/deploy.yml/badge.svg)
![Security Scan](https://github.com/yourorg/uba-ds-oscal-crowdstrike/actions/workflows/security-scan.yml/badge.svg)
![NIST Compliance](https://github.com/yourorg/uba-ds-oscal-crowdstrike/actions/workflows/nist-compliance.yml/badge.svg)

A production-ready User Behavior Anomaly Detection System that validates OSCAL documents while integrating with CrowdStrike Falcon and multiple SIEM platforms.

## Key Features

- **Automated Anomaly Detection**: ML-powered scoring of user behavior deviations
- **Multi-SIEM Integration**: Splunk, QRadar, Elastic, and generic webhook support
- **CrowdStrike Falcon**: Real-time host containment & forensic collection
- **ServiceNow Sync**: Bi-directional incident management
- **NIST 800-53 Ready**: Pre-mapped compliance controls

## Architecture

graph TD
    A[UBA-DS] -->|Alerts| B[CrowdStrike Falcon]
    A -->|Logs| C{Splunk/QRadar/Elastic}
    A -->|Tickets| D[ServiceNow]
    B -->|Containment| E[AWS EC2]
    C -->|Dashboards| F[SIEM Consoles]
    D -->|Remediation| A

Integrations
Platform	Capabilities	Configuration File
CrowdStrike	Host containment, RTR forensics	modules/crowdstrike/main.tf
Splunk	CEF-formatted alerts, HEC ingestion	modules/siem_integration/splunk/
QRadar	LEEF events, DSM configuration	modules/siem_integration/qradar/
ServiceNow	Incident auto-ticketing, CMDB sync	modules/servicenow/siem_sync.tf
AWS	Lambda orchestration, S3 forensics	modules/logging/main.tf
Quick Start|

Prerequisites

Terraform 1.3+

AWS account with required permissions

CrowdStrike Falcon API credentials

SIEM endpoint details
