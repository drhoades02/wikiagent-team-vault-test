---
title: GNJSN1
created: 2026-06-18T20:16:37.776636+00:00
updated: 2026-06-18T20:16:37.776636+00:00
concepts:
- 10Gb
- 1st Gen SN
- Firewall VIP
- Gen 2.7 GNJSN1MR01/MR02
- In-Production US
- Path2 - Router-Replace 2.7
- SIDA Install
entities:
- GNJSN1
- Kernersville
- MX960
- NC
- Neptunes
- SPIP7-8
- SRX4600
facets:
- Retain
indexes:
- '[[VOIP Nodes]]'
description: In-production US VOIP node GNJSN1 in Kernersville, NC, with 1st Gen SN node type, MX960 router, 10Gb bandwidth, SRX4600 firewall, SPIP7-8 VSN type, management VIPs, and Gen 2.7/Neptunes migration planning.
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-18T20:16:37.776636+00:00",
  "conversion": {
    "converter": null,
    "detail": null,
    "required": false,
    "status": "skipped"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-18T20:16:37.776636+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "markdown",
  "sourcePath": "/Users/drhoades/Library/CloudStorage/OneDrive-Personal/work docs/VOIP-Nodes/nodes/GNJSN1.md",
  "sourceSha256": "10e6832cd5b002a8bf4b423c565d5737f5841342a160b064659f8e4bf2b17fcb"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

GNJSN1 is an in-production US VOIP node in Kernersville, NC, with a 1st Gen SN node type, Path2 Router-Replace 2.7 evolution path, MX960 router, 10Gb bandwidth, SRX4600 firewall, SPIP7-8 PIP VSN type, SIDA Install IDA1 status, management VIPs, and planning to migrate Neptunes from GNJSN2 while retaining the node.
<!-- wikiagent:agent-summary:end -->

# GNJSN1

## General

| Field | Value |
| --- | --- |
| NODE | GNJSN1 |

## NODE INFO

| Field | Value |
| --- | --- |
| City | Kernersville |
| State/Co | NC |
| Production/Lab | In-Production US |
| Node Type | 1st Gen SN |
| Node Evolution Path | Path2 - Router-Replace 2.7 |
| Router | MX960 |
| Bandwidth | 10Gb |
| Firewall Type | SRX4600 |

## VSN TYPES

| Field | Value |
| --- | --- |
| PIP (FW/ACL/Both) | SPIP7-8 |
| IDA1 | SIDA Install |

## Management IPs

| Field | Value |
| --- | --- |
| Router1 VIP | 166.34.60.197 |
| Router2 VIP | 166.34.60.218 |
| FW VIP | 166.34.2.160 |

## Node/Site Planning

| Field | Value |
| --- | --- |
| Node Evol Step 1 | Gen 2.7 GNJSN1MR01/MR02 |
| Node Evol Step 2 | Migrate Neptunes from GNJSN2 |
| Node Evol Step 3 | - |
| Node Evol End View | Retain |

## Related

- [[sources/norsn1|NORSN1]]
- [[sources/rcnsn2|RCNSN2]]
