---
created: 2026-06-19T15:04:10.758103+00:00
updated: 2026-06-19T15:12:01.673726+00:00
concepts:
- ISPEC
- Layer 1 verification
- MoP
entities:
- EX4400
- ISE
- JSI
- Juniper Service Manager
- Junos
- Kirke
- S2i
- SMARTS
- SNM
- SNMPv3
- Verizon
title: Verizon Route/Switch Layer 1 Tasks
indexes:
- '[[Team Index]]'
- '[[Verizon Migration Procedures]]'
- '[[Verizon Process 101]]'
description: Checklist for Verizon route/switch Layer 1 readiness tasks, including ISPEC/MOP preparation, device configuration, hardware and software verification, monitoring/access updates, connectivity checks, and migration-readiness handoff.
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-19T15:04:10.758103+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 1970,
      "inputPath": "/Users/drhoades/VaultRaw/layer1_tasks.pptx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/layer1-tasks-1781881450769397000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-19T15:04:10.758103+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "powerpoint",
  "sourcePath": "/Users/drhoades/VaultRaw/layer1_tasks.pptx",
  "sourceSha256": "ac977bdc69f100dc0fa6e0d0d1170d61f7be461de98227d23315909a2f21a51b"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

A PowerPoint-derived checklist for Verizon route/switch Layer 1 readiness tasks, covering ISPEC download, base configuration, console and SSH access, hardware and Junos checks, archival, ISE/S2I/SMARTS/SNM/JSI updates, legacy-device KIRKE handling, connectivity verification, and final notification/documentation steps.
<!-- wikiagent:agent-summary:end -->

Verizon Route/Switch Layer 1 Tasks

- Triggered by notification from Verizon Engineering regarding device readiness for Layer 1 verification 
- MOP available at Layer 1 MOP
- 
- Download relevant ISPEC 
- Create “non service-impacting” KIRKE for legacy devices
- Usually auto-approved 
- Create base configuration utilizing relevant templates and ISPEC input (D1 and D2)
- IP addresses/backup router/default route/hostnames/management interface configurations

Verizon Route/Switch Layer 1 Tasks  -  cont’d

- Login to new devices using console connections specified in ISPEC (Tab D1) 
- Add basic connectivity configuration for management interfaces and associated static route to default gateway (ISPEC Tab D2) along with “Juniperps” userid and credentials 
- Verify SSH login capability (may need root-login permission) 
- Extract hardware layout “show chassis hardware | display xml | no-more” (required for service contract) 
- Verify software version in all devices and update as necessary (code is available on jump servers)
- If EX4400, double-check firmware version  EX4400 Revision
- 

Verizon Route/Switch Layer 1 Tasks  cont’d

- Update base configurations as per relevant templates
- SNMPv3 idiosyncrasy requires second commit (use cleartext)
- Archive server setup requires additional step and may also require addition of appropriate directory folder on backup server 
- Verify device archival is operational as expected by checking server files 
- Verify NTP synchronization 
- Add new devices to S2I filter “ISNTS\_IPCOMM\_Not Paged”  
- Add new device details to ISE environment and verify access

Verizon Route/Switch Layer 1 Tasks  cont’d

- Verify expected hardware build (Layer 1 MOP)
- Reference ISPEC, LLD and existing legacy equipment connections
- Linecards and common components
- Transceivers (optics, UTP and serial if applicable)
- Note that often XFP transceivers in legacy gear are re-purposed from unused connections rather than new 
- Open the “non service-impacting” KIRKE for legacy devices
- 
- Verify available connections
- Crossover connections between new devices
- Connections between new devices and legacy gear
- Ensure that all links on legacy gear activated for this task are returned to original state when done
- Verify no outstanding alarms for legacy gear per S2I
- No verification possible for currently active connections (uplinks/edge equipment etc) 
- Close Kirke when done 
- Reply to original email with success/fail results of verification
- Issues encountered will necessitate site work and re-check of all interfaces as noted above

Verizon Route/Switch Layer 1 Tasks  cont’d

- Send notification to relevant Verizon staff to add/verify access for new devices from SMARTS and SNM
- Currently smarts-voip-dev@Verizon.com and matthew.trostel@verizon.com
- Confirmation from both required within 2 weeks
- Note that typically issues with SMARTS access is due to SNMPv3 configuration problems while SNM access requires correct ISE function
- 
- Send email to Verizon staff confirming that archival of new device configurations is operational
-  
- Send copies of XML hardware extract to Juniper Service Manager
- Include site address detail from ISPEC 
- Add new device details to JSI environment
- 
- Ensure that appropriate project management directed documentation updates are completed – the site should now be ready for migration tasks
- Site Checklist

- Email messages should include all relevant PS staff 
- An example of a new equipment table template for emails to Verizon is shown below:

| Hostname       | Management IP   | Rack Location   | Serial Number   |
|----------------|-----------------|-----------------|-----------------|
| tessn1mr01-vip | 63.39.36.92     | --              | --              |
| tessn1mr01-re0 | 63.39.36.90     | 51.13 23        | JN12788C9AFA    |
| tessn1mr01-re1 | 63.39.36.91     | 51.13 23        | JN12788C9AFA    |
| tessn1mr02-vip | 63.39.36.95     | --              | --              |
| tessn1mr02-re0 | 63.39.36.93     | 51.11 23        | JN1276B57AFA    |
| tessn1mr02-re1 | 63.39.36.94     | 51.11 23        | JN1276B57AFA    |

Verizon Route/Switch Layer 1 Tasks  Notes

Verizon Route/Switch Layer 1 Cheat Sheet

1. Download relevant ISPEC
2. Login to new devices via consoles
3. Verify hardware build matches requirements
4. Update configuration to enable SSH connectivity
5. Update Junos as required
6. Load base configuration to new devices and verify operation
7. Add new device information to ISE and verify operation
8. Verify configuration archival is operational and email Verizon staff
9. Email Verizon SNM and SMARTS staff to add/verify new device connections (14 day window for replies)
10. Extract chassis hardware information (XML format) and send to Juniper SM
11. Open “non service-impacting” KIRKE for legacy devices
12. Verify all available connectivity between new nodes and to legacy devices
13. Email reply to Layer 1 trigger email with results
14. Re-check all interfaces if issues found in Step 11 are resolved and email results again
15. Update JSI (just the VIP address)
16. Update project management directed documentation

## Related

- [[sources/verizon-process-101-mop-cutsheet-creation-transcript|Verizon Process 101: MOP and cut sheet creation transcript]]
- [[sources/verizon-process-101-mw-process-prechecks-migration-and|Verizon Process 101: Maintenance-window pre-checks, migration, and post-checks]]
- [[sources/verizon-process-101-milestones-gates-prerequisites-resha-transcript|Verizon Process 101: Milestones, Gates, and Prerequisites]]

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-19T15:13:55.235879+00:00",
      "canonicalTerm": "Juniper Service Manager",
      "reviewCardId": 217,
      "term": "Juniper SM"
    }
  ]
}
-->
