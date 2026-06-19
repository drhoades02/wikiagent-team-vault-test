---
title: RCNSN2
created: 2026-06-18T20:07:03.563010+00:00
updated: 2026-06-18T20:07:03.563010+00:00
concepts:
- 2nd Gen SN
- In-Production US
- PathB
- PVGs
- VSN
entities:
- C20
- G9x2
- MX960
- Neptunes
- RCNSN1
- RCNSN2
- Richardson
- Texas
indexes:
- '[[Team Index]]'
- '[[VOIP Nodes]]'
description: RCNSN2 is an in-production second-generation SN in Richardson, TX with MX960 routing, VSN type details, management VIPs, and node migration/decommission planning.
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-18T20:07:03.563010+00:00",
  "conversion": {
    "converter": null,
    "detail": null,
    "required": false,
    "status": "skipped"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-18T20:07:03.563010+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "markdown",
  "sourcePath": "/Users/drhoades/Library/CloudStorage/OneDrive-Personal/work docs/VOIP-Nodes/nodes/RCNSN2.md",
  "sourceSha256": "53e38d9b11f072dbc7f8c402866c3828a70953e91f0d5194bd30121d6bb960f4"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

A structured node inventory record for RCNSN2, an in-production second-generation SN in Richardson, TX, including router type, VSN types, management VIPs, and node evolution/decommission planning.
<!-- wikiagent:agent-summary:end -->

# RCNSN2

## General

| Field | Value |
| --- | --- |
| NODE | RCNSN2 |

## NODE INFO

| Field | Value |
| --- | --- |
| City | Richardson |
| State/Co | TX |
| Production/Lab | In-Production US |
| Node Type | 2nd Gen SN |
| Node Evolution Path | PathB - Migrate 2.0 VSN to Colo SN 2.7 |
| Router | MX960 |

## VSN TYPES

| Field | Value |
| --- | --- |
| LD C20 | C20 - C |
| LD G9 | G9x2 - C |
| LCL C20 | C20 - E |
| LCL G9 | G9x2 - E |

## Management IPs

| Field | Value |
| --- | --- |
| Router1 VIP | 146.170.214.230 |
| Router2 VIP | 146.170.214.233 |

## Node/Site Planning

| Field | Value |
| --- | --- |
| Node Evol Step 1 | Migrate to Neptunes/vC20/G9 |
| Node Evol Step 2 | Migrate Neptunes to RCNSN1 |
| Node Evol Step 3 | Retain with PVGs |
| Node Evol End View | Decomm after PVG migrations |

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-18T20:07:51.707567+00:00",
      "canonicalTerm": "Texas",
      "reviewCardId": 58,
      "term": "TX"
    },
    {
      "appliedAt": "2026-06-18T20:07:51.737060+00:00",
      "canonicalTerm": "G9x2",
      "reviewCardId": 59,
      "term": "G9"
    }
  ]
}
-->
