# Windows Endpoint Security: Microsoft Defender Antivirus & Windows Firewall

**Status:** In Progress  
**Category:** Windows Security / Endpoint Protection  
**Environment:** Windows virtual machine provided through Coursera  
**Source:** Practical exercises from the Coursera course *Microsoft Windows Defender and Firewall for Beginners*

## Overview

This project documents practical exercises involving Microsoft Defender Antivirus and Windows Firewall in a Windows virtual machine provided through the Coursera lab environment.

The project brings together endpoint protection, antivirus scan verification, Windows Firewall configuration, and security analysis. The original exercises are being reorganized and documented as a technical portfolio project, with additional explanation of security implications and verification results.

## Objectives

- Review Microsoft Defender Antivirus protection status and threat definitions.
- Perform and document antivirus scan results.
- Examine Windows Firewall configuration and rule management.
- Explain the security purpose of the configurations and their limitations.
- Document observed results and distinguish verified findings from assumptions.

## Lab Environment

The exercises were performed in a Windows virtual machine provided through Coursera.

The available screenshots document different system states and timestamps. These are treated as separate observations rather than assumed to represent one continuous session.

## Part 1: Microsoft Defender Antivirus

### 1.1 Review Windows Security

The Windows Security overview displayed the following protection areas:

- Virus & threat protection
- Firewall & network protection
- App & browser control
- Device security

<img width="771" height="607" alt="Windows Security - 2" src="https://github.com/user-attachments/assets/d334fc0f-5f87-4fbf-bf05-2bae803349ae" />   

The overview indicated that no action was required in these areas at the time shown in the screenshot.

### 1.2 Review Windows Update Status

A Windows Update screenshot displayed a warning that the system was missing security and quality updates. It also indicated that automatic updates had been disabled by an organizational policy.

<img width="788" height="626" alt="Update and Security - 1" src="https://github.com/user-attachments/assets/288dc5ad-8873-4d87-84a2-fb0e008829e7" />   

The screenshot showed an update check dated September 16, 2020.

**Security consideration:** Missing security updates can leave a system exposed to known vulnerabilities. Update status and policy configuration should therefore be reviewed as part of endpoint security maintenance.

The screenshot represents a recorded state of the lab environment; it does not establish the update status of the system during the later antivirus scans.

### 1.3 Review Antivirus Protection Definitions

The Windows Security interface displayed the following protection definition information:

- **Definition version:** 1.411.424.0
- **Version created:** May 29, 2024, 1:07 AM
- **Last update:** May 29, 2024, 5:33 PM

The interface also provided an option to check for updates.

**Security consideration:** Antivirus protection depends in part on current threat intelligence and definitions. Reviewing the update status helps establish whether the recorded protection information is current for the time of the observation.

The screenshot documents the displayed version and update timestamp; it does not independently establish the current status of the antivirus engine or all protection components.

### 1.4 Perform and Review a Quick Scan

The available screenshots document two different Quick Scan results:

| Observation | Scan date | Duration | Files scanned | Threats found |
|---|---|---|---:|---:|
| Earlier recorded scan | April 13, 2020 | 54 seconds | 16,113 | 0 |
| Later recorded scan | May 29, 2024 | 3 minutes 8 seconds | 34,072 | 0 |

<img width="842" height="728" alt="Run Antivirus Quick Scan - 6" src="https://github.com/user-attachments/assets/96cb835e-685c-4b40-ab31-2a95cc9ad746" />   

<img width="845" height="722" alt="Run Antivirus Quick Scan - 7" src="https://github.com/user-attachments/assets/d0bfd815-515f-4456-9680-939a3db0fa39" />   

Both screenshots reported no detected threats.

The screenshots show different scan dates and results and are documented as separate observations.

**Interpretation:** The recorded scans did not identify threats at the time they were performed. A clean Quick Scan does not prove that a system is free from malware or other security weaknesses.

### 1.5 Review Scan Options

The Windows Security interface displayed the following scan options:

- Quick scan
- Full scan
- Custom scan
- Microsoft Defender Offline scan

<img width="850" height="726" alt="Scan Options- Custom Scan - 9" src="https://github.com/user-attachments/assets/f9bc0800-5d37-474a-9af3-d1161da970df" />    

Custom scan was selected in the recorded screenshot. The available evidence does not establish that a Custom Scan was subsequently executed.

## Part 2: Windows Firewall

**Status: In Progress**

This section will document the Windows Firewall exercises after the original screenshots have been reviewed.

Planned documentation includes:

- Firewall configuration and relevant network profiles
- Inbound and outbound rules
- Rule properties and access scope
- Verification of the recorded configuration
- Security implications and limitations

Only configurations and results supported by the lab evidence will be documented as completed.

## Security Analysis

The Defender exercises demonstrate basic endpoint protection checks, including reviewing protection definitions, examining Windows Update status, and interpreting antivirus scan results.

The observations also illustrate an important distinction: a scan that reports no detected threats is not equivalent to a complete security assessment. Endpoint security depends on multiple controls, including patch management, appropriate configuration, network protection, and ongoing monitoring.

The Windows Firewall section will extend this analysis by examining how host-based network traffic controls contribute to endpoint security.

## Limitations

- The project is based on guided exercises in a virtual lab environment.
- The available screenshots do not establish that the system was exposed to real malware or that detection effectiveness was independently tested.
- Different timestamps and recorded system states are kept separate.
- The project does not claim production deployment or enterprise-scale security validation.
- Additional findings will be included only when supported by the original lab material or subsequent documented tests.

## Learning Outcomes

This project is intended to demonstrate practical familiarity with Windows endpoint security interfaces, antivirus scan verification, protection definition status, and Windows Firewall configuration.

The final learning outcomes and conclusions will be expanded when the Firewall section has been reconstructed and reviewed.

## Acknowledgment

The original practical exercises were based on the Coursera course *Microsoft Windows Defender and Firewall for Beginners*. This repository reorganizes and documents the lab work for technical learning and portfolio purposes.

## Project Status

- [x] Review available Defender screenshots
- [x] Document recorded protection definition information
- [x] Document available Quick Scan results
- [x] Record relevant limitations and timestamp differences
- [ ] Reconstruct the Windows Firewall exercises
- [ ] Add verified Firewall configuration evidence
- [ ] Complete the combined security analysis
- [ ] Final review and publication


