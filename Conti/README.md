# Conti Ransomware Adversary Emulation Plan

This threat is based on The DFIR Report post on May 12, 2021: https://thedfirreport.com/2021/05/12/conti-ransomware/

## Instructions
1. Download and import the threat in JSON format to your SCYTHE instance: https://raw.githubusercontent.com/scythe-io/community-threats/master/Conti/Conti_scythe_threat.json
2. Download the Virtual File System (VFS) files under Conti/VFS
3. Upload the VFS files to your SCYTHE VFS in the following location: VFS:/shared/Conti
4. Create a new campaign, selecting HTTPS, and ensuring the communication options match the CTI: --cp yourdomain[.]com:443 --secure true --multipart 10240 --heartbeat 62 --jitter 39
5. Set the Program database path to: A:\source\conti_v3\x64\Release\cryptor_dll.pdb 
6. Import from Existing Threat: Conti
7. Launch Campaign
8. Execute with rundll32.exe

Note that different TTPs will be performed based on the endpoint being on a domain or not and running with local administrator privileges or not.
