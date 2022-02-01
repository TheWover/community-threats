# UNC2452 Supply Chain Attack Adversary Emulation Plan

This threat is explained further in SCYTHE Threat Thursday blog: https://www.scythe.io/library/threatthursday-unc2452

This threat is based on information published by the Mitre ATT&CK project on the actions now credited to APT29 : https://attack.mitre.org/groups/G0118/

To emulate:
1. Download and import the threat in JSON format to your SCYTHE instance - https://raw.githubusercontent.com/scythe-io/community-threats/master/UNC2452/UNC2452_scythe_threat.json
2. Download the Virtual File System (VFS) files under UNC2452/VFS
3. Upload the VFS files to your SCYTHE VFS in the following location: VFS:/shared/UNC2452
4. Create a new campaign, selecting HTTPS, and ensuring the communication options match the CTI: --cp yourdomain[.]com:443 --secure true --multipart 10240 --heartbeat 62 --jitter 39
5. Import from Existing Threat: UNC2452
6. Launch Campaign

Note that different TTPs will be performed based on the endpoint being on a domain or not and running with local administrator privileges or not.
