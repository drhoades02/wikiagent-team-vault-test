---
created: 2026-06-16T04:53:36.994311+00:00
updated: 2026-06-16T05:00:28.279152+00:00
concepts:
- Gen. 2.7
- Low Level Design
- SPIP 7/8
- Verizon Process 101 Low Level Design Review (SPIP7-8)
- Virtual Service Node
- VoIP infrastructure VPN
entities:
- AS701
- Broadsoft
- Don Nguyen
- Gery Czirjak
- Hassan Rauf
- IDNKR
- James Erickson
- Mohan Kanumuru
- MX104
- MX960
indexes:
- '[[Verizon Low Level Design Reviews]]'
description: Transcript of a November 26, 2025 Verizon Process 101 session on reading and reviewing SPIP7-8 low-level design documents, including Gen. 2.7, VSNs, Broadsoft, routing instances, VLANs, and firewall behavior.
source: /Users/drhoades/VaultRaw/Verizon Process 101_ Low Level Design Review (SPIP7-8) Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-16T04:53:36.994311+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 4181,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Low Level Design Review (SPIP7-8) Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-low-level-design-review-spip7-1781585617081931000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-16T04:53:36.994311+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Low Level Design Review (SPIP7-8) Transcript.docx",
  "sourceSha256": "7bcf13577f296157de6049f96b1f7abb74b53ab4de33470bd323049f5760176e"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Meeting transcript for “Verizon Process 101 Low Level Design Review (SPIP7-8)” covering how to find, interpret, and validate Verizon LLDs, especially SPIP/Broadsoft VSN designs, Gen. 2.7 migrations, MX960/MX104 topology, routing instances, VLANs, firewall/ACL behavior, and related terminology.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 Low Level Design Review (SPIP7-8)-20251126\_110314-Meeting Recording**

November 26, 2025, 6:03PM

2h 3m 45s

<!-- image -->

**Czirjak, Gery** 0:03
My dreams.

<!-- image -->

**Erickson, James** 0:05
It will.
No.
OK, I started recording.
Um.
That's not gonna work.
This is in the um.
Which isn't one of the shared drives or something that's shared with you.

<!-- image -->

**Czirjak, Gery** 1:02
No, the thing I threw up. No, that's just our shared drive. It's a design docs file or folder, I should say.
We should all have that. That's I'm getting a via my HP user.
Which incidentally, I don't know if you noticed, doesn't work with nats.

<!-- image -->

**Kanumuru, Mohan** 1:26
I'm able to get there.
So I'm just curious why it is called SPIP 7/8, the title of the 101 today.
Is it Gen. 5, Gen. 7, Gen. 2? So there is a Gen. 8.

<!-- image -->

**Erickson, James** 1:54
No. Um.
So SPIP seven and eight.
Um.

<!-- image -->

**Czirjak, Gery** 2:07
They're just VSNS, Mohan.

<!-- image -->

**Kanumuru, Mohan** 2:11
OK.

<!-- image -->

**Erickson, James** 2:12
Yeah.

<!-- image -->

**Czirjak, Gery** 2:12
I guess pip one through 5.

<!-- image -->

**Kanumuru, Mohan** 2:15
OK, so it's nothing to do with the Gens 2.7, Gen. 2.5, Gen. 2. OK, I mistook five and seven as though it's Gen. 2.7. OK, so there are.
SP 7-8 OK that that help. Thank you.

<!-- image -->

**Czirjak, Gery** 2:40
Yeah, I think didn't Nick, didn't Nick do a 27 node already? Wasn't DNG a 27 node and I think it had skip on it even, right?

<!-- image -->

**Kanumuru, Mohan** 2:49
OK.
Yes, it one node got done, yeah.

<!-- image -->

**Czirjak, Gery** 2:56
That's just another VSN.
I should shut up. Sorry, James.

<!-- image -->

**Erickson, James** 3:02
No, you can speak and.
Um.
Still trying to find.
How to get this shared out? Um.

<!-- image -->

**Kanumuru, Mohan** 3:23
So I can I you want me to open the file and share my screen James? I'm able to get to that Gen. 2.7 DPC uplift SP 7/8 Gen. 2.7 file.

<!-- image -->

**Erickson, James** 3:37
No, I got it.

<!-- image -->

**Kanumuru, Mohan** 3:38
LL V4V49.

<!-- image -->

**Erickson, James** 3:42
You guys seeing my browser here?

<!-- image -->

**Kanumuru, Mohan** 3:48
Yes.

<!-- image -->

**Erickson, James** 3:50
OK.
No.
So.
What happened is the the Gen. 2.5.
I um.
Do we have SPIP 7/8 VSNS on a Gen. 2.5 or is that all on Gen. 2.7?

<!-- image -->

**Czirjak, Gery** 4:20
I'm not sure.

<!-- image -->

**Kanumuru, Mohan** 4:21
Yeah, baby.

<!-- image -->

**Erickson, James** 4:21
Was Nick? Was Nick gonna join us?
Um.

<!-- image -->

**Kanumuru, Mohan** 4:29
Yeah, maybe it's.

<!-- image -->

**Erickson, James** 4:45
O the base.

<!-- image -->

**Czirjak, Gery** 4:48
I'll have a quick look in Travis' summary.

<!-- image -->

**Kanumuru, Mohan** 4:58
Well, let's let's ask Gemini in the in the Google Drive.
SPIP 7.
Where is Gemini here? Is there any way I can get to Gemini here?
I think we can assume that it's at at least for now it's not there, it's only 2.7.

<!-- image -->

**Erickson, James** 5:48
Yeah, this is.

<!-- image -->

**Kanumuru, Mohan** 5:48
LLD.

<!-- image -->

**Erickson, James** 5:51
So most of these should have a lot of recorded sessions from, you know, um.
And and these LLDs, LLDs, they do.
I think they've lately taken to.
Making them piecemeal. Um.
Like every VSN has its own LLD like a Cedar.
RSIDALLD.
So that's probably the first challenge and once you get here.
Um.
uh deciding which of these is applicable to you any um

<!-- image -->

**Don Nguyen** 6:44
So, so James, I have a question. What are the tiebreaker between site? What are the main variation of different? Is it the line call or just the the architecture or the circuit size?

<!-- image -->

**Erickson, James** 6:56
So.
Anything that says micronode is an MX104, we probably won't be doing anything with those. PIP Bridging is an MX104 with EX4400s probably won't have any more of those to do.
Erickson Engine only had three sites, so we won't be doing any of those. Well, actually we do have two more sites of those we have to migrate early next year and then one gig signaling was MX104 with um EX4400s in a virtual chassis. So yeah, you're pretty much only looking at.
Most of our business as usual work in the coming year. We might not have so much 2.5 to do, but a lot of 2.7.

<!-- image -->

**Kanumuru, Mohan** 7:48
27.

<!-- image -->

**Don Nguyen** 7:51
27.
2.7 is the MX 960 with the latest Uh Uh line card, right?

<!-- image -->

**Erickson, James** 8:00
Yeah, the 960 with the it's only got the 248 port or is it 48 or is it? How many ports are on those?

<!-- image -->

**Don Nguyen** 8:09
Yeah, what I I'm not writing slot night 11 and 12. What are you talking about? You know that 1011? Yeah.
Usually 40.

<!-- image -->

**Erickson, James** 8:12
40.
Uh, 10 and 11? Yeah, yeah. Um.

<!-- image -->

**Czirjak, Gery** 8:21
By the way, SPIP 7 and eight is all over the place. I found it in Gen. twos, Gen. ones. It's all over the place.

<!-- image -->

**Erickson, James** 8:27
Oh yeah, mainly what they are talking about is the the.
The hardware behind and the topology, a lot of it's the configuration.
Standards that get upgraded as things go along.
as no hardware is introduced, and and that kind of thing, as they do some optimization in their design. Um, they they may call for
Um.
You know, a new Gen.
Designation, but right now the current one is 2.7 with those MPC.
Uh, seven cards.
And and of course you know the topology that goes along with that, the all SFP connections.
And.
Uh, 10 gig or 40 gig? Um.
So.
I don't know that they'll be upgrading any of their new Gen. or any of their old Gen. ones to Gen. 2.5, or directly take them to 2.7, I think. Um.
Um.
It really depends when you when you look at the.
Um, a new ice back, right? Or a new site that's in the plan. They should be calling out from the get go whether this is going to be a Gen. 2.5.
Migration or Gen. 2.7 migration that that's the first decision they're going to be making and I think now that 2.7 is in production and as as fast as we can get it all.
Certified for all the different VSNS. This is going to be the one we're going to be seeing most in rest of network. The Gen. 2.5 went through all the certifications in the last two years and then last year got put into production.
But I don't think they're going to be rolling out any new stuff unless they absolutely have to. Otherwise they're waiting for Gen. 2.7 certification in the lab before they can roll out VSNS onto this beyond what we've already done.
Does that make sense?

<!-- image -->

**Don Nguyen** 11:21
Yeah, yeah.

<!-- image -->

**Erickson, James** 11:23
OK, so they they.

<!-- image -->

**Don Nguyen** 11:25
Yeah, I don't know about Hassan for me, but before this I had a hard time differentiate between the IDA, micro and stuff. I just it didn't click, you know what I'm saying? So that mean the 104, yeah, I just.

<!-- image -->

**Erickson, James** 11:38
Yeah, like I said.

<!-- image -->

**Hassan Rauf** 11:40
Yeah.

<!-- image -->

**Erickson, James** 11:42
Yeah, yeah. Like I said, the because you're doing a lot of different stuff like with the firewall upgrades and the MX104 upgrades. I don't know if you've been upgrading the axes as well.

<!-- image -->

**Hassan Rauf** 11:43
You know.

<!-- image -->

**Erickson, James** 11:58
But other side you know.
Um.
Upgrades might have gone back and revisited some of these things, but for migration purposes, and I think that's where we really need to focus most of these lunch and learns.
Is on the migration process because just an upgrade.
Um, I mean.
It's It's not going to be or or maintenance, or whatever, and you know I don't think you'll be seeing many of these other ones. Uh. Oh, God, that's like a
Uh.
Curious case, we we built it out like it's.

<!-- image -->

**Don Nguyen** 12:53
Why do they call Ericsson engine to connect to a Nokia Siemens router or something on the other side? What do they call Ericsson engine? I'm just curious.

<!-- image -->

**Erickson, James** 13:04
Yeah, it's an Ericsson brand. Um.
Uh.
Platform, you know, um.
I'm trying to remember the designations for it. Um.
Honestly.
I'd almost think it you'd be better off not.
Um.
Not concerning yourself. We've already done all the LLDS layer one I spec reviews and all of that for these.
These Ericsson engines.
and there's only 3 of them, so I don't think we'll get any benefits from following um
Some of these.
You know, learning more about this, this architecture. We even have the MOPs and cut sheets done for most of these, I think.
I'm trying to the the core routing and uh platforms in the Ericsson engine site was um.
A This doesn't look right. Wasn't it 7613 or 7?
Anyway, um, and you know, for example, they had a one.
An OC48.
Connecting to oh, that's right. Yeah, the MX960 replaced old 76 thirteens is what this was saying. That's what I passed here.

<!-- image -->

**Don Nguyen** 15:18
Got it. So OK, so Ericsson engine basically before is a Cisco 7613. Is that what the the the the the slang come from Ericsson engine?

<!-- image -->

**Erickson, James** 15:19
Um.
Yeah, well, no, the Ericsson engine is actually part of this. The service is provided beyond the route core, the the routing platforms, the Ciscos were kind of routing aggregators or.

<!-- image -->

**Hassan Rauf** 15:32
Oh.

<!-- image -->

**Erickson, James** 15:47
Aggregate aggregating routers. Sometimes they refer to them as a R routers. That's what you'll see that in the lab in the Ericsson engine. They're named a Rs.

<!-- image -->

**Don Nguyen** 15:58
OK, OK.

<!-- image -->

**Czirjak, Gery** 16:03
So Don, I I would agree with James that this isn't worth a lot of trouble of looking at this, but view the EE as just another variation of an SBC.

<!-- image -->

**Erickson, James** 16:04
But.

<!-- image -->

**Don Nguyen** 16:07
OK.
Got it. OK.

<!-- image -->

**Erickson, James** 16:15
Yeah. Um.

<!-- image -->

**Czirjak, Gery** 16:17
Really all it is.

<!-- image -->

**Erickson, James** 16:19
Yeah.

<!-- image -->

**Czirjak, Gery** 16:19
What's the one we're struggling with now? The the sonus one? It's just another SBC.

<!-- image -->

**Don Nguyen** 16:26
They have Sonus also.

<!-- image -->

**Erickson, James** 16:27
Yeah.

<!-- image -->

**Czirjak, Gery** 16:28
Yeah, they everything under the sun probably, right?

<!-- image -->

**Don Nguyen** 16:31
Crap, because Sonus is a company right across the street from the 12/1 headquarter. I mean right across the street.

<!-- image -->

**Erickson, James** 16:39
I wonder if this is an opportunity.

<!-- image -->

**Czirjak, Gery** 16:40
Well, you'll hear the name Ribbon a lot, right? And Ribbon ate Sonus, I believe, and they use a lot of Ribbon stuff.

<!-- image -->

**Don Nguyen** 16:46
Yeah.

<!-- image -->

**Czirjak, Gery** 16:49
I'll shut up.

<!-- image -->

**Erickson, James** 16:50
Mhm.
Don't.

<!-- image -->

**Don Nguyen** 16:52
Yeah, I don't. James hadn't been here yet, right? But Sonus is right across the street, a big building with a big sign Sonus.

<!-- image -->

**Erickson, James** 16:58
Yeah, I've no, I've been down there a few times and I think I remember seeing it. Um.

<!-- image -->

**Don Nguyen** 17:00
Oh yeah, yeah.
And I know Acme Packet and Broadsoft is out of Colorado or somewhere Denver.

<!-- image -->

**Erickson, James** 17:10
Yeah.
Um.
The 2.5 routers.
Um.
They're actually when you are.
Since we're talking about these.
how to read or how to analyze these LLDs. It's
Definitely.
Um.
Worthwhile to.
Remember these recorded sessions? Um.
The uh where we have them.
It really does help to.
Um have.
You know that that refresher of, yes, this question's probably been asked before about a certain LLD, you know, a certain technical point in the LLD that.
We've discussed with and we definitely want you to, before asking it again on another call, go back through the recorded sessions and.
Uh.
And talk with, you know, me, Nick or Gary or if we have any input as well, if what we remember about it. But so the first thing is, you know, there's a base design.
And then there's a design where they exclude the base.
Components and focus on specifically a Broadsoft VSN and NSRSVSN or the OCAS VSN or the PIP VS NS SPIP VS NS.
Um, I pack.
We'll have a few of those. Um.
I think this is a pretty complete list. This is all the different types of ESNS.
For these, um.
And they're relatively new. Some of these are pretty old.
But uh.
VPC migration.
See what we have in here.
Oh.
Yeah, this is one of the.
Um.
Um.
When we before we even get to this.
And I spec, you know, we.
Are asked to.
Put together a bill of materials or and a purchase order for all four things. And so you might be asked or or project management might be able to handle this on their own, but you might be asked to go through and you know.
Count cards and.
The XF PS and SF PS are also really big sticking points for these even at this stage because we can go months and months between an actual migration.
After we've done.
Um.
Uh, an order and if the topology is changed or the LLD is changed, um, then we have to go back and.

<!-- image -->

**Don Nguyen** 21:18
Remind me the XFP, is it a fat thing when nobody use anymore? XFP is it a fat nobody use anymore, right?

<!-- image -->

**Erickson, James** 21:25
Yeah, it's a little bit not as fat as a GBIC, but fatter than a SFP.

<!-- image -->

**Don Nguyen** 21:32
Yes, yeah, yeah, yeah.

<!-- image -->

**Erickson, James** 21:34
Yeah, where where a GBIC will be as wide as the length of your thumb, XFP will be as wide as the width of your thumb. Umm

<!-- image -->

**Don Nguyen** 21:47
Yeah, yeah, alright.
I didn't know you people are still using those kind of uh uh form factor.

<!-- image -->

**Erickson, James** 21:51
So.
Yeah, and that goes, that's it's totally a thing. And they still have GBICs in production too, so.

<!-- image -->

**Don Nguyen** 22:06
Right.

<!-- image -->

**Erickson, James** 22:16
The uh.
MOP for Okay, this is an example. MOP for to BFD with LAG on VoIP routers. I think this is a MOP. Umm

<!-- image -->

**Kanumuru, Mohan** 22:44
Now where does the information about which ports are reserved or standardization wise both for the up links, cross connects and access?

<!-- image -->

**Erickson, James** 22:57
Well, that's the curious thing about these LLD's is they don't necessarily give.
Port identifiers and go into the weeds as far as any kind of useful information which port it should be on.
Um.

<!-- image -->

**Don Nguyen** 23:19
You mean the AE100AE0? Those are not in LLD.

<!-- image -->

**Erickson, James** 23:20
But.
Yeah.
Well, they'll they'll specify like here that there's supposed to be a lag, you know, with X number of member links.
My gosh, he's got comments back to 2020 on here and it's impossible to read. And this isn't the first time anybody will say that these LLDs are impossible to read. This is why we're kind of having this call is to.
Making you aware that these will be challenging. You know, even working with these LLDs is going to be challenging because.
They.
Like to track and comment the heck out of these.
Um.
And.
You just gotta kinda work around that unless you're saving a local copy and turning off the track changes. Um.
The uh.
And and hope the the conversion from a Google Sheets Word document to a a Microsoft Word document doesn't.
Screw it all up to make it unreadable or put in old changes or whatever, right? So there's, you know, just working with these documents is gonna be a challenge. Um.
The uh.
Let's see. Current list includes IP IVR. So there are other services VSNS like this IP IVR, I skip, D skip.
You know, these are coming down.
Um. In fact, I think it's the I skip specifically that uses those Sonas.
Um, SPCS. I'm not sure about the DSCIP, but that's what the LLD is for. We'll find out.
These are international skip services. These are domestic, you know, within the US skip services.
Um.

<!-- image -->

**Kanumuru, Mohan** 26:10
Those are all, those are all routing instances, logical, logical instances now.

<!-- image -->

**Erickson, James** 26:21
No, they.
Uh.
Just in terms of VSN, right, the kind of devices that we're supporting, they don't necessarily get their own logical system, but they'll they'll most they'll likely.
Share the common resources, the CRVR routing instance with other VSNS. That's that's the new model is to instead of having the routing tables separated by VSN.
The each VSN if if you're working, if you're working on node that shares has multiple VS NS on it, then they'll share. They should be sharing a routing table in the common or common resources.
Routing instance if they if they need a routing table of their own for their own topology, like after it's been inspected to after a traffic flow has been inspected by the firewall for example, or for specialized routing purposes.
Yeah, we will put those routing tables in their own routing instance.
Um, but not every VSN uses their own routing instance, and that would only be on the trusted side of the firewall, not on the untrusted on the untrusted side of the firewall we're likely looking at. Um.
The the the CRV CR1 VR routing instance.
Um.
Infrastructure elements. Let's see.

<!-- image -->

**Kanumuru, Mohan** 28:22
Is VSN stands for voice service node or what?

<!-- image -->

**Erickson, James** 28:27
Virtual service node.

<!-- image -->

**Kanumuru, Mohan** 28:29
Virtual service node?

<!-- image -->

**Erickson, James** 28:31
Yeah.
Uh, this is still just in in introduction stuff. Um.
The.

<!-- image -->

**Don Nguyen** 28:56
So James, so for for practical purpose, all these voice stuff on the trusted side.
The only on the untrusted side from a security point of view is the the VPN people come in from 701 right from outside that's that's it right. From our perspective it's just from the routing switching perspective it's just matter of how the logical system is shared you know or the routing is shared right between those.
Variation of design, right? But they are on the trusted side from Azure X point of view, right? Security.

<!-- image -->

**Erickson, James** 29:26
Yeah.
Well, from the SRX point of view, the security, the untrusted is facing AS701 because yeah, because that that MPLS network has.

<!-- image -->

**Don Nguyen** 29:37
701, yeah, 701, yeah, the VA router, that's what coming in, right?

<!-- image -->

**Erickson, James** 29:45
Of a default routing table that's Internet accessible.
and the Vrf. Um.
On that MPLS network, the uh.
Has um.
Sick, you know, private routing paths through with no Internet connection. So not every service needs a firewall inspection.
For example, the SPIP services. Um
They've actually removed the firewall inspection piece from the SRX directly to the MX960 and created a state, a stateless.
Uh, filter list.

<!-- image -->

**Don Nguyen** 30:57
Um, firewall ACLI mean on the MX, right? Uh, yeah, file. Uh file. Yeah, what you call it. Yeah. Router ACL. Yeah, yeah, take place.

<!-- image -->

**Erickson, James** 30:59
Yeah.
On the MX on the.
Yeah, yeah, exactly. And so.
Um, the only I think.
You'll have to verify it with the with the correct LLD though, right? That's one of the reason these LLDs exist, because it'll tell you, for example, that you know Broadsoft or SPIP.
And.
Um, do not go through a firewall.
Or in what certain instances that they might be? Um.
Gosh, these things are.
Um.
Trucking this CSPC Broadsoft AS cluster, the Ms. pool, the NS pool, the um
The PSTN gateways.
Let's see.
And they've removed stuff out here that.
Are years old. These have probably been axed out.
4.

<!-- image -->

**Don Nguyen** 32:46
Is mainly one of ours or is is a Verizon resource?

<!-- image -->

**Kanumuru, Mohan** 32:51
Ben Liu is Juniper, Juniper.

<!-- image -->

**Don Nguyen** 32:52
I know we have a.

<!-- image -->

**Czirjak, Gery** 32:54
Ben is the Juniper guy.

<!-- image -->

**Erickson, James** 32:55
Yeah.

<!-- image -->

**Don Nguyen** 32:56
Yeah, I know. I saw him in Lou. I'm not sure he's a Verizon person or a Juniper. I I went to dinner with him my first week at work.

<!-- image -->

**Erickson, James** 32:56
Yeah.
Yeah.

<!-- image -->

**Don Nguyen** 33:07
OK.

<!-- image -->

**Kanumuru, Mohan** 33:09
Is is Ben. You are out of California, right?

<!-- image -->

**Don Nguyen** 33:13
No, there's a Ben Liu guy in Plano here, but I'm not sure if that's the same person or not.

<!-- image -->

**Kanumuru, Mohan** 33:16
No. Oh, he's he's big. Yeah, he's the same person. Oh, he's also implanted.

<!-- image -->

**Czirjak, Gery** 33:21
I don't think Ben is in Plano. He's in the East Coast somewhere, if I remember really this Ben.

<!-- image -->

**Don Nguyen** 33:26
I think that's a different question, yeah.

<!-- image -->

**Czirjak, Gery** 33:29
This Bin Liu, Doctor Bin Liu is is a Juniper guy and I'm pretty sure he's on. I think he's in New Jersey or something. I can't remember exactly where he's in the data center.

<!-- image -->

**Kanumuru, Mohan** 33:38
Is new.

<!-- image -->

**Don Nguyen** 33:42
Yeah, I think that's a different person, yeah.

<!-- image -->

**Erickson, James** 33:45
See, here's another thing.

<!-- image -->

**Don Nguyen** 33:45
Not the building in China.

<!-- image -->

**Erickson, James** 33:48
Here's another thing is, you know.
These things that have already been mangled, you might not be able to.
See what this actually.
should look like. Let's see if this opens up in paint.

<!-- image -->

**Kanumuru, Mohan** 34:11
Oh, I think it looks like we have to read the LLD first to to really even have a.
Appreciation of different terminology and what you're talking about.

<!-- image -->

**Erickson, James** 34:25
Yeah, well, you know.
Part of the issue is they they do maintain historical information here. The first generation Broadsoft design. This is not the current design here. Here we go.
Um.
If we zoom in here.
Um.
2123 Yeah, this is a Gen. 1 router that has.
This is 678, yeah, 8-9 and 10.
I believe those are.
789.
Yeah, 67891011 Yeah, so these are.
Old design documents that.
Do they have firewall represented? Um.
I don't see that, yeah.
Um.
So find trying to find things you know to answer topology questions. This is the ideal place to answer those or going through the recordings, but you also run into the issue of.
Oh wait, but which is the section that I'm reading that describes the VLAN IDs or this? Is this part of a legacy design like this first Gen.
And why does it say skip here when this is the broad soft?
Uh design, you know. So these can be really, really challenging to read and work with. Um.
You do. You will spend a lot of time, um, looking through these I.
Um.

<!-- image -->

**Don Nguyen** 37:13
Yeah, I did. I did go to some of these already, but I thought you guys noticed the back of your hand. So I don't know. For me, it's kind of quirky stuff to go to all these things and understanding the the relationship, what they call and what is in a network point of view. Yeah.

<!-- image -->

**Erickson, James** 37:17
Mhm.
Mhm.
Um.
Cause see this is still.
Not the ideal design either, right? This is still not because Broadsoft still.
Um, this is represents the
MX960 in this container here, but um as a routing to well, not a router, a virtual router. So it's a uh AVR.

<!-- image -->

**Don Nguyen** 38:11
Logical system.

<!-- image -->

**Erickson, James** 38:18
But and you'll see that the broad the application server is directly connected to it.
Um.
But you'll see that it's got VLAN uplinks to this XL router that don't exist in the 2.5 Gen.
Um.
So they don't reference here anywhere that says this is still um.
A legacy design. So you you kinda.
You're gonna have to ask until you get a feel for it. Um.
The uh.
Yeah, um.
And see, it's always still just showing this.
VLAN 621620 going to the XL router and not going through the.
Common resources LS. Um.

<!-- image -->

**Czirjak, Gery** 39:55
I think the 6.1 LLD is a little newer than this one James.

<!-- image -->

**Don Nguyen** 40:13
61 is the latest 60 is oh I think.

<!-- image -->

**Erickson, James** 40:17
Where is this but 61 is for broad soft.

<!-- image -->

**Don Nguyen** 40:20
I think it's in a 27.
Uh.
Yeah, the last time I reviewed with the Scott Hiller in the Yeah.

<!-- image -->

**Erickson, James** 40:27
Why?

<!-- image -->

**Czirjak, Gery** 40:28
There's a 61 broadsoft, yeah.

<!-- image -->

**Don Nguyen** 40:31
OK.

<!-- image -->

**Erickson, James** 40:32
Well, I'm not seeing it in this folder, so let's go back to our first question. Where is the thing?

<!-- image -->

**Czirjak, Gery** 40:40
It's uh.
In that folder.
This is buried. So under design docs, under Gen. 27 DPC uplift, under Broadsoft Gen. 27. This is part of it. We have 10,000 documents somewhere.

<!-- image -->

**Don Nguyen** 41:01
Yeah, 61, yeah, yeah, I remember 61 is the current 160. I don't know.

<!-- image -->

**Czirjak, Gery** 41:06
Yeah, if you look under the Gen 2.7 DPC uplift, James, you'll find it buried in there.

<!-- image -->

**Erickson, James** 41:07
So.
Oh, I got it. This is the one.
This is.

<!-- image -->

**Don Nguyen** 41:18
Hopefully it's anatomically correct. Yep.

<!-- image -->

**Erickson, James** 41:19
So is this the same doc just as updated October 3rd?

<!-- image -->

**Czirjak, Gery** 41:22
There's a little there.

<!-- image -->

**Erickson, James** 41:27
For 6.1.
And this one.

<!-- image -->

**Don Nguyen** 41:39
Who who?

<!-- image -->

**Erickson, James** 41:39
OK, when do you want to be able to read what date was there? 2023, June 29th, 2023.

<!-- image -->

**Czirjak, Gery** 41:40
What a piece of crap.
So just so you guys know, this is hopefully gonna go away, right? This came. This is a Sallyism, right?
Um.

<!-- image -->

**Erickson, James** 41:57
Yeah.

<!-- image -->

**Czirjak, Gery** 41:58
Venuto doesn't like this either. So I think going forward you're going to start seeing these things be a bit more standalone than not so 1000 year old.

<!-- image -->

**Erickson, James** 42:09
Yeah, yeah, exactly. So.
So not only back to that first question, where is it? But then we also have to add on the question, is this the latest version?
Here we can.

<!-- image -->

**Czirjak, Gery** 42:31
That looks a bit more current, doesn't it?

<!-- image -->

**Erickson, James** 42:34
Yes it does.
Um.
With now instead of having our 6/21 and 6:22.

<!-- image -->

**Don Nguyen** 42:48
It's a it's a router, yeah.

<!-- image -->

**Erickson, James** 42:48
Um VLANs. We only we have just the 20/21 going up to your VAs. Um.
OK, yeah, this is looking better. This one went through a lot of updating, so they do try to go through the traffic flows like for Broadsoft SIP traffic.
Um.
The Broadsoft BSNS device and the BSAS device are here right?
We have.
Uh, an ACL style firewall on the MX960 on the Uh.
Um.
VLAN IRB 622.
Um.
And.
A. It says default switch. It's gonna be. It is the default switch rather than being a um.
A virtual switch like a virtual um.

<!-- image -->

**Don Nguyen** 44:15
You mean the global? Uh, global.

<!-- image -->

**Erickson, James** 44:16
A routing a routing instance type virtual switch. You know that configuration statement in.
in Junos, right? If you're not using a routing instance type virtual switch, then any bridge domain you create will be in the default switch.

<!-- image -->

**Don Nguyen** 44:39
Right.

<!-- image -->

**Erickson, James** 44:39
Even if it's in a, even if it's in the logical system.
Um.
So they have all of these moved out to from.
Virtual switch configurations um to default switch, and just so it's just a set bridge domain, bridge domain.
Um.
name VLAN ID.
Type bridge.
Um, that kind of thing.
So.
All site traffic between a pair of AS is hosted between 2 geographically diverse Supernodes route over the public IP VPN VIV so.
Public IP VPN. Does that mean through?
Um.
To the public IP router Viv, yeah.
This is OK. OK. They're saying public IP, right? Here's where the vernacular we use, you know, matters a great deal because we talk about.
A S701 that MPLS network. It has a default routing table and a a VPN routing table. The VPN routing table you know being just for VoIP infrastructure VPN. Right, that's what VIV means, but a lot of times that default routing table is referred to as the public IP. The difference, the only discriminating factor to tell which is which.
Is which VLAN it uses. 20 is the default routing table on the that has the access to the Internet and 21 goes through the private VPN or the VIV.
Right.
So.
Um.

<!-- image -->

**Don Nguyen** 47:26
22 go 622 go to the CAVA router, 21 going to the IDN router, the L2 circuit.

<!-- image -->

**Erickson, James** 47:26
That's.
No, 622 state doesn't even leave the MX 960.
2120 and 21 are the ones that leave the MX960.

<!-- image -->

**Don Nguyen** 47:41
Oh.

<!-- image -->

**Erickson, James** 47:47
Um.
20 is the one that has access to the Internet. 21 is the one that has is referred to as the VIV, VoIP infrastructure VPN.
And you, you, you do kind of have to drill that into your heads, you know?

<!-- image -->

**Don Nguyen** 48:07
OK. OK. Voice. OK. Voice ID and we avoid infrastructure IDN, yeah.
IDA, ID and web ID.

<!-- image -->

**Czirjak, Gery** 48:15
Don't say IDN. Don't say IDN. That's something else.

<!-- image -->

**Don Nguyen** 48:19
Oh, sorry.

<!-- image -->

**Erickson, James** 48:20
Yeah.

<!-- image -->

**Don Nguyen** 48:20
Is that the link connect to the the the the the layer two private circuit right?
You ever you ever to join in France?

<!-- image -->

**Erickson, James** 48:34
Where? What are you talking about? This one?

<!-- image -->

**Don Nguyen** 48:37
Yeah, the one connect to the 701, the other one connect to the private Verizon voice infrastructure.

<!-- image -->

**Erickson, James** 48:46
Yeah, yeah, exactly. You can see how these are.
These arrows don't really expect to show up very well, but.
Um.
What they're trying to say here is that um, there is a traffic flow in the black arrows here. Um, that goes from the MX 960.
And it I guess it's pointing to the.
that, or the Vlan twenty point to point interface sub interface, meaning it should be going through the public IP.

<!-- image -->

**Don Nguyen** 49:35
Is is the XL router in this one the VA router?

<!-- image -->

**Erickson, James** 49:39
Yeah, and that's.

<!-- image -->

**Don Nguyen** 49:40
XL. Is that the same notation of VA?

<!-- image -->

**Erickson, James** 49:43
Yeah, because XLs were the a previous generation of um the Vas.

<!-- image -->

**Don Nguyen** 49:51
Oh, OK, OK, let's.

<!-- image -->

**Erickson, James** 49:52
They they say they they say they serve the same role and it's just the capacity difference, the hardware difference.

<!-- image -->

**Don Nguyen** 50:00
Got you.

<!-- image -->

**Erickson, James** 50:01
Um.
So.
Um.
I think the reason they um.
Normally, we don't carry sip over the public IP, but um.
With it firewalled like this, that's that's what we're protecting to. Yeah, well, it's.

<!-- image -->

**Don Nguyen** 50:27
The the five one doesn't end.

<!-- image -->

**Erickson, James** 50:32
Well, it's.

<!-- image -->

**Don Nguyen** 50:32
This this version but the the firewall in the in the other design did the the firewall does the the NAT proxy the the the SIP doesn't talk to the directly you go into a a NAT translation it at the SOX.
But this one they do use the the built in stateless deal here.

<!-- image -->

**Erickson, James** 50:56
Well, although you have to.
Only certain VSNs might use that NAT or I'm sorry VSNS. This is specifically Broadsoft. Broadsoft might use IP addresses that are public IP.

<!-- image -->

**Don Nguyen** 51:06
Right.
Oh, OK. OK.

<!-- image -->

**Erickson, James** 51:16
Addressing on their actual devices here. Um.
So.
Um.
Let's see. Um.

<!-- image -->

**Don Nguyen** 51:41
We should have this review earlier when I just got here.
Can we scale about the time? I'm just kidding. Yeah, it's it's like peeling a damn onion, like in the Shrek movie, man.

<!-- image -->

**Erickson, James** 51:49
Yeah.
Yeah, right.
So.
Again, you know they're showing the topologies and flow by flow like this one is specifically the SIP flow or the IDNKR flow.
Um.
IDNKR is kind of a.
Um.
It's an older style.
Access to the IDN network. The IDN network is like their corporate um WAN stuff, right? Their corporate in intranet.

<!-- image -->

**Don Nguyen** 52:52
Right, right. The private, yeah.
Internet, yeah.

<!-- image -->

**Erickson, James** 52:57
Um, and they have uh.
Servers and tools for management on this in data centers that need access to a million other sites.
Um. And where before the IDN was its own network, it was, you know, built out.
Like.

<!-- image -->

**Don Nguyen** 53:29
That's a legacy MCI, right?
Legacy MCI. The legacy private stuff they maintain, yeah.

<!-- image -->

**Erickson, James** 53:35
I it might.
I'm not sure with the IDN specifically, but to a certain point the IDN was just a standalone network of devices and data centers that.
You know, anytime you wanted to add to it, you had your own.
You had to add um Wan and extend your network the network to.
Uh, each individual site, but you know every brick and mortar store for Verizon is also gonna have need access to the IDN network too, so they couldn't expand.
The physical network as quickly as they could and provide points of presence to each physical location fast enough.
So they started adding in these IDNKR routers. Um.
These are just gateway routers.
Um. In fact, that's what the GR means. Gateway router KR is, I think, the preferred um.
Designation name naming convention for this role of router, but its entire purpose is to backhaul things privately from.

<!-- image -->

**Don Nguyen** 55:12
So the the MX the CR router had a a a dedicate layer one layer one socket to those IDN router, right?

<!-- image -->

**Erickson, James** 55:26
Yeah, so in this container here, this is all still the same MX 960.

<!-- image -->

**Don Nguyen** 55:30
Yeah.

<!-- image -->

**Erickson, James** 55:34
And then and this ref this.
Router icon represents a virtual router, so this this is a virtual routing table and then we have VLAN 150.

<!-- image -->

**Don Nguyen** 55:40
Oh, is a is a virtual router OK?

<!-- image -->

**Erickson, James** 55:50
Reserved, or sometimes it actually uses no VLAN at all. You'll see that occasionally too.

<!-- image -->

**Don Nguyen** 55:57
Is it straight layer 3 IP address?

<!-- image -->

**Erickson, James** 56:00
Yeah, um.
Where and but you'll your I spec should reflect that there is a physical connection between the MX960 to an IDNKR router.

<!-- image -->

**Don Nguyen** 56:18
So in the network to the drawing point of view, this is that correct?
They cannot have a a VRACRVR and and the same container with the ID and that's not correct. Drawing is anatomically incorrect.

<!-- image -->

**Erickson, James** 56:34
Well, yeah.

<!-- image -->

**Don Nguyen** 56:34
We can you explained it, I understand it, but that's not a correct that we're going.

<!-- image -->

**Erickson, James** 56:40
No, you're right. I think there's um.

<!-- image -->

**Don Nguyen** 56:45
This would be two container, yeah.

<!-- image -->

**Erickson, James** 56:45
You know what they have done in the past is is the container for each routing table.
Um, but there is a relationship between the CR1 VR and the IDNGRVR.

<!-- image -->

**Don Nguyen** 56:53
Yeah.
They may have the RIP group, export, import, crazy stuff, but that's two still two different CRI mean logical, whatever you call it, yeah.

<!-- image -->

**Erickson, James** 57:06
Yeah.
Yeah.

<!-- image -->

**Don Nguyen** 57:11
It's OK, I understood it now, but the farmer network going, there's a some needs to be, yeah, OK.

<!-- image -->

**Erickson, James** 57:18
Yeah, and what they're not showing here, I think they just kind of tried to phase fade it out since it's not not in the focus of this traffic flow explicitly this.

<!-- image -->

**Don Nguyen** 57:32
Yeah.

<!-- image -->

**Erickson, James** 57:34
faded out pieces, yet another routing table that's related to IDN that goes directly to the um

<!-- image -->

**Don Nguyen** 57:44
I got you. So let me ask you a stupid question. I I kind of in sorry to interrupt you from a Verizon point of view. Only Scott Hiller work on this right and John Sullivan.
From a Verizon, the and Chao Ram or those guy or only Scott Hiller?

<!-- image -->

**Erickson, James** 57:56
Yeah.
No, they should all be putting in their their two cents, their input, and you tasked depending on which type of services it provides or.

<!-- image -->

**Don Nguyen** 58:06
OK.

<!-- image -->

**Erickson, James** 58:21
Um.
Yeah, this this describes the.

<!-- image -->

**Don Nguyen** 58:26
The RIB group export import, yeah.

<!-- image -->

**Erickson, James** 58:27
The RIB groups, yeah, they're specific to the Broadsoft.
Um, you won't see the RIB groups with anything but the broad soft. Um.
But you do have some.
Uh, configuration here.
Um.
So what you're doing here is your interface routes. Um.
Do they? Oh, do they? I'm looking for the.

<!-- image -->

**Don Nguyen** 59:07
2021 6/20.

<!-- image -->

**Erickson, James** 59:13
Actual policies. They don't write out the policy.
Because they you know they're they're clear. This is the rib group name Lau Broadsoft to IDN. You you import it from CRVR where the that Vlan resides that Vlan and IRB.

<!-- image -->

**Don Nguyen** 59:41
Yeah.

<!-- image -->

**Erickson, James** 59:42
resides there. You want to import it into the IDNGR table, but you do it
You restrict it by only certain broad soft routes are allowed to do that. Um.
Oh, so they have the policy statement. It was the prefix list I was looking for allow only, but they don't have that allow only broadsoft.

<!-- image -->

**Don Nguyen** 1:00:07
Right there, yeah.

<!-- image -->

**Erickson, James** 1:00:15
Um.
Uh, prefix list.
Exemplified here in this.
LLD.
And normally I'll just see the lab version of, you know.
No.
This prefix list since the prefix list is gonna have IP addresses.
In it that are specific to Broadsoft, you'll get an example. Um.
That has. I guess it's either abstracted or has lab IPs in it.

<!-- image -->

**Don Nguyen** 1:01:01
Got it.

<!-- image -->

**Erickson, James** 1:01:01
Um.
So here we're allowing the opposite way you're taking anything.
Um, I don't know that this export rib actually does anything.
Um.
From the point of from the perspective of this.
Yeah, at any rate, um.
It's in the LLD, so you'll add it. Um.
The again this is added. Well this one was added to our interface routes because the IRB that exists in CR1 VR is IRB 622.

<!-- image -->

**Don Nguyen** 1:01:59
Yeah.

<!-- image -->

**Erickson, James** 1:01:59
Is that interface route that we're looking for, right? Whereas the IDNGR, we don't just need the interface route, we need all of the BGP routes.

<!-- image -->

**Don Nguyen** 1:02:04
Yep.

<!-- image -->

**Erickson, James** 1:02:15
That are coming in from your GR router and those are the ones we are allowing.

<!-- image -->

**Don Nguyen** 1:02:23
From the ID inside, right?

<!-- image -->

**Erickson, James** 1:02:26
Yeah.

<!-- image -->

**Don Nguyen** 1:02:28
Because from the from the public you only need to 622 specific only.

<!-- image -->

**Erickson, James** 1:02:37
Yeah, but for yeah, when it comes down to purposes for purposes of like a config conversion, this is already all be built out. You'll probably already see this.

<!-- image -->

**Don Nguyen** 1:02:38
From the other side, you wonder, yeah.
OK, OK.

<!-- image -->

**Erickson, James** 1:02:53
This specific prefix list already exists in previous Gen. hardware, yeah.

<!-- image -->

**Don Nguyen** 1:03:00
Because they don't change, right? Those are static, right? So it's a just a conceptual of how things should be, but it's already in the existing stuff. From a configuration standpoint, we we already have it in these current config, right?

<!-- image -->

**Erickson, James** 1:03:11
Yeah.
Yeah.

<!-- image -->

**Don Nguyen** 1:03:16
That's good.

<!-- image -->

**Erickson, James** 1:03:19
And just validate. Um.
It's percurrent VoIP design is 161 once.

<!-- image -->

**Don Nguyen** 1:03:29
It is a way you can quiz me like next week or something. I I I I noticed, but the next week I don't remember. I need somebody to quiz me or give me a test, man. I'm serious. Oh Nick, I'll maybe go with Nick and Nick asked me some random. Make sure I remember.
Hassan, are you on the same page?

<!-- image -->

**Erickson, James** 1:03:45
That's an.

<!-- image -->

**Kanumuru, Mohan** 1:03:48
close to you I oh.

<!-- image -->

**Don Nguyen** 1:03:49
Yeah, yeah. When you understand the logic stuff, it's it's it's helps solve all the Riddle in my head, yeah.

<!-- image -->

**Kanumuru, Mohan** 1:03:53
Yeah, I'm I'm glad that you you were actually connecting the dots here. I have no clue what's happening when all this James is explaining.

<!-- image -->

**Don Nguyen** 1:04:05
Then I I I will quiz you then Mohan. I we we need to do that among us. I'm James too easy for him. He's to the back of his hand but I need to understand. I understand the logic but some of the stuff I wasn't quite sure because on the SRX there's also them rip group and export import and and also a firewall policy too.
So they need to all match end to end.

<!-- image -->

**Erickson, James** 1:04:31
Yeah.

<!-- image -->

**Kanumuru, Mohan** 1:04:36
OK, I won't. I don't want to digress this.

<!-- image -->

**Don Nguyen** 1:04:39
That was the the society. OK, yeah.

<!-- image -->

**Erickson, James** 1:04:43
So um.
This is also calling out that um.
We have.
This is a well known policy name for our BGP set that's applied to our BGP session BGP sessions with the VA routers.

<!-- image -->

**Don Nguyen** 1:05:12
Mhm.

<!-- image -->

**Erickson, James** 1:05:14
Um, so.
Um.
Any EBGP, although they're.
These are just showing specific terms that are related for the reference Broadsoft. I'm sorry, Broadsoft IDN routes.
That are required for IDNGR to access the the Broadsoft devices, but we reject them from being sent to.
Um to the.
AS 701.

<!-- image -->

**Don Nguyen** 1:06:05
So we don't want the process to be available on 701 public at all, right?

<!-- image -->

**Erickson, James** 1:06:06
Uh.
Well, just the IDNGR routes, the ones that we we've we've received from the BGP, the BGP session.

<!-- image -->

**Don Nguyen** 1:06:18
IDN.

<!-- image -->

**Erickson, James** 1:06:22
Restrict ID and routes. These are the Uh the ones we get from our Uh BGP session with.

<!-- image -->

**Don Nguyen** 1:06:27
OK, let me sorry, sorry, let me ask you this. So we have prostop within the location direct attached to the MX, right? And also prostop from at the IDN location too, right? They're two different location, right?
At IDN location and add the direct attached to the MX right? So the the public they can they can get to the the one connect to the MX directly but not to the one in IDN right?

<!-- image -->

**Erickson, James** 1:06:49
Uh.
Well, there's there's nothing broad soft in IDN specifically, there's just the the tools like the OSS, BSS, BGP, right routes, right?

<!-- image -->

**Don Nguyen** 1:07:03
Oh, OK. OK.
Yeah, the two tag would come in the string. We done with it, but I prefix a little bit harder.

<!-- image -->

**Kanumuru, Mohan** 1:07:14
But but all but all this seems to be at certain points, at certain places, at certain nodes, this idea is going to connect to the.

<!-- image -->

**Erickson, James** 1:07:15
Yeah, I I'm.

<!-- image -->

**Kanumuru, Mohan** 1:07:29
The PIP network, I mean not PIP, SPIP or whatever you call it, the work, the MX is that we are working on, but it's not everywhere. It looks like for example, I just looked at the HSJBR. There is no such thing here.

<!-- image -->

**Erickson, James** 1:07:40
Yeah, yeah.
Yeah, exactly. So that's the difference between the IDNGR and the IDN.
just the regular IDN telemetry like the the GR router is set up to send BGP prefixes umm for these specific devices and and other
Tools that exist on IDN. Um.
For for Broadsoft, but Broadsoft doesn't have another interface that it can use for telemetry, so it has to accept, so it has to use it's the same interfaces that passes production traffic through.
For, you know, the SIP calls and all of that has to be available and accessible to these IDN.
Uh, resources.

<!-- image -->

**Kanumuru, Mohan** 1:08:52
So, so you're saying that basically where? So whenever there is a broad soft device, then we will end up having these policies in this BGP session.

<!-- image -->

**Erickson, James** 1:09:01
Well, the yeah, well, well, more specifically, it's where we have the RIB groups. Why we have the RIB groups is because this Broadsoft server doesn't have a second link to use up to this IDNGR.

<!-- image -->

**Kanumuru, Mohan** 1:09:04
1.

<!-- image -->

**Don Nguyen** 1:09:16
He doesn't have a dedicated link. He had to uh uh share and that only with the split hair using rip group, right? Split hair.

<!-- image -->

**Erickson, James** 1:09:18
Yeah.
Yeah, other other devices will have a different interface here.
Um and.
But then you have to go to that services LD to find that out, you know.

<!-- image -->

**Kanumuru, Mohan** 1:09:41
Yep. So there is a separate VLAN. Yeah, there. Yep.

<!-- image -->

**Don Nguyen** 1:09:42
Got it. Got it. Got it. No, this is a this is a big, big deal, man. Thank you for making it clear. It's easy to understand the why. Yeah.

<!-- image -->

**Kanumuru, Mohan** 1:09:50
So that VLAN 622 is basically meant for this ID and equivalent.

<!-- image -->

**Erickson, James** 1:09:57
Six no 6/22 it's it's 150 that represents this BGP session.

<!-- image -->

**Kanumuru, Mohan** 1:09:57
On the.

<!-- image -->

**Don Nguyen** 1:10:07
Yeah, that's right, 150, yeah.

<!-- image -->

**Erickson, James** 1:10:08
All right.
150 and 622 is the public IP VLAN subnet that represents down here.
And that is like I said that is publicly addressed the same SIP traffic and you know call traffic that that goes through here out to the Internet or out to.
To the AS 701 Um.
Has to be shared with these routes that are coming in through here an replicated into this routing table without sharing these.
Um prefixes out to the AS7 on one.
So we we leak, you know, so that both sides not have.
Uh, this.
You know.
Your your egress points.
And then?
Restrict your BGP advertisements out to your VA router, so not so it restricts the VLAN 622, but so it restricts anything you learn over the IDNGR.
Wan BGP session. So that's what we were looking at down here. That's what this does is it takes the same ID and GR route prefixes that we learned over BGP.
Um.
and rejects them from being sent over the EBGP to the umm to the V8 router.
NAS 701. The AS number for IDN by the way is what, 65,000 something like that?
Um.
Does it say here specifically?
622.
64549.

<!-- image -->

**Don Nguyen** 1:12:41
That's private AS number, yeah.

<!-- image -->

**Erickson, James** 1:12:44
Yeah, so that AS number.
Um.
Is what that?

<!-- image -->

**Don Nguyen** 1:12:52
Yes, something in the phase 150 BN 150. Yep, right there.

<!-- image -->

**Erickson, James** 1:12:56
Yeah.
Um.
And of course, you know 2 lines to describe the the utility server. Honestly, come on, do you think that's enough to?
You know, information. Maybe it describes it more in depth down lower somewhere, but there's a lot more to that utility server than.
Um.

<!-- image -->

**Don Nguyen** 1:13:28
Is that a stupid something? The sniffer that mad cop used to troubleshoot the voice failing?

<!-- image -->

**Erickson, James** 1:13:28
And justice the two lines.
Uh, when?

<!-- image -->

**Don Nguyen** 1:13:42
When we had the Houston issue, remember.
Like it look like a snippet trace the the voice troubleshooting tool.

<!-- image -->

**Erickson, James** 1:13:49
Oh.
No, that wasn't so much the utility server as it was the Geo probe the the local.
Port mirroring uh.

<!-- image -->

**Don Nguyen** 1:14:05
OK.

<!-- image -->

**Erickson, James** 1:14:08
Because the Houston issue was all the.
The port mirroring off the EX is went directly to, you know, um a Geo probe, and he could use his iris view tool to to see what was.

<!-- image -->

**Don Nguyen** 1:14:26
I still, yes, yeah, yeah.

<!-- image -->

**Erickson, James** 1:14:31
To connect to that Geo probe and.
Monitor frames coming in and out.
Um, here's some details on what these.
Um.
A specific SDC for Rotsoft I package for the in network connection.
So when they're talking about these elements, you know, the broad, soft, um.
Elements. Here's one of them. So the DL 36 three 60s. Um.
You know, net zero or net, you know, to whatever, right? Um, I don't know.
And this is this they say here this is um.
The actual layout suite part of the site specific. Um.
So there might be a difference in the layouts depending on the site.
Um.
But it does give.
Um.
subnet information like for this one specifically.

<!-- image -->

**Don Nguyen** 1:16:00
The formula how they they cut out the IP address.

<!-- image -->

**Erickson, James** 1:16:06
Yeah, yeah, exactly. So for VLAN 622, your your IRB is going to have um.
An IP address on it.
Um.
Utility server.
Although I don't remember that they didn't use.
I'm not sure why they're not using here why they have +5 or +6 here instead of +2 and three.
Um.
Yeah, so they've got a whole /25 set aside for the 622 VLAN.
And everybody just.
gets a piece of that subnet. 629 is going to be more um.
Management driven like actually as being able to SSH and access it like lights out management for the broadsoft equipment will be in 629.
And so you get a slash 26. Um.
Historical references again back with the old style historical stuff. Um.
And trying to decide where that historical stuff.
Starts and ends.
Section 5. Maybe just skip all of Section 5 and hope there's nothing.
Relevant that you're missing by skipping all of Section 5, right?

<!-- image -->

**Don Nguyen** 1:18:29
No, it's really good. I I I think I understand the why so and it understands some of the differentiation between type so.

<!-- image -->

**Erickson, James** 1:18:40
Yeah, well, and.
I I.
I think um.
Nitra 40s, 4270s.
Is using. Again, this is. It's still Section 5, so it's still Section 5, which is noted as.

<!-- image -->

**Don Nguyen** 1:19:05
That's sun, right?

<!-- image -->

**Erickson, James** 1:19:14
Legacy Gen. 1 historical information. So hopefully you don't need anything any of that information. I guess it's it's Section 5 is the last section, so you know.
That's part of the.
The challenge that I was talking about is is distinguishing whether something's historical Gen.
Early generation.
Topologies and and design.
Um, and what isn't?
Cause that's part of what makes these so so difficult to to read and and understand and the they don't put a specific configuration.
for the whole shebang um into the LLD, and that's OK. I mean, there's also.
should be a uh another document alongside of the Ld. Um called the a build out doc.

<!-- image -->

**Don Nguyen** 1:20:35
Yeah, yeah, that's that's a different doc. Yeah, you can only, yeah, you can't have. So all the config in LOD. LOD just, yeah, network drawing.
Point.

<!-- image -->

**Erickson, James** 1:20:46
Yeah.
So build mops were a specific task on Atif before he left.
Um.
and other people in in
Not exactly sure where.
The latest build mop is um.
Let's build Mop review. Build Mop review.

<!-- image -->

**Don Nguyen** 1:21:31
When was it? What day was it 22?

<!-- image -->

**Erickson, James** 1:21:36
I don't know when he created these build maps. Um.

<!-- image -->

**Don Nguyen** 1:21:58
So I'm curious who, James, you and Nick, who trained you guys? You too.

<!-- image -->

**Erickson, James** 1:22:03
Um, Atif was always a great resource. He kind of knew everything about.
Everything because he went through and did one of the first steps in this entire project when we first kicked off, you know?
Work with Verizon on this on some of these. Yeah, from day one stuff. Um, the first step was with the firewalls and moving the net screens off the network. Um.

<!-- image -->

**Don Nguyen** 1:22:30
Oh, from the day one stuff, yeah.

<!-- image -->

**Erickson, James** 1:22:48
And replacing them with with SRXS. So he kind of had all that experience and that was a much easier task than the routers because you know these are just firewalls on a stick. You can it's the conversion from net screen to SRX might have been the.

<!-- image -->

**Don Nguyen** 1:22:51
Yeah.

<!-- image -->

**Erickson, James** 1:23:07
The biggest pain, but you know.

<!-- image -->

**Don Nguyen** 1:23:09
Yeah, it's it's condensed. Yeah, it's, it's, yeah, yeah.

<!-- image -->

**Erickson, James** 1:23:10
You don't have multiple. Yeah, you don't have multiple devices connecting to it and multiple, you know.
Um.
Routing paths. It's all in the same.

<!-- image -->

**Don Nguyen** 1:23:24
Yeah, yeah, yeah, yeah. It's a it's a it's a simple policy, but there are a lot of repetition of the VPN. So you get one, you get all of them.

<!-- image -->

**Erickson, James** 1:23:26
Uh.
Yeah.
Um, I'm not seeing it.
Where do you find these build mops?
Um, Gary?

<!-- image -->

**Don Nguyen** 1:23:49
Yeah, drop off. Just me, you and Hassan and Mohan.

<!-- image -->

**Erickson, James** 1:23:55
Oh.

<!-- image -->

**Kanumuru, Mohan** 1:23:55
There is a MOP folder, isn't it? Within this in the drive there is a MOP specific folder, isn't it?

<!-- image -->

**Erickson, James** 1:24:03
Well, they're they're not actually mops. They're.
Um.

<!-- image -->

**Kanumuru, Mohan** 1:24:10
What? What is a building up then? What is a?

<!-- image -->

**Erickson, James** 1:24:11
A build mop. It might be in design documents here. Maybe there is a.

<!-- image -->

**Don Nguyen** 1:24:11
Like configuration template, yeah.

<!-- image -->

**Erickson, James** 1:24:19
Um.

<!-- image -->

**Don Nguyen** 1:24:32
So how do you guys interact with Matt Tiggy?

<!-- image -->

**Erickson, James** 1:24:37
How do we end up with him? What do you mean?

<!-- image -->

**Don Nguyen** 1:24:39
No, no, no. How do you guys interact with Matt Tiggy? Any conversation at all with him at all? I'm just curious. Yeah, I don't know because I we met him at the the first couple week meeting and I never, I never talked to him anymore. So I just wonder how you guys interact with him, so.

<!-- image -->

**Erickson, James** 1:24:45
Occasionally, why?
Oh.
It's rare. He comes in at the very start kind of to vet the um to do sales and and vet the like the.
A project before it gets stamped and and approved by management. He's. I don't know how much sales he actually does. Like if he's setting prices, he's at the very least.
In terms of LOE stuff, determining you know the tech, the technical sales, the doing the.

<!-- image -->

**Don Nguyen** 1:25:28
I got you.

<!-- image -->

**Erickson, James** 1:25:37
Um.
You know, trying to decide how much time we're gonna bid and that kind of thing. Um.

<!-- image -->

**Don Nguyen** 1:25:47
So is this our tip work on the MX2 in the early day to set all the router instant and logical router on exporting first up too or you was here or you were here early enough to do that stuff James?

<!-- image -->

**Erickson, James** 1:25:55
No, he was.
Yeah, I was here earlier. Me and Derek were started right after they were finishing up all the SRX migrations. They started with the router migrations and moving M10 eyes to MX10 fours.
And so now we've matured into moving off those M10 eyes to um.
Starting work on these MX960's.
So.
Um.

<!-- image -->

**Don Nguyen** 1:26:33
So how did you get L2 support on M10, the AE equivalent, the AE zero and one? How? How did you do that before the M10? I mean, what was the alternative solution for that?

<!-- image -->

**Erickson, James** 1:26:48
The M10s were never using lag bundles. It it was all yeah, no, we well, I mean the M10s should.

<!-- image -->

**Don Nguyen** 1:26:51
Because I don't. I don't. It doesn't support a start. It's just yeah.
It's kind of, but I think it's supported. I just wonder what was his back then? How did you guys get around that?

<!-- image -->

**Erickson, James** 1:27:07
If the switches did it, the sys goes to the port channel.

<!-- image -->

**Don Nguyen** 1:27:08
Oh, 6500, OK, OK. The the old school way, OK.

<!-- image -->

**Erickson, James** 1:27:13
Yeah, um.

<!-- image -->

**Don Nguyen** 1:27:15
OK, I got the answer, yeah.

<!-- image -->

**Erickson, James** 1:27:17
Yeah.
Um.
No, the the port density on those M10 eyes just couldn't handle anything like that. So Max got, you know, 8 interfaces at most.

<!-- image -->

**Don Nguyen** 1:27:30
Yeah, yeah, a couple of 10 gig. No, you don't have a 10 gig. I don't remember. Maybe. I don't remember tiny stuff. 1 gig.

<!-- image -->

**Erickson, James** 1:27:36
No, at most you got, yeah.
Um, I'm not seeing.
Build mops. Um.
Huh. I'm seeing a lot of reviews for the big build mops. Um.
Buildmop review.
At any rate, uh, I think I have some of those available to view.
Maybe on the next call we'll we'll cover what these build mops look like because they do kind of take the.

<!-- image -->

**Don Nguyen** 1:28:24
Yeah, I am very happy with this right now, man. Yeah, the bill mop would be a bonus for me, but I have to be honest with you. I'm really happy right now to and this confirms some of my reading and stuff. But I wish you had a training class like this early, like when I just got here.

<!-- image -->

**Erickson, James** 1:28:39
Yeah.

<!-- image -->

**Don Nguyen** 1:28:44
A couple weeks and when I started to be a lot more helpful, but you were busy, so everybody busy and the large run around. Nobody had time to stop and wait, you know, racing.

<!-- image -->

**Erickson, James** 1:28:45
Yeah.
Yeah, that was.
Yeah, yeah, yeah.
So the the goal at that point was just to let you guys observe the process, get what you could get. Let's take a look at one other different.
Um LLD. Um.

<!-- image -->

**Don Nguyen** 1:29:20
Uh a non prostop type with the so the only prostop had the the uh the rip or input actual right? So what what else was other scenario packet?

<!-- image -->

**Erickson, James** 1:29:23
Yeah, let's do S pip.
As soon as the.
Base node. That's the broad soft. That's the other broad soft.
E.
This guy is what I'm looking at.
Um.
So this is SPIP 7 and eight.
Um.

<!-- image -->

**Don Nguyen** 1:30:28
Oh, this is the one we intend to review today. OK, doesn't matter. I got what I got.

<!-- image -->

**Erickson, James** 1:30:33
Yeah.

<!-- image -->

**Don Nguyen** 1:30:34
Yeah.

<!-- image -->

**Erickson, James** 1:30:35
Well, we did book for this for for two hours, so I'm might as well take next.
Um.
So sample flow call flow for hosted IP centrics with.
Pip D Access.
So.
Um.
Acme SVC Sesson Blower Controller SVC interested so.
We have.
We this is where we are hosting.
Or, you know, the PIP D is something that we come you come across with these SSPIP. Well, no, it means PIP dedicated, private IP dedicated per customer.

<!-- image -->

**Don Nguyen** 1:31:41
Domestic, right?
Oh, OK. OK.

<!-- image -->

**Erickson, James** 1:31:52
Um.
And this is a different AS altogether.
This is the 65,000 AS. Um.
The Uh, so the customer presence, customer um presence equipment, you know all of their VoIP equipment for their enterprise, their office all goes.
To a firewall and then hops on to this L network that's was provisioned just for them.
And then it's back called from from there.

<!-- image -->

**Don Nguyen** 1:32:37
To uh.
To the 701 AS, right?

<!-- image -->

**Erickson, James** 1:32:42
Yeah, to the Well, not quite yet. It goes to the hour 1661 as because um.
These SPCS connect to our routers.
And then it this the signaling then goes to the Broadsoft cluster.
To get there, yes, it does cross a S 701 to get from here.

<!-- image -->

**Don Nguyen** 1:33:19
So on the left, on the left side, there's not even into Verizon network yet, not into our project yet. It's it's somewhere else, right?

<!-- image -->

**Erickson, James** 1:33:25
No, this is it right here. This is because and this is only call processing diagram, right? This isn't actual topology diagram, this is just call processing. So there's still signaling.

<!-- image -->

**Don Nguyen** 1:33:33
Right.
Correct.

<!-- image -->

**Erickson, James** 1:33:42
You know, SIP traffic, but this is these SSPCS are are connected to our MX devices.
And once we take it to the AS 701 back haul it to another site where there happens to be a Broadsoft cluster and so it drops out of AS701 back to AS 1661.
Which is another VoIP node.
And then from there to the Verizon business NSRS cluster. So again, it may need to go back out to AS701 and then back to one of the VoIP nodes.
In AS 1661 to reach the NS and the Rs.
and then from here go. Yeah, Pstn.

<!-- image -->

**Don Nguyen** 1:34:45
SDN wherever that is, right?

<!-- image -->

**Erickson, James** 1:34:51
And.
Um.
And then media, of course, once it gets to the SBC, it it it doesn't. Yeah, it it doesn't.

<!-- image -->

**Don Nguyen** 1:35:02
That's the RTP traffic.
Yeah.

<!-- image -->

**Erickson, James** 1:35:08
Need the prod soft or the NSRS for processing. It just goes straight.

<!-- image -->

**Don Nguyen** 1:35:11
Yeah, it's RDP. I got it. Yeah, yeah, yeah.

<!-- image -->

**Erickson, James** 1:35:16
Um.
Virtual servers are all deprecated.
Um.
Common design components. Um.
A lot of reading here, but it doesn't. No diagrams. Love it.

<!-- image -->

**Don Nguyen** 1:35:39
I will go over this a few more times by myself and go slow with the hot tea and digest it slowly.

<!-- image -->

**Erickson, James** 1:35:42
Yeah.
Well.
The the key thing to remember here is the difference anytime you're talking PIP or SPIP. Um.
We have a large range of Vlans for it that are customer because remember we're we're provisioning per customer and each customer, each customer needs a VLAN.

<!-- image -->

**Don Nguyen** 1:36:11
Uh, OK, OK.

<!-- image -->

**Erickson, James** 1:36:15
Out of this range for SIP and out of that range for RTP.

<!-- image -->

**Don Nguyen** 1:36:19
RTTI know that on prostop the range were one to 199 right? This is 1000 increment I if I'm not mistaken right?

<!-- image -->

**Erickson, James** 1:36:22
Yeah.
Mhm.
Oh, Broadsoft should have just been two different VLANs or some, you know, depending on that that LLD, right? Yeah, this has customer VLANs, yeah, and each one of these VLANs has a subnet, like a slash 25 subnet.

<!-- image -->

**Don Nguyen** 1:36:39
Yeah.
Yeah.

<!-- image -->

**Erickson, James** 1:36:52
So like 2001 and 3001 will have an entire slash 24 of private IP space, you know, for natting.

<!-- image -->

**Don Nguyen** 1:37:02
Yeah.

<!-- image -->

**Erickson, James** 1:37:05
And be paired up for a specific customer, right? Um, these IP's here or these Vlans here, kind of, yeah, they're.

<!-- image -->

**Don Nguyen** 1:37:15
Those are common, right?

<!-- image -->

**Erickson, James** 1:37:20
Common or carrier stuff. You'll you'll you'll still use this 510 for management.

<!-- image -->

**Don Nguyen** 1:37:22
Yeah.

<!-- image -->

**Erickson, James** 1:37:29
Um.
I didn't know they actually went all the way up to.
I'll have to talk to Nick about that, but I guess they do go up to five, sixteen, five, seventeen, five, eighteen, five, nineteen. So the even ones are all media, and then the odd ones are all sip.
Um.
And yeah, they are shared. Um.
And these are unique public IP addresses that are advertised out to a S 701 either in you know the the the media ones are shared out for.
You know in both the Internet default routing table and AS 701.

<!-- image -->

**Don Nguyen** 1:38:28
Yeah, they have to otherwise the the user the client couldn't get to this comment SPC.

<!-- image -->

**Erickson, James** 1:38:28
And the VPN.
Yeah.

<!-- image -->

**Don Nguyen** 1:38:36
Right. We can accessible to other voice customer.

<!-- image -->

**Erickson, James** 1:38:39
Yeah, and the SIP doesn't. It only goes through the private.
Viv routing instance we were talking about. Yeah, Viv.

<!-- image -->

**Don Nguyen** 1:38:50
VIV Yeah, yeah, VIV, yeah.

<!-- image -->

**Erickson, James** 1:38:56
Um.
Utilities are all removed from nodes, except those supporting Bing Bull.

<!-- image -->

**Don Nguyen** 1:39:06
Is it a stupid Ubuntu with smoking?
But something equivalent.

<!-- image -->

**Erickson, James** 1:39:15
With what?

<!-- image -->

**Don Nguyen** 1:39:16
Smoke ping, which is open source smoke ping. They ping all the node that you put in there and tell you the give you the latency list in in a nice way.

<!-- image -->

**Erickson, James** 1:39:18
Oh.
I'm not.
Yeah, I'm not sure what app it uses, but yeah, it's just gonna be able to.
Um.
Here's a here's our first top topology map. I mean what it it.
All the way down to page 15 before you get to your first apology map. Um.
But you should you see the V. The Spcs here. Um.

<!-- image -->

**Don Nguyen** 1:40:05
Mhm.

<!-- image -->

**Erickson, James** 1:40:14
510 The Wan com is a management interface. Um.
You have when uh additional land com between SBC one and two for health check reasons.

<!-- image -->

**Don Nguyen** 1:40:28
Heartbeat, yeah.

<!-- image -->

**Erickson, James** 1:40:30
Yeah, so we're not looking at the carrier side stuff. This is just customer side, right? So this is all PIP AS65000.

<!-- image -->

**Don Nguyen** 1:40:38
Yeah.

<!-- image -->

**Erickson, James** 1:40:45
Um.

<!-- image -->

**Don Nguyen** 1:40:46
Those are VA router, right? PE12 VA router.

<!-- image -->

**Erickson, James** 1:40:47
And.

<!-- image -->

**Don Nguyen** 1:40:57
Yeah.
Yeah.

<!-- image -->

**Erickson, James** 1:40:58
Is uses the VA routers the the AS 65000 PIP my MPLS network. Yeah the dedicated one. So if this is a customer.

<!-- image -->

**Don Nguyen** 1:41:06
So this is a dedicated one, the private one. Yeah, 6500, OK.

<!-- image -->

**Erickson, James** 1:41:15
Premise equipment here their their VoIP gateway here they.

<!-- image -->

**Don Nguyen** 1:41:21
Oh, I got you.

<!-- image -->

**Erickson, James** 1:41:22
Traverse and backhaul all the way through this MPLS cloud to get to the MX960. So this is the NNI interface here. This is the Wan.

<!-- image -->

**Don Nguyen** 1:41:32
I got you. I I I'm sorry I I messed up. I keep confusing between PIP and IDN. They're both private, but this is specifically only for customer side, not the IDN is Verizon OSS. I I I got it now. I I mixed up.

<!-- image -->

**Erickson, James** 1:41:38
Yeah.
Yeah, well and sometimes and some. Sometimes they do use the PIP network to backhaul IDN traffic, but they use a different VRF on on the same devices.

<!-- image -->

**Don Nguyen** 1:41:57
I'll be I have incident, OK.

<!-- image -->

**Erickson, James** 1:42:02
They'll have customer customer built VRFS.

<!-- image -->

**Don Nguyen** 1:42:02
Oh, OK. OK.

<!-- image -->

**Erickson, James** 1:42:08
To to.
Route traffic to between different customers, but they also have a VRF, you know, a private VRF for IDN that goes lands into the IDN network over here on this side, so.
Um.
So this is the NNI interface. These are the.
Those Vlans 2000 to 3000 um range.

<!-- image -->

**Don Nguyen** 1:42:48
Yeah, one.

<!-- image -->

**Erickson, James** 1:42:48
Vlans.
Um, and then?
They you know the SP is connected to the SBC. The SBC has matching VLAN identifiers on its customer side.

<!-- image -->

**Don Nguyen** 1:43:05
They configure so we match, right?

<!-- image -->

**Erickson, James** 1:43:08
Yeah, so we can't deviate in those because it has to match what's on here.

<!-- image -->

**Don Nguyen** 1:43:10
So you you have a cut sheet without a scheme that that somewhere that matches that 100 second guess ourselves, right? Is that is that in a form of the cut sheet I skip whatever you call it, no or something else?

<!-- image -->

**Erickson, James** 1:43:21
No.
No. Um.
What happens is the uh.
Yeah.
The interface is just, you know, a one gig interface to the SPCS that allows multiple V lens. It's just a trunk and.
We don't necessarily have to.
Um, well, yeah, we do.

<!-- image -->

**Don Nguyen** 1:43:53
Yeah, it's all this is signaling, right? Just very a couple 100 KS of a signaling. Are you allowed to make this call number and whatever credit card stuff, right? Signaling, no traffic.

<!-- image -->

**Erickson, James** 1:44:01
Yeah, yeah, yeah, the the SBC.
Matches the customers with their Um.
With their credentials and their correct IP address, yeah, so that we can work that out on, you know the the Broadsoft and NSRS equipment, right?

<!-- image -->

**Don Nguyen** 1:44:18
Credential dead dial plan. Yep.

<!-- image -->

**Erickson, James** 1:44:33
Um. For now, it's just keeping um.

<!-- image -->

**Don Nguyen** 1:44:34
Right.

<!-- image -->

**Erickson, James** 1:44:41
The uh.
The routing table.
For each customer, each customer has their own routing table because each customer has a different VLAN on this NNI this Wan link here. Each customer has its own point to point VLAN slash 30.
Here let's see if it has an example of the routing instance.
And this might help.
O the IE.
VRF and NI. Then you have the signaling.
which would be like the land two thousand two thousand one, two thousand and three. This is three thousand three thousand one, et cetera. Um, and then

<!-- image -->

**Don Nguyen** 1:45:35
Yeah, signaling and RTP. Got it. Yeah.

<!-- image -->

**Erickson, James** 1:45:38
Yeah, and then these.
Um.
Downlink to the SPCS and then the SPC translates these private IPS into public IPS.
More than just a NAP because it doesn't do it based on UDP port or or whatever. It translates based on customer ID.

<!-- image -->

**Don Nguyen** 1:46:09
Yeah, SIP ID, SIP ID.

<!-- image -->

**Erickson, James** 1:46:10
So yeah.
So it it then it provides a a public IP, public IP for further routing out to the infrastructure. Now this shows these are separate, but they're not really they're.
Um.

<!-- image -->

**Don Nguyen** 1:46:30
Well, in a voice end they're separate, but network they don't have to, yeah.

<!-- image -->

**Erickson, James** 1:46:33
Network wise, yeah, one there.
Logical design IPV 6. Um, I'm not sure.

<!-- image -->

**Don Nguyen** 1:46:44
I think those may be in the past wishful thinking, but.

<!-- image -->

**Erickson, James** 1:46:45
Well, I I think they're trying to implement ipv6, but I think that might be either typo or something.

<!-- image -->

**Don Nguyen** 1:46:53
Good luck.
Good luck.

<!-- image -->

**Erickson, James** 1:46:59
Um.

<!-- image -->

**Don Nguyen** 1:47:05
When I work on this stupid **** and back in 2001 and two, it take a lot of people to do this stuff. I don't know how the hell they do this, which is Scott Hiller.

<!-- image -->

**Erickson, James** 1:47:11
Yeah.
Yeah, well.

<!-- image -->

**Don Nguyen** 1:47:17
I work for Level 3 back in 2001 and two, man. We have a lot of people doing this stuff, not I don't know how they get around with just Scott Hiller.

<!-- image -->

**Erickson, James** 1:47:28
Yeah.
So you know, if you read carefully, you're getting a lot of information here. It's just buried in this wall of text, right?

<!-- image -->

**Don Nguyen** 1:47:44
They're not easy. Yeah, yeah, that's why if you don't talk to me, it take me a lot longer to work backward. I mean, what do you call this? Not top down, but bottom up of approach. Really nearly impossible, yeah.

<!-- image -->

**Erickson, James** 1:47:57
Yeah.
Yeah.

<!-- image -->

**Don Nguyen** 1:48:01
They're like a industrial spy, man. Send me to a spy on freaking Verizon technology.

<!-- image -->

**Erickson, James** 1:48:08
Yeah, this shows physical port layout on the.
Specifically, well, see these are Oracle this month.

<!-- image -->

**Don Nguyen** 1:48:21
Oracle is Acme package. Same thing.

<!-- image -->

**Erickson, James** 1:48:23
Yeah, forty-five hundreds, and they're taking those out in exchange for forty-six hundreds.

<!-- image -->

**Don Nguyen** 1:48:33
Yeah.

<!-- image -->

**Erickson, James** 1:48:35
Um.
Which I think they still got this wrong. If this is supposed to represent 45 hundreds, I think they still got a.
Oh, let's see pair 1A, pair 1C.
Well.
Oh, there you got it right. Okay, Here's what the the the forty-six hundreds look like. Um.
SVC one has four ports P0123 and they all four of them connect to router one along with its Wancom 0 for management.

<!-- image -->

**Don Nguyen** 1:49:23
Been too hot beat back-to-back.

<!-- image -->

**Erickson, James** 1:49:23
Management and SSH. Yeah, management, SSH, alarming messaging.
To the IDN network through this interface. These two are just to load, share and and share health information, heartbeats between the two pair, between the two devices in the pair.
And then?

<!-- image -->

**Don Nguyen** 1:49:51
Yeah.

<!-- image -->

**Erickson, James** 1:49:54
#2 has the same ports, all of them.
Um, going to router too, yeah.

<!-- image -->

**Don Nguyen** 1:49:58
Bundle, yeah.

<!-- image -->

**Erickson, James** 1:50:03
So.
Um.
P0 and P1 are the customer ones and Mohan, you'll recognize that from, you know, this goes back to every 4600. You know, we recently went over this with the.

<!-- image -->

**Kanumuru, Mohan** 1:50:17
Up here.

<!-- image -->

**Erickson, James** 1:50:25
DNG.
VR Yeah. So the customer side, signaling and media or PO or P0 and P1P2 and P3 are the carrier side.
Um.

<!-- image -->

**Kanumuru, Mohan** 1:50:43
But but but there are those are the ones that we report internally but sometimes in the.
Actually, they call it the Nick one, DLC, ILO, et cetera, et cetera.

<!-- image -->

**Erickson, James** 1:50:55
Yeah, they'll or or in the in the in in the descriptions actually is the the I speckle should have it labeled P0P1P2P3 the physical device if we see it.
photo of it anywhere in here. The physical device might be labeled net zero, net one, net two, net three, but then you also get the descriptions from
The configuration you've been you're you're tasked with converting says M0M3M2M3 or 00 and 10.
Um.
And.

<!-- image -->

**Don Nguyen** 1:51:54
So what what side that we cut over had the ACME package we've so far?
The of them S and one.

<!-- image -->

**Erickson, James** 1:52:01
All of them. Anything that anything that has.

<!-- image -->

**Don Nguyen** 1:52:07
Can you say the SN1?

<!-- image -->

**Erickson, James** 1:52:07
Uh.
No, anything that's an SPIP site.

<!-- image -->

**Don Nguyen** 1:52:11
S pip side OK, OK.

<!-- image -->

**Erickson, James** 1:52:14
Well, it's called an S pip for the S being super node, right? Super pip.
But what? So when I say SPIP, I'm specifically talking about the 10 gig MX960S.
But the S the Oracle S 4600 SPCS are not only used in SPIP super nodes, they are also used in.
Um.
I bridge I micronodes and and you'll see here also.
Um, all these PIP devices?
Uh, where's a good picture of this?
Um, you'll see the the Sbc.
Between customer and carrier, well, the SBC Acme 4600 SBC is also used in IDA and SIDA.
And those are.
The same hardware.
Um, but they only use the carrier side. They don't have this.
Customer piece that has the customer provisioned and dedicated configurations on them.

<!-- image -->

**Kanumuru, Mohan** 1:53:58
Today.

<!-- image -->

**Don Nguyen** 1:54:00
Got it.

<!-- image -->

**Erickson, James** 1:54:01
And that is used just for signaling, so like 1 gig signaling, SIDA and IDA and micronodes.

<!-- image -->

**Don Nguyen** 1:54:10
So the NNI router, what do we call them? Do we need to know what the heck they are on the on that side like a VA?

<!-- image -->

**Erickson, James** 1:54:17
Yes, but how many? How many times will you get it wrong? A lot, because this NNI router on the S pip are old. They're old Cisco's.

<!-- image -->

**Don Nguyen** 1:54:21
It is.
Oh, they're not. The Juniper MX PE.

<!-- image -->

**Erickson, James** 1:54:37
Well, actually I think I've seen some that are we. The problem is we don't have access to them and the teams that do don't don't communicate with us well.

<!-- image -->

**Don Nguyen** 1:54:44
Oh.

<!-- image -->

**Erickson, James** 1:54:50
So the the the yeah, they're they're owned. Mhm. Yeah, most definitely.

<!-- image -->

**Don Nguyen** 1:54:51
But are they owned by Verizon? Those the private network?
Oh, since oh Cisco 7200 crap like that.

<!-- image -->

**Erickson, James** 1:55:03
Um, I I don't even know what what types of I think they're.

<!-- image -->

**Don Nguyen** 1:55:03
2.
****.

<!-- image -->

**Erickson, James** 1:55:13
Yeah, I I can't say, but like I was what I was saying though is that the teams that.
Like for the Viv, the VA routers, we have Jim Harper, right? He does the the AS701 VIV MPLS cloud, the public IP P/E routers.

<!-- image -->

**Don Nguyen** 1:55:40
Who?

<!-- image -->

**Erickson, James** 1:55:42
They give us good engagement. They continually talk with us, you know, because that's the real backbone, this backbone for the PIP stuff between.
Their business customers. Remember, these are all.

<!-- image -->

**Don Nguyen** 1:56:03
Yeah, yeah, yeah.

<!-- image -->

**Erickson, James** 1:56:05
You know, reach business retail customers.

<!-- image -->

**Don Nguyen** 1:56:06
Dedicated customer, yeah.
Yep.

<!-- image -->

**Erickson, James** 1:56:10
Um.
They these Cisco's here. Um.
And this whole MPLS cloud, I think they are looking to.
Well, I don't know. I don't know what they plan on doing with it or anything, but the teams that run this do not engage with us very well. Like if we were to, we we can't log into these devices ourselves to check their configuration.

<!-- image -->

**Don Nguyen** 1:56:37
Hmm.

<!-- image -->

**Erickson, James** 1:56:43
We can't get permission to change the descript, the descriptions ourselves, um, or anything.
Um.
But yeah.

<!-- image -->

**Don Nguyen** 1:56:59
So in the cutover we just replace light for light, right? And keep everything the same.
And hopefully correct, yeah.

<!-- image -->

**Erickson, James** 1:57:04
Yep, config conversion. You just keep everything the same. In fact, converting this this router from say an M10I or a previous.
MX960.
I mean it's not trivial, but it's it's a lot easier because they can't change the configuration too much because they have tools that log on to the routers and and use an automation.
Tool to provision each customer on here, right?

<!-- image -->

**Don Nguyen** 1:57:46
Right, right.

<!-- image -->

**Erickson, James** 1:57:47
And and that also accounts to for why you'll see some that aren't working. If they were provisioned wrong, it can really screw some stuff up, right?

<!-- image -->

**Don Nguyen** 1:57:55
Yeah.
Yep.

<!-- image -->

**Erickson, James** 1:58:01
The um.
But when you're doing a config conversion that involves like S pip 12345 or seven or eight.
You you can't. You have.
Only few things change at a time and nothing changes this according to.

<!-- image -->

**Don Nguyen** 1:58:30
Let me ask you now, the the SSPIP S stand for super or?

<!-- image -->

**Erickson, James** 1:58:30
Um, well, if you.

<!-- image -->

**Don Nguyen** 1:58:36
The PIP is a private. The S is super, right?

<!-- image -->

**Erickson, James** 1:58:37
Yes.
Yeah.
Yeah, super. And and that's why I.

<!-- image -->

**Don Nguyen** 1:58:46
Is it a a super it's 10 gig and above?

<!-- image -->

**Erickson, James** 1:58:46
And specifically the MX 960s are the, yeah, 10 gig and above.

<!-- image -->

**Don Nguyen** 1:58:51
OK.
OK.

<!-- image -->

**Erickson, James** 1:58:57
All right.

<!-- image -->

**Don Nguyen** 1:58:57
Man, I wish I had this quick conversation with you. Like, freaking like, second week of work, dude. Damn. And I, you know, I banged my head again on the wall, man. I studied this **** back and forth. I said, what the hell?

<!-- image -->

**Erickson, James** 1:59:00
I know.
Yeah.

<!-- image -->

**Don Nguyen** 1:59:09
And I try to correlate this convict with the SRX and then here and there it's solid list connect. I don't know who to ask.

<!-- image -->

**Erickson, James** 1:59:15
Yeah.

<!-- image -->

**Don Nguyen** 1:59:16
And I'm not supposed to can call Scott Hiller because that's a that's a car no sin ****.

<!-- image -->

**Erickson, James** 1:59:24
Yeah, um.
All right. Well, that's all the time we have right now. I mean the.

<!-- image -->

**Don Nguyen** 1:59:30
Yeah.

<!-- image -->

**Kanumuru, Mohan** 1:59:35
You used every minute.

<!-- image -->

**Erickson, James** 1:59:37
Well, there's a lot of stuff to go.

<!-- image -->

**Don Nguyen** 1:59:37
Yes, yes, yes. I think next time let me, uh, let me talk and then uh, I I need to talk to Hassan and see and Mohan, I I don't know, maybe you got ahead of me, but uh for me.

<!-- image -->

**Kanumuru, Mohan** 1:59:47
No, I did not go through any LLD document. I'm I I I did not. This is all just doing the working with James and just getting here and there some, but not no hierarch, not overarching. What are?
Flow and the devices involved. What are they do? No knowledge of that.

<!-- image -->

**Don Nguyen** 2:00:07
Yeah, right, right. Well, lucky for you, man. So I'm working with Verizon. They drill me on this **** and they expect me to know this stuff.

<!-- image -->

**Erickson, James** 2:00:10
Yeah.
Yeah, now.

<!-- image -->

**Don Nguyen** 2:00:16
Already like second week of work.

<!-- image -->

**Kanumuru, Mohan** 2:00:16
How? What is your interaction with them? What type of interaction you have with them?

<!-- image -->

**Don Nguyen** 2:00:21
Go on a meeting and talk to them. They want proposal or this and that, but so far not as I and then Greg Hunt asked it and then would we do no **** man. I was not ready dude. I was freaking not like the the the the technology is easy but I do not know.
The back the the back story. What the hell is for? Why?

<!-- image -->

**Erickson, James** 2:00:45
Yeah, yeah, and eventually.

<!-- image -->

**Don Nguyen** 2:00:45
I don't know the back story. I had no idea what the hell's going on. I just I there's the the I look at config I see AE lacks the VLAN scheme there there there's a there's a method of the method but I do not know why until I go to the stuff and I understand now it's just.
In this week it's kind of slow. It's give me time to sync back and go slow. Make sure I'm not doing any crazy ****.

<!-- image -->

**Erickson, James** 2:01:13
Yeah.
Mhm.

<!-- image -->

**Don Nguyen** 2:01:19
It's just a matter of shut, no shut, right? You do AE, you shut, no shut, you moved up. I kind of know what you're doing. You know you you shut, no shut as a Cisco lingo, right? Shut no shut. That makes sense. But there's a there's a why. I do not know why until now because I work with you on the on the how to, you know, bottom up config T.

<!-- image -->

**Erickson, James** 2:01:34
Yeah.

<!-- image -->

**Kanumuru, Mohan** 2:01:35
Hey there.

<!-- image -->

**Don Nguyen** 2:01:38
You know, shut, no shut. You move to here, L2, you move to the side and you appear there. I kind of get idea. But when I talk to Greg Hutton, they hit me on the Y man like this ****. They say why do you want to do this? I I.

<!-- image -->

**Erickson, James** 2:01:40
Yeah.
Yeah.

<!-- image -->

**Kanumuru, Mohan** 2:01:50
No, this was as a part of that issue that Ray came up when you're applying the root cause analysis type of thing. What is the?

<!-- image -->

**Don Nguyen** 2:01:58
Paula too is some of the conversation. They expect me to on top of this game by now, you know?

<!-- image -->

**Kanumuru, Mohan** 2:02:03
No, no, I understand. But is this in the context of when you have to explain why it went wrong?

<!-- image -->

**Don Nguyen** 2:02:07
Yes, yes, yes. A lot that too. Yeah. They expect me to be in the trenches, you know, with them, you know, to be be able to communicate with the talk to Charles and and and the other guy Sullivan and this stuff and then expect me to know all the little.

<!-- image -->

**Erickson, James** 2:02:22
Mm.

<!-- image -->

**Don Nguyen** 2:02:27
New on stuff, but I don't.

<!-- image -->

**Erickson, James** 2:02:30
Yeah. Yeah, no.

<!-- image -->

**Don Nguyen** 2:02:31
It's good. It's good. Just try by 5, man. ****.

<!-- image -->

**Erickson, James** 2:02:34
Yeah, there's there's a lot of that and things will start slowly clicking in and the more you sit down to to read it, the the better.

<!-- image -->

**Don Nguyen** 2:02:47
Because to be honest I I work on similar project like this like 2-3 years ago with AEMMX 304 similar for another client you know on my own similar AE 100 but I I I don't use I I use AE two and three and four and 6/7.

<!-- image -->

**Erickson, James** 2:02:57
Mhm.

<!-- image -->

**Don Nguyen** 2:03:03
Similar concept that all this, all the jazz stuff, but not for voice, it's just for MPLS, EVPN stuff, but similar. But I am the one to build that stuff so I know the background. I know the stuff in the back of my hand. I don't have to read LOD stuff to understand what's going on because it's my design, you know what I'm saying? I know the back of my head.

<!-- image -->

**Erickson, James** 2:03:04
Yeah.

<!-- image -->

**Don Nguyen** 2:03:21
But now going to Scott Hiller and Atip stuff, I had no idea what they had in mind and some of the LD stuff, unless James, you work with this stuff like you did today, you only get like 4050% up at most.

<!-- image -->

**Erickson, James** 2:03:39
Yeah.

<!-- image -->

**Erickson, James** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-16T05:01:48.739598+00:00",
      "canonicalTerm": "SPIP 7/8",
      "reviewCardId": 12,
      "term": "SPIP 7-8"
    },
    {
      "appliedAt": "2026-06-16T05:01:48.739935+00:00",
      "canonicalTerm": "SPIP 7/8",
      "reviewCardId": 12,
      "term": "S pip seven and eight"
    },
    {
      "appliedAt": "2026-06-16T05:02:40.454573+00:00",
      "canonicalTerm": "Low Level Design",
      "reviewCardId": 3,
      "term": "LLD"
    },
    {
      "appliedAt": "2026-06-16T05:02:41.521036+00:00",
      "canonicalTerm": "Virtual Service Node",
      "reviewCardId": 4,
      "term": "VSN"
    },
    {
      "appliedAt": "2026-06-16T05:02:43.089413+00:00",
      "canonicalTerm": "VoIP infrastructure VPN",
      "reviewCardId": 5,
      "term": "VIV"
    }
  ]
}
-->
