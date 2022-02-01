# CozyBear Adversary Emulation Plan

This threat is explained further in SCYTHE's Threat Thursday blog: https://www.scythe.io/library/threatthursday-cozy-bear

It is based on Step 1 and Step 2 of the CozyBear/APT29 adversary emulation plan used by MITRE in its ATT&CK Based Evaluations: https://attackevals.mitre-engenuity.org/enterprise/apt29/

There is also an explanation video and interview with our CTO, Jorge Orchilles, and Jamie Williams from MITRE: https://vimeo.com/432180389

## Instructions

1. Download and import the threats in JSON format to your SCYTHE instance - 
    * https://github.com/scythe-io/community-threats/blob/master/CozyBear/CozyBear-Step1_scythe_threat.json
    * https://github.com/scythe-io/community-threats/blob/master/CozyBear/CozyBear-Step2_scythe_threat.json 
2. Go to the Threat Catalog and select "CozyBear-Step1"
3. Click "Create Campaign from Threat"
4. Name the Campaign
5. Parameters: Replace unicorn.scythedemo.com with your SCYTHE instance IP address or FQDN.
4. Launch the Campaign
5. Execute via an EXE
6. Perform steps 2-5 again for the threat "CozyBear-Step2"
