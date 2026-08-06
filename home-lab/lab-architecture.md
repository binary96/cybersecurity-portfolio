# SOC Home Lab Architecture

## Objective

The purpose of this home lab is to develop practical security operations skills in a controlled environment. The lab will be used to generate, collect and investigate Windows security events using tools such as Event Viewer, Sysmon, Splunk and Wazuh.

## Host Specifications

- Device: HP ProBook 650 G5
- Processor: Intel Core i5-8365U @ 1.60 GHz
- Memory: 8 GB RAM (7.81 GB usable)
- Storage: 238 GB
- Host operating system: Windows 11 Pro, 64-bit
- System architecture: x64-based processor
- Primary limitation: Limited memory for running multiple virtual machines

## Virtualization Software

VirtualBox will be used as the hypervisor for creating and managing the Windows virtual machine.

The hypervisor separates the guest operating system from the physical host computer and allows the virtual machine to be restored using snapshots.

## Guest Operating System

The main guest system will be a Windows 10 or Windows 11 virtual machine.

Planned resource allocation:

- Memory: Approximately 4 GB RAM
- Processor: 2 virtual CPU cores
- Storage: Dynamically allocated virtual disk
- Number of active virtual machines: One at a time

The Windows virtual machine will be used to generate and investigate security events without using workplace or personal organisational systems.

## Network Configuration

NAT networking will initially be used.

NAT will allow the Windows virtual machine to access the internet through the host laptop while reducing its direct exposure to other devices on the local network.

Host-only networking may be introduced during later isolated lab exercises.

## Security Controls and Data Sources

The lab will use the following security controls and monitoring tools:

- Windows Defender
- Windows Firewall
- Windows Event Viewer
- Sysmon
- Splunk or Wazuh
- Virtual machine snapshots

Windows Event Viewer and Sysmon will provide endpoint telemetry. Splunk or Wazuh will be used to search, analyse and present the collected events.

## Lab Architecture

```mermaid
flowchart TD
    A["Host Laptop"]
    B["VirtualBox"]
    C["Windows 10/11 VM"]
    D["Windows Event Logs and Sysmon"]
    E["Splunk or Wazuh"]

    A --> B
    B --> C
    C --> D
    D --> E
