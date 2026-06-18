---
title: SEJSN1
created: 2026-06-18T20:17:43.215814+00:00
updated: 2026-06-18T20:17:43.215814+00:00
concepts:
- 1st Gen SN
- Firewall VIP
- In-Production US
- Path2 - Router-Replace 2.7
- SIDA Install
entities:
- Kent
- MX960
- SEJSN1
- SPIP7-8
- SRX4600
- Util Server VM
- WA
facets:
- Retain
indexes:
- '[[Team Index]]'
- '[[VOIP Nodes]]'
description: SEJSN1 is an in-production US VOIP node in Kent, WA, with 1st Gen SN node type, MX960 router, 10Gb bandwidth, SRX4600 firewall, SPIP7-8 PIP VSN type, and retain planning after Gen 2.7 migration.
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-18T20:17:43.215814+00:00",
  "conversion": {
    "converter": null,
    "detail": null,
    "required": false,
    "status": "skipped"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-18T20:17:43.215814+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "markdown",
  "sourcePath": "/Users/drhoades/Library/CloudStorage/OneDrive-Personal/work docs/VOIP-Nodes/nodes/SEJSN1.md",
  "sourceSha256": "be8992e591e39b5507bde34eca465d2e23b8cf86926a9a9bd8c22f2b936d0936"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

SEJSN1 is an in-production US VOIP node in Kent, WA, with 1st Gen SN node type, Path2 Router-Replace 2.7 evolution path, MX960 router, 10Gb bandwidth, SRX4600 firewall, SPIP7-8 PIP VSN type, SIDA Install for IDA1, Util Server VM ping poller, router/firewall VIPs, and planning to move to Gen 2.7 SEJSN1MR01/MR02 while retaining the node.
<!-- wikiagent:agent-summary:end -->

# SEJSN1

## General

| Field | Value |
| --- | --- |
| NODE | SEJSN1 |

## NODE INFO

| Field | Value |
| --- | --- |
| City | Kent |
| State/Co | WA |
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
| Ping Poller | Util Server VM |

## Management IPs

| Field | Value |
| --- | --- |
| Router1 VIP | 166.33.34.43 |
| Router2 VIP | 166.33.34.46 |
| FW VIP | 63.39.195.204 |

## Node/Site Planning

| Field | Value |
| --- | --- |
| Node Evol Step 1 | Gen 2.7 SEJSN1MR01/MR02 |
| Node Evol Step 2 | - |
| Node Evol Step 3 | - |
| Node Evol End View | Retain |

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-18T20:18:41.769091+00:00",
      "canonicalTerm": "Node Evolution",
      "reviewCardId": 160,
      "term": "Node Evol"
    }
  ]
}
-->

## Related

- [[sources/norsn1|NORSN1]]
- [[sources/rcnsn2|RCNSN2]]
