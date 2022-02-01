# Buhtrap Adversary Emulation Plan

This threat is explained further in SCYTHE's Threat Thursday blog: https://www.scythe.io/library/threatthursday-buhtrap

There is also a walkthrough video by our CTO, Jorge Orchilles: https://vimeo.com/427717937

Threats for both DNS and HTTPS communication protocols are provided. HTTPS is used for Initial Access and Collection, and DNS is used for long-term Persistence.

## Instructions

1. Download and import the threats in JSON format to your SCYTHE instance
    * HTTPS: https://github.com/scythe-io/community-threats/blob/edits/Buhtrap/Buhtrap-HTTPS_scythe_threat.json
    * DNS: https://github.com/scythe-io/community-threats/blob/edits/Buhtrap/Buhtrap-DNS_scythe_threat.json
2. Go to the Threat Catalog and select "Buhtrap"
3. Click "Create Campaign from Threat"
4. Name the Campaign
5. Parameters: Update the parameters to provide your SCYTHE server IP address or domain
4. Launch the Campaign
5. Execute via an EXE
