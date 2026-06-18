---
title: IDCSN1
created: 2026-06-18T20:13:40.678420+00:00
updated: 2026-06-18T20:13:40.678420+00:00
concepts:
- 10Gb
- 1st Gen SN
- In-Production US
entities:
- IDCSN1
- IDCSN4
- Independence
- MO
- MPC7E
- MX960
- SPIP7-8
facets:
- Decommission
- Path3 - Migrate to 2.0 Colo
indexes:
- '[[Team Index]]'
- '[[VOIP Nodes]]'
description: IDCSN1 is an in-production US VOIP node in Independence, MO, with 1st Gen SN node type, MX960 router, SPIP7-8 VSN type, router VIPs, and a plan to migrate SPIP7_8 to IDCSN4 before decommissioning IDCSN1.
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-18T20:13:40.678420+00:00",
  "conversion": {
    "converter": null,
    "detail": null,
    "required": false,
    "status": "skipped"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-18T20:13:40.678420+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "markdown",
  "sourcePath": "/Users/drhoades/Library/CloudStorage/OneDrive-Personal/work docs/VOIP-Nodes/nodes/IDCSN1.md",
  "sourceSha256": "9dfb9d0ca16349a38e3428a06f3d6c073def0e71b47fbebc7aacd5f6d8f9380c"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

IDCSN1 is an in-production US VOIP node in Independence, MO, using a 1st Gen SN node type, MX960 router, 10Gb bandwidth, SPIP7-8 VSN type, router VIPs, and a migration/decommission plan involving IDCSN4.
<!-- wikiagent:agent-summary:end -->

# IDCSN1

## General

| Field | Value |
| --- | --- |
| NODE | IDCSN1 |

## NODE INFO

| Field | Value |
| --- | --- |
| City | Independence |
| State/Co | MO |
| Production/Lab | In-Production US |
| Node Type | 1st Gen SN |
| Node Evolution Path | Path3 - Migrate to 2.0 Colo |
| Router | MX960 |
| Bandwidth | 10Gb |

## VSN TYPES

| Field | Value |
| --- | --- |
| PIP (FW/ACL/Both) | SPIP7-8 |

## Management IPs

| Field | Value |
| --- | --- |
| Router1 VIP | 166.46.115.134 |
| Router2 VIP | 166.46.115.137 |

## Node/Site Planning

| Field | Value |
| --- | --- |
| Node Evol Step 1 | Upgrade IDCSN4 with MPC7E |
| Node Evol Step 2 | Migrate SPIP7_8 to IDCSN4 |
| Node Evol Step 3 | Decomm IDCSN1 |
| Node Evol End View | Decomm |

## Related

- [[sources/norsn1|NORSN1]]
- [[sources/rcnsn2|RCNSN2]]

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-18T20:14:48.112623+00:00",
      "canonicalTerm": "SPIP7-8",
      "reviewCardId": 124,
      "term": "SPIP7_8"
    },
    {
      "appliedAt": "2026-06-18T20:14:48.226325+00:00",
      "canonicalTerm": "Decommission",
      "reviewCardId": 125,
      "term": "Decomm"
    }
  ]
}
-->
