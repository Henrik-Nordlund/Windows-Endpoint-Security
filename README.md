# Windows Endpoint Security: Microsoft Defender Antivirus & Windows Firewall

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

<img width="851" height="723" alt="Check for Updates - 5" src="https://github.com/user-attachments/assets/6a2343e9-d0dd-46c3-9764-6070bd81d2a5" />   


The interface also provided an option to check for updates.

**Security consideration:** Antivirus protection depends in part on current threat intelligence and definitions. Reviewing the update status helps establish whether the recorded protection information is current for the time of the observation.

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

Custom scan was selected here. 

## Part 2: Windows Firewall

### 2.1 Firewall Status and Network Profiles
Windows Defender Firewall was reviewed through the Windows Security interface to examine the firewall status and configuration of the three available network profiles:

- **Domain network:** Firewall enabled; no active domain network connection.
- **Private network:** Firewall enabled; no active private network connection.
- **Public network:** Firewall enabled; active network identified as *Network 6*.

The firewall was enabled for all three profiles, with the Public network profile active in the lab environment.

The option to block all incoming connections, including those for allowed applications, was not selected in the displayed profile settings.

**Security consideration:** Windows Firewall uses separate network profiles to apply security settings according to the type of network connection. Public networks generally require more restrictive access controls because the connected devices and network environment cannot be assumed to be trusted.

<img width="836" height="680" alt="Firewall and Network Protection - 2" src="https://github.com/user-attachments/assets/10f9ef00-bd90-440d-b330-a05817e64c10" />    

<img width="851" height="691" alt="Public Network - 5" src="https://github.com/user-attachments/assets/f8095f1c-2cdf-474a-a7d8-4e50bef094c1" />    

The screenshots above confirm the displayed firewall status and active network profile but do not independently verify network traffic filtering.


### 2.2 Application Exceptions
The Windows Defender Firewall application exceptions were reviewed through the **Allow an app through firewall** interface.

This interface allows administrators to configure which applications and Windows features are permitted to communicate through the firewall on Private and Public networks.

The initial screenshot showed several configured application exceptions, including:

- **Mozilla Firefox:** Allowed on Private networks only.
- **Google Chrome:** Allowed on both Private and Public networks.
- **File and Printer Sharing:** Not enabled in the displayed list.
- **mDNS:** Allowed on both Private and Public networks.

<img width="781" height="594" alt="Allow an App through Firewall - 6" src="https://github.com/user-attachments/assets/056d8464-4b7b-4f95-9b7c-48c78bbc01bd" />   

A later screenshot showed Mozilla Firefox selected with both the Private and Public checkboxes enabled, indicating a change in the displayed application exception configuration.

<img width="785" height="596" alt="Allow an App through Firewall - 7" src="https://github.com/user-attachments/assets/531188de-0525-4f7a-8f81-aa49612cef3c" />     

**Security consideration:** Application exceptions should be limited to the network profiles where they are required. Allowing applications to receive unsolicited inbound connections on Public networks can increase the system's attack surface.

The screenshots document the displayed exception settings and their differences. They do not independently verify whether the applications were listening for incoming connections or whether network traffic was successfully permitted through the firewall.



### 2.3 Advanced Firewall Configuration
Windows Defender Firewall with Advanced Security was opened to examine the firewall's configuration and rule management capabilities.

The interface provides access to:

- **Inbound Rules:** Control incoming network connections.
- **Outbound Rules:** Control outgoing network connections.
- **Connection Security Rules:** Configure connection security policies, including IPsec.
- **Monitoring:** Review firewall and connection security information.

The overview displayed the following configuration for all three network profiles:

| Setting | Domain | Private | Public |
|---|---|---|---|
| Firewall status | On | On | On |
| Inbound connections not matching a rule | Block | Block | Block |
| Outbound connections not matching a rule | Allow | Allow | Allow |

<img width="1012" height="711" alt="Advanced Settings Overview - 8" src="https://github.com/user-attachments/assets/f419d06c-2c14-4d98-8553-f2e898d66a85" />   

The Public profile was active in the recorded environment.

This configuration follows a default-deny approach for unsolicited inbound traffic while permitting outbound traffic unless a rule explicitly blocks it.

The Inbound Rules interface was also examined. It displayed predefined rules for Windows services and features, including File and Printer Sharing, Network Discovery, Remote Desktop, Windows Remote Management, and Key Management Service.

Individual rules can specify whether connections are allowed or blocked, whether the rule is enabled, and which network profiles it applies to.

<img width="1016" height="717" alt="Key Management Service - 9" src="https://github.com/user-attachments/assets/24e42855-fd4e-4503-8b80-582a65a8736d" />   


**Security consideration:** Firewall rules should be configured according to operational requirements and the principle of least privilege. Unnecessary inbound access should be restricted, particularly for administrative services and systems connected to untrusted networks.

The screenshots document the displayed firewall policies and rule configurations. They do not establish that traffic filtering was independently tested.


### 2.4 Key Management Service – Rule Configuration
The predefined **Key Management Service (TCP-In)** firewall rule was examined through Windows Defender Firewall with Advanced Security.

Key Management Service (KMS) is used for volume activation of Microsoft products in organizational environments. KMS communication typically uses TCP port **1688**.

The available screenshots document the inspection and configuration of the rule, including:

- **Rule status:** Whether the rule is enabled or disabled.
- **Action:** Whether matching inbound connections are allowed or blocked.
- **Network profiles:** Whether the rule applies to Domain, Private, or Public networks.
- **Protocol and port:** TCP port 1688.

The rule properties were examined to review the available configuration options.
<img width="1016" height="717" alt="Key Management Service Properties - 10" src="https://github.com/user-attachments/assets/d0361ead-c0b9-4eb0-bac5-697e6e397b72" />   

<img width="1018" height="716" alt="Key Management Service Advanced - 11" src="https://github.com/user-attachments/assets/2aa385db-8fbd-4d8e-b3c6-f331524e222e" />    


<img width="1012" height="713" alt="Block The Connection For Public Advanced - 14" src="https://github.com/user-attachments/assets/4c473358-c7fa-42be-bfe9-2ed683f7059e" />    

The screenshots also show the configuration of a blocking rule for the Public network profile.

In the later Inbound Rules overview, two enabled Key Management Service rules were displayed:

| Network profile | Rule enabled | Action |
|---|---|---|
| Domain | Yes | Allow |
| Public | Yes | Block |

This demonstrates how firewall rules can apply different access restrictions depending on the network profile.

<img width="1014" height="717" alt="Rules Enabled - 16" src="https://github.com/user-attachments/assets/49d2c9fa-dc51-4ac4-9aab-32c6a5cb6d2f" />    

**Security consideration:** Services required within a managed organizational network should not automatically be accessible from less trusted networks. Restricting inbound connections according to network profile helps reduce unnecessary exposure.

The screenshots document the configured rule properties and their displayed status. They do not independently demonstrate successful KMS communication or confirm that blocked connections were tested.


### 2.5 Windows Remote Management – Inbound Rule

The predefined **Windows Remote Management (HTTP-In)** firewall rule was examined through Windows Defender Firewall with Advanced Security.

Windows Remote Management (WinRM) enables remote administration of Windows systems and is used by management tools and PowerShell remoting. WinRM commonly uses TCP port **5985** for HTTP-based communication.

The available screenshots document the inspection of the inbound firewall rule, including:

- **Rule name:** Windows Remote Management (HTTP-In).
- **Protocol and port:** TCP port 5985.
- **Rule status:** Enabled.
- **Action:** Block the connection.

The rule properties showed that the firewall action was configured to **Block the connection**.

<img width="1009" height="719" alt="Block Windows Remote Management On The Public Network - 17" src="https://github.com/user-attachments/assets/8d889dcd-a2de-49f2-a72a-d97afe704929" />    

<img width="1015" height="727" alt="Block Windows Remote Management On The Public Network Advanced - 18" src="https://github.com/user-attachments/assets/9a396dfe-c4a2-4512-9322-3542ce0bb3ae" />    


**Security consideration:** Remote management services can provide powerful administrative access to a system. Unnecessary exposure of WinRM should therefore be restricted, particularly on untrusted networks.

Blocking inbound WinRM connections can reduce the attack surface when remote administration is not required. In managed environments, however, firewall restrictions must be balanced against legitimate administration and operational requirements.

The screenshots document the displayed firewall rule configuration. They do not independently verify that WinRM was listening on TCP port 5985 or that an attempted remote connection was successfully blocked.


### 2.6 Security Findings and Verification Limitations

The Windows Firewall exercises demonstrated how host-based firewall configuration can be used to control network access and reduce unnecessary exposure of Windows services.

**Key findings:**

- **Network profiles:** Windows Defender Firewall was enabled for Domain, Private, and Public networks, with the Public profile active in the recorded lab environment.
- **Default traffic policies:** Inbound connections without a matching rule were blocked by default, while outbound connections without a matching rule were allowed.
- **Application exceptions:** The configuration differed between Private and Public networks, illustrating how application access can be controlled according to network profile.
- **Service-specific rules:** The Key Management Service exercise demonstrated profile-based firewall rule configuration for TCP port 1688.
- **Remote administration:** The Windows Remote Management exercise documented an enabled blocking rule for inbound HTTP-based management traffic on TCP port 5985.

**Security implications:**

The exercises illustrate the importance of applying firewall restrictions according to network trust levels and operational requirements.

Limiting unnecessary inbound connections, particularly for administrative services, can reduce the attack surface of a Windows endpoint. Firewall configuration should follow the principle of least privilege while preserving required system functionality.

**Verification limitations:**

The available screenshots document the displayed firewall settings and rule configurations. No packet captures, connection attempts, or firewall logs were available to independently verify enforcement of the documented rules.

The results therefore demonstrate practical firewall configuration and inspection rather than a comprehensive assessment of the effectiveness of the firewall.

## Security Analysis

The Defender exercises demonstrate basic endpoint protection checks, including reviewing protection definitions, examining Windows Update status, and interpreting antivirus scan results.

The observations also illustrate an important distinction: a scan that reports no detected threats is not equivalent to a complete security assessment. Endpoint security depends on multiple controls, including patch management, appropriate configuration, network protection, and ongoing monitoring.

The Windows Firewall exercises demonstrate how network access can be controlled through firewall rules and network profiles according to different security requirements.

## Limitations

- The project is based on guided exercises in a virtual lab environment.
- The available screenshots do not establish that the system was exposed to real malware or that detection effectiveness was independently tested.
- Different timestamps and recorded system states are kept separate.
- This project does not claim production deployment or enterprise-scale security validation.

## Learning Outcomes

This project demonstrates practical experience with Microsoft Defender Antivirus and Windows Firewall, including:

- Reviewing endpoint protection status, security updates, and antivirus scan results.
- Configuring application exceptions and inbound firewall rules.
- Applying firewall restrictions based on network profiles and security requirements.
- Evaluating security configurations and recognizing the limitations of available evidence.

## Acknowledgment

The original practical exercises were based on the Coursera course *Microsoft Windows Defender and Firewall for Beginners*. This repository reorganizes and documents the lab work for technical learning and portfolio purposes.



