---
created: 2026-06-16T05:22:20.850825+00:00
updated: 2026-06-16T13:39:04.833872+00:00
concepts:
- ISPEC Review
- layer one validation
- Verizon Process 101
entities:
- A10
- A8
- A9
- C3
- CCR
- Citrix
- Czirjak, Gery
- D1 and D2
- Don Nguyen
- Erickson, James
- Flex tap
- ISPEC
- Kanumuru, Mohan
- LLD
- master port assignment list
- Netscout PFS 5010
- NFID
- packet broker
- PRF
- Reddy, Resha
- Rob Lebue
- Scott Stroud
- SFP
- SPIP
- Venue
- VSN
indexes:
- '[[Team Index]]'
description: Transcript of a Verizon Process 101 meeting on ISPEC review, covering LLD-to-PRF/CCR/NFID workflow, port-assignment validation, ISPEC tab checks, D1/D2 access, SFP/hardware review, and discrepancy handling.
source: Verizon Process 101_ ISPEC Review (James E_Gery) Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-16T05:22:20.850825+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 2905,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ ISPEC Review (James E_Gery) Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-ispec-review-james-e-gery-1781587340897180000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-16T05:22:20.850825+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ ISPEC Review (James E_Gery) Transcript.docx",
  "sourceSha256": "037d9862b40ab0c522d158fd853664f5e35580a0ab7c499f1ecee1744b5aae85"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Transcript of a December 2, 2025 Verizon Process 101 meeting covering how Verizon migration engineering artifacts progress from LLDs through PRF/CCR/NFID into ISPECs, and how reviewers should validate port assignments, layer-one readiness, hardware/SFP details, regional ISPEC variations, and discrepancies against old-router connectivity.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 ISPEC Review (James EGery)-20251202\_153320-Meeting Recording**

December 2, 2025, 8:33PM

1h 30m 43s

<!-- image -->

**Kanumuru, Mohan** started transcription

<!-- image -->

**Kanumuru, Mohan** 0:04
OK, recording is started.

<!-- image -->

**Erickson, James** 0:17
This document where everybody can see it and then share it out.
I don't know. Gary, do you want to step us through this?
See.
Actually, let me take that back. Instead of sharing windows, share my screen there.
OK.
So um.
Gary, you still with us?

<!-- image -->

**Czirjak, Gery** 2:02
I was sleeping. Is that OK?

<!-- image -->

**Erickson, James** 2:07
Sleeping in lunch and learn. Ah
Oh, um.
As you can see here, Gary kindly.
Put down some notes for us here.
Um.
So the ISPEC. Installation specifications. We last time we talked about the.
Um LLDS.
And.
There's a lot of processing on the Verizon side to get from an LLD to, you know, where we actually have an I spec.
Part of that is going through.
Um, like a uh.
The PRF and the CCR uh.
Um process um.
Let me see if I have.

<!-- image -->

**Kanumuru, Mohan** 3:29
PRF and CCR PRF stands for.

<!-- image -->

**Erickson, James** 3:33
PRF I don't know what it stands for, honestly. Um.
Let's see if we can get.

<!-- image -->

**Kanumuru, Mohan** 3:41
See you.

<!-- image -->

**Erickson, James** 3:43
Myself logged into.
Show you what these look like. They're the first stage once we've identified a site.
That's gonna, you know, need a migration. Um.
Scott Stroud steps in and it's his. He writes the technical specifications, the engineering specifications that are going to be required for the hardware that goes in. That includes.
Power space. So he does site surveys, that kind of thing. Um.
And then compiles that into a PRF.
So let's see.
Let's see, where were those stored at? Does anyone remember where these PRFs? What are they?
This is what happens when I close tabs. All right, Gary, do you? Do you know where that?
That like that spreadsheet is on the Google Drive.

<!-- image -->

**Czirjak, Gery** 6:31
Spreadsheet. You mean the thing that we were reviewing for NOR and HSJ and all that?

<!-- image -->

**Erickson, James** 6:37
Yeah.

<!-- image -->

**Czirjak, Gery** 6:37
Let me let me get it and I'll just pass it in the chat then.

<!-- image -->

**Erickson, James** 6:55
Gonna have to pull up an an entirely different Google.
Chrome entry as well too.
Um.

<!-- image -->

**Czirjak, Gery** 7:56
That should be it, I hope.

<!-- image -->

**Erickson, James** 9:12
OK, so um from one one other thing that they bring into the they create these docs that I'm sharing right now. These ones are um.
Kind of master port allocations.
Um.
So the LLD.
Is.
Created.
And as part of that, once you know they have.
Um.
You know, Gen. 2.5 base port allocations that are gonna be common for all the sites. Um.
Sites. Um.
And then as they go and build them out, you know, Scott creates one of these for.
Let's see, this is this one was done recently. This is NZZSN one.
Gen. 2.5 No a a site specific port allocation, right? So he takes.
Some of this um.
All right, looking for that.
Link here.
Here we go.
Can't access item of it.

<!-- image -->

**Czirjak, Gery** 11:28
Are you trying to find the link I put in the chat, James or something? Oh, that was an HPE one, not a Juniper.

<!-- image -->

**Erickson, James** 11:32
Yeah.
Oh.

<!-- image -->

**Czirjak, Gery** 11:39
User ID.

<!-- image -->

**Erickson, James** 11:45
See use edge for that.
Still want to be signed into Google Sheets.
Um.
Why is Chrome asking which thing I want to?
Log in as anymore. I want these all linked. Um.
All right, time. Um, all right.
The uh.
Find my Google account.
It was an HPE like.
Google Drive, Gary.

<!-- image -->

**Czirjak, Gery** 13:51
Yeah, it's the Google Drive that we got everything got moved to.
You had the user ID there a few minutes ago.

<!-- image -->

**Kanumuru, Mohan** 14:20
Yeah, it will be in the format of your.
That your e-mail address dash.
Hpe.com at Verizon extension.
Yep, that's the one.

<!-- image -->

**Erickson, James** 14:53
Yeah, but it needs to be done over here in this one.

<!-- image -->

**Kanumuru, Mohan** 14:56
Yeah, so here also I take the juniper.net, try to switch switch the account with.
Which I think try try the switch.

<!-- image -->

**Erickson, James** 15:28
I think the whole, my whole chrome just forgot my profiles. I think that's where we're coming from this. But um, the
You're signed in as I don't want.

<!-- image -->

**Kanumuru, Mohan** 15:43
Yeah, sign out and then maybe you can sign in again.
Hello.

<!-- image -->

**Erickson, James** 17:37
All right. Uh, that's one.
OK, yeah.
So these are an example of the PRFS that Scott creates. Um.
Gives a CCR number. Usually they open a couple of CCR. There's a phase one and a phase two. Phase one is just all this first batch of information they engineer where.
In the Uh.
Where which rack and aisle they want their space? Um.
The um.
Take take in the specs from all the devices that they from the devices that are going to be installed and make sure there's power for them all.
And suitable Breakers and grounding. So all that stuff comes in through the first CCR.
And we don't pay much attention to that, just as long as we have the the IDN.
Telemetry information comes through as this doesn't even happen in the first stage, the first CCR this has. The second CCR is the installation where they actually take all of the the gear that's been ordered, the POS.
Those are delivered and on site. Um.
Or soon to be and.
They um.
They already know, right? Uh.
What port's gonna connect to what? This is just a list of all those connections that they expect to see on a completed install.
For it. So this is the the first engineering doc that we you might see just one of these from any given site to to build out this sheet though with all of these.
Port information. Yeah, they're just referring to this.
This diagram, right? Um.
They're referring to this master.
Port assignment list. Um.
For migration, there's.
There's still room for us to catch errors here. This they don't. They're not always perfect on these kind of things. I mean, they're every site's different, but they also might be finding.
You know, um.
The site survey should count out how many, let's say a bricks that's on location or a utility server or whatever, right? Any interface that's live on the old devices that needs to be migrated.
Should have an entry here in this master port assignment list of what they're you know, where they're moving it over to, but.
Um.
That isn't always the case. So you may need to go and you know find out is this device on you know when when we do an audit we we we we're we're only.
Most of our solid information we know is gonna come from the old router, the old devices, and we do, you know, without actual input from Verizon.
We don't know even if the descriptions are correct, right? So there's a lot of gaps in what we do know. We just have to rely that to a certain extent that the descriptions are correct, that the ports that are up do have live equipment on it that's required, you know.
These are assumptions we make live interface. Yes, it's required for you know initially, yes, it's going to be required and then if it if it's not on here or in.
You know this PRF? Um.
Then we should be raising a a flag with Verizon and say hey this utility server or this bricks or you know.
Isn't represented. It's on, you know it's it's connected and on in the old device, but doesn't appear to be connect represented in the new engineering docs.
So that's where we would want this flagged even before it gets to this this I specs base stage you you catch it in the PRF. Ideally you know we haven't really been able to do catch it that early.
Um, but now that we've got this.
Document available to us. Yeah, we should be able to catch these things.
Um.
Once we hear that this I spec is um.
Finished. They've taken this document, fed it through there and there.
Uh, other teams. These are Fred. Um, let's pull up some of these.
Um.
Brad Rubio or any of these other DE representatives. They're the ones responsible for taking the engineering information from the PRF. Um that that CCR um.
What's the new? What are they calling it now? HH, not HRID.

<!-- image -->

**Czirjak, Gery** 25:43
NFID.

<!-- image -->

**Erickson, James** 25:44
NFID Yeah, they're taking these these NFIDs, you know, and creating an ISPEC. These have everything in them. There should have everything.
But that's part of our job. This is why one of the reasons we're having this call is if we didn't catch it in the PRF or on the master port allocation. Um, and it's not here in the PRF. Um, or we didn't catch it there, then we need to go.
Find it in what's what's a good.
NFID.
To search for there.
Gary, do you have one handy?

<!-- image -->

**Czirjak, Gery** 26:47
Uh, no.

<!-- image -->

**Erickson, James** 26:51
No.

<!-- image -->

**Czirjak, Gery** 26:51
How about 3065820?

<!-- image -->

**Erickson, James** 27:02
So you just put the CCR number and NFID.

<!-- image -->

**Czirjak, Gery** 27:05
Yeah.

<!-- image -->

**Erickson, James** 27:05
Um.
Is yeah, MS1MZ ZSN one so.
If you don't see it here, it's likely not in here yet. You know, if you're sure of this number, um.
Sometimes it takes a minute on an initial install to get these.
Generated, but you know, and this one's already gone through a few different revisions. Um.
I.
Don't generally like the PDF, but it's good for viewing when you're still while you're still in Citrix, right? Um.
Otherwise, you know I'm usually downloading this into.
Um.
In it's uh.
In its Excel form.
Click on that and it should automatically download as well.
Once you have that downloaded you can't open U these.
Uh.
In.
Yeah, looks like I've already got it. Um.
You can't open these in Citrix. We don't have Excel and it's worthless on Google.
Let's go to copy that. Um.
Through from move it from Citrix into here. Um.
Host machines.
Downloads.
Pretty simple process here.
And now we should have this.
Yeah, I uh.
So this is the one I just downloaded.
Um. Easy, you know. Um.
Um.
The uh thing is, you you do end up with a lot of.
Just.
Formulas for things.
um We'll get to that in a minute. I mean, we we do use this to create cut sheets, and you don't necessarily want these.
So this is usually an easy.
Um.
And hide everything.
Copy the entire sheet.
And then paste it back in with just the values.
And that's what I start with when I start. Um.
You know I do that for every applicable page, right?
Um.
Unprotected.
Yeah, unhide everything.
Unhide everything.
Oh, select everything. Yeah, select everything, then unhide it.
And then copy it.
Paste just the values.
OK.
Oh, where's her?
So this um.
This is the venue site. Let me, I'll go ahead and take.
If you don't already have access to venue.
Let me go ahead and put it in the chat.
There's your link to venue. It should be working on Active Direct Verizon's Active Directory. I think you saw when I first logged in it. There's something a little weird with it. It doesn't.
Think you want to log in? Like it thinks you're a new user. It takes a beat and says OK, what's your new user's information? If you back out of that and just log in again with the same credentials, it'll let you in. It's just a bug in there.
Um.
Have you seen that issue there, Gary?

<!-- image -->

**Czirjak, Gery** 33:20
No, but I have a Mac and trash, so it's different. I have a different sort of behavior.

<!-- image -->

**Erickson, James** 33:21
Athenia.

<!-- image -->

**Reddy, Resha** 33:23
I haven't seen it either though. I haven't seen. Usually I just go straight in and I just click on venue and it goes straight in. What's the link that you're seeing when you maybe it's the log out link.

<!-- image -->

**Erickson, James** 33:30
Yeah.
No. Um.

<!-- image -->

**Reddy, Resha** 33:39
This is what you're getting for venue.

<!-- image -->

**Erickson, James** 33:43
Yeah.

<!-- image -->

**Reddy, Resha** 33:44
I don't get a login at all.
It just auto logs man.
That's interesting.
Huh.

<!-- image -->

**Erickson, James** 33:55
Huh.
So the first time I come to it, you know, after I haven't been there for a while, it will ask like give, create your profile, create your account, back out and then.
Log back in and it seems to work so.
I don't know if that's part of the.

<!-- image -->

**Reddy, Resha** 34:25
Well, it seems like it's different for different people. Like I don't get a login page at all.
I haven't had one for years.

<!-- image -->

**Erickson, James** 34:32
You're gone. You're gone through Citrix.

<!-- image -->

**Reddy, Resha** 34:36
Yeah.

<!-- image -->

**Erickson, James** 34:40
Interesting.
Um.
So there's really no mystery behind this one. You know how to use venue, just the link and how to log in. What you're looking for is usually, you know, going to be here, just the.
Check the revisions. Um.
And then from there.
Uh.
Yeah.
Um.
Considerable attention to detail. That is correct.
Um.
So you've you've probably noticed that each different site we work with has different VSNS and different combinations of VSN or maybe just one and.
Um.
Different ways they use the SPCS make the difference between whether it's an SPIP VSN or if it's a IDASSIDA or if it's a.
Uh.
This uh.
Or a D skip or an I skip, right? Those all have SPC components to them, but they're used differently. So you know, pay attention to you'll you'll notice it once you see the architecture and how they the existing routers and how they name.
Name there.
there uh,
Logical logical routers and that kind of thing. But yeah, like I said, we we already introduced you to the to.
engineering documents. Pretty much, you know. This is what they've created for port allocations and
before the I spec, and then, yeah.
The ISPEC itself. Um.The ISPEC itself, you know one of the first things I always look at is to just make sure they have D1 and D2 cause you're not getting anywhere with the layer one.
Uh.
Validation until you have D1 and D2 and can actually log in to the devices.
Rob Lebue should have had is responsible for the installations. Um. And if you have any questions, feel free to hit him up on Slack or or e-mail, you know he'll usually
Want to work with us anyway if he's having issues with, you know, the console connections not working or if you have some issue or he's just not plain not seeing the hardware.
Behave the way it should. He'll be welcome to having a relationship with you to to be able to.
Ping each other, you know, on Slack and and ask, you know, straighten things out for them, get things done a little bit faster if you want to go that route.

<!-- image -->

**Reddy, Resha** 38:49
Yeah.

<!-- image -->

**Erickson, James** 38:51
Sorry, Rachel, was that something? Were you saying something?

<!-- image -->

**Reddy, Resha** 38:54
No, he's he's a really good resource to have. Him and Rob Lebou and Scott Stroud work together on setting up all the details for these CCRS, which it feeds into the ice specs. So they would usually if you have a question, he would he if he can't answer it, he'll go back to Scott Stroud and they'll figure it out and come.

<!-- image -->

**Erickson, James** 38:57
Yeah.

<!-- image -->

**Reddy, Resha** 39:14
Back to you.

<!-- image -->

**Erickson, James** 39:17
Yeah.
Um.

<!-- image -->

**Reddy, Resha** 39:20
So.

<!-- image -->

**Erickson, James** 39:22
So the format of these, they do have a lot of these tabs that are just hidden as well.
Especially if you're working in the EMEA site. Um.
They might hide tabs that have.
You know, a lot of these are just feeding the the formulas we saw before. You might not need a lot of these. There's no reason to really.
Um. Review them. Just know that they're there. Um.
But then uh.

<!-- image -->

**Reddy, Resha** 40:17
I will also mention that you'll notice differences between ice specs by region. So anything that's created domestically looks all basically the same, but if you look at one like we James had a fun time with one from.

<!-- image -->

**Erickson, James** 40:18
And kit.

<!-- image -->

**Reddy, Resha** 40:32
From APAC, very different.

<!-- image -->

**Erickson, James** 40:37
Yeah. Oh yes, that was a fun time. I've and.

<!-- image -->

**Reddy, Resha** 40:40
Yeah.
It's very different. It depends on who creates and what information they think that they would need for their on-site people. Sometimes it sometimes you'll get tons of information, sometimes they'll be missing information. Really depends.

<!-- image -->

**Erickson, James** 40:54
Yeah, yeah.
Um.
Like uh.
The engineering that goes behind these Netscout, the PFS 5010, this is the packet broker and these fibre taps the the there's some that are.
the just, you know, we we know the ports, but don't.
Uh, it's hard to represent in an I spec, so they as long as they're not, uh, leaving out important information, you know, um.
A9A10 and A8 should be all of our data ports. Um.
And A8 is always copper, A9 is always new fiber runs.
Um.
And then 810, sometimes they're new runs, sometimes they're just swinging an old run, but it's kind of a miscellaneous tab, you know, sometimes they rely on it really heavily to.
To count every.
You know connection that.
They, for whatever reason, didn't decide to put in a nine or eight, a eight, and
But you can see here every flex tap, every monitor port, every port to the packet brokers is accounted here for our connections.
Um.
The you know, use your best judgment. We might not even need any of this information if it's already in place like there this isn't.
Like they've already got the packet broker and the Flex tap installed and all we're doing is adding new.
Or or moving the live um.
Moving the WAN circuit from the old router to the new router.

<!-- image -->

**Reddy, Resha** 43:32
Yes.

<!-- image -->

**Erickson, James** 43:34
You you uh.
For example, you might only be dealing with flex tap one or flex tap two.
Then we have.
Uh 34567.
89101112 These, I believe, are all going to um.
Hip.
S Pip Wan.
Um.
Network B. But we're our devices are going to be all be network A, and then network B will be umm the other side going to whichever PE router.
Um, that lines U with all of this we were just seeing here, right? Uh, flex tap one.
And and and so match this, match these two up. Tap 2, tap 3, tap 4, tap 5, tap six. Those are SPIP 7 and eight. So if this was an SPIP one through 5, they'd keep numbering 89101112.

<!-- image -->

**Reddy, Resha** 44:59
S.

<!-- image -->

**Erickson, James** 45:00
Uh, to get the other.
Other ones. Um.
And then their corresponding ports for the monitor output the the.
The splitter that takes the light over to a different port.
On the Netscout the the packet broker. Um.
And.
You know, I think a few of you have seen a migration, you know and have seen where they have to jumble these around. They they went through and made changed their base assignments there on the packet brokers on these 5010s.
Um.
They so sometimes that is not a service affecting thing. Then cat usually directs that. That's not our gear, but.
you know it's something to watch out for, just so you don't, and um just so you're aware of it when you're reviewing the ISPEC, trying to make heads or tails over what's connected where
Um.
And.
Uh, yeah, so.
Let's go back here. Um.
Showed you the design documents besides the LLDs. We have those two master port assignments and the PRF that they create.
Um.
Yeah, usually the the POs and the gear, the the the hardware.
Um, Bill of materials.
Hasn't been um.
Too far off, except for when you get to these SF PS. Mike and Ray should do a do a good job, you know, making sure we have everything we need ordered, but it can get so confusing.

<!-- image -->

**Reddy, Resha** 47:57
Yes.

<!-- image -->

**Erickson, James** 47:57
So many times around that circle, through that loop, trying to tie out these numbers here for orders in the 1st place, and then you don't think about it until six months later when you see the ISPEC.

<!-- image -->

**Reddy, Resha** 48:11
Yeah, because things change, right? You, you do a FOA and then you realize that there's an issue and then you order and then you know you have to go back and make sure that they've actually made the updates to the additional, the additional sites for the ISPECs and the CCRs. So you have to make sure that when you get the ice spec, you validate against.

<!-- image -->

**Erickson, James** 48:14
Yeah. Oh, yeah.

<!-- image -->

**Reddy, Resha** 48:31
The design, but also against what you believe is needed.

<!-- image -->

**Erickson, James** 48:35
Yep.

<!-- image -->

**Reddy, Resha** 48:38
Absolutely.

<!-- image -->

**Erickson, James** 48:39
Yeah.

<!-- image -->

**Reddy, Resha** 48:40
Oh.

<!-- image -->

**Erickson, James** 48:42
So um.
Pay and pay attention to I I've actually had to do this on a couple of I specs is.
You know, once we're solid with the with the number of runs, right, we're we've layer one checked as much as we can for the live circuits, the ones that should be up even during the the initial rack and stack.

<!-- image -->

**Reddy, Resha** 49:01
Yes.

<!-- image -->

**Erickson, James** 49:12
Install tasks these.
Some of these like our management runs should all be connected. These shouldn't need any SFPs though, but we.
But then you get to these that are going these temporary links, the current between existing Gen. 1 or router and the new Gen. 2.7 router, right?
These are new runs. They should be up during the layer one validation step. So we have to make sure they have the SFPs there, you know, and you know we should solidify.

<!-- image -->

**Reddy, Resha** 49:52
Yes.

<!-- image -->

**Erickson, James** 50:03
All of our permanent runs. These are permanent runs between router one and router, new router one, new router two, or you know, and then we start dealing with.
The.
The firewall connections, which are all gonna be fiber. Um.
And our these are port mirroring connections directly from the new routers and directly to the packet broker. No taps, no WAN, no BGP running over these.
These are just um.
Port port mirroring output connections to the packet broker. This this is fairly standard, but you'll get a feel for it with all the especially as you review the existing routers.
You know, try to figure out you know what what device is connected where on the existing routers and and it's always helpful if you do figure out hey.

<!-- image -->

**Reddy, Resha** 51:02
8.

<!-- image -->

**Erickson, James** 51:17
Bricks #1 is connected to or is going to be connected to 700. Where is it currently connected on the old router? If you ever find out that information or have to go through this exercise, you know.
Just put it in there, put it in the install notes, put it, you know, in the I spec, put it in the cut sheet. Just track it somewhere. The earlier we can get that information, the better, because that'll make all the difference in the world for, say, config conversion.
Um.
That kind of thing.
So because you noticed all of the rest of these engineering docs I showed you, nothing here mentions the old routers except for these temporary links. Um.
Wherever they are. Yeah, here's, you know, this is the only time you'll see these.
Old routers referenced, they don't. They're just concerned with what's going into the new box. We're the first time we we couple that with, well, what's on the old box.
And and how do we reconcile a bricks that's connected but isn't being used?
Are we ready to orphan that and leave that on the old router after the migration so it's never seen again on the network? And you need to be very sure of that step before we do that, right?
So that's one of the reasons we do this I spec review. Find anything that might be missing, compare it to when compared to the old routers if they.
I don't know where it's gone with that now.
Any other questions so far? Oh, yeah, the
The type and form factor of the SFPS.
Um.
2. Gen. 2.7 is all leaning towards these SFP pluses with, you know, occasional SFP's, but for temporary link, temporary fiber links. Remember, we're still dealing with XFPs.
Um.
We might need some temporary copper SFPs, but on the old routers we shouldn't need SFPs for copper. They should be built in ports.
Yeah, some of these tabs a three through 5, not directly relevant.
No.
They're good for um.
Like these notes are step for step instructions on even if they need something um sent back um or you know.
Tested, removed all of this. It should be clearly defined in this. That's not necessarily our task to audit this or or.
Get Make sure this is correct. That's that's still up to Verizon, but if you ever have a question about a certain component, a certain note that you might see somewhere else in the run list.
This is where it's at uh a four and a five tell you tell you where um
What it where it's coming from, where it's going? Um.
the other tabs.
like B1 show any given hardware item listed here gives a purchase order. Umm
So if you do need track down SF PS or or a a specific card or something, this is where you're gonna find the PO number for it.
Uh, then there's um.
An overall summary material with just the quantities.
You can probably see a few of these are.
Might be off a little bit. Um, again, it's.
Just the fact that they have this number in the right place or or or just that it's wrong.
Doesn't mean it's not correct. This this tab also has to be reconciled with.
This tab and this is where you know the actual build out this tab C3 we do check because this tells us.
For every card, which slot it's going into? Um.
From base chassis all the way up to SFP. So base chassis, MPC, MIC port.
And the SFP assigned to it.
Um.
You know this nine times out of 10 is correct. I think they they pay more attention to this because this is directly informed from you know these tabs you might if something doesn't look right, feel free, you know compare your.
Copper runs. How many SFPs you need to support all these copper runs with?
With this with C3 um.
And just make sure they've got all their ports. Sometimes they've got their port number and they can't read the front of the router, the front of the card right on site. Sometimes you might be working with Rob Le Bue and his installer on site.
To to sort out which SFP goes where. Um.
And you know.
Ideally, we catch it early. We we make sure this can, you know, nothing's.
obviously obviously wrong here. Um, but you.
Rob Labue will usually catch these during the install if there's a massive problem, but you know, having us double check it isn't gonna hurt.
Any questions up to here?
Console and Ethernet connections. Um.
These are very specific to per device. Um.
You know some of them like your SBC.
You know it usually has five connections, whether it's one for management, 2 for carrier, 2 for customer for an SBIP, or it's one for management and two for carrier side for a SIDA.
Install or you know here's some information on the.
KRGR routers. Um.
Bricks.
These.
Should have only ideally management for these new bricks is all run to IDN. Occasionally you'll see them the management port connected to the MX960.
But as long as we have the the test, sometimes there's one bricks and sometimes there's two. You know the there's. Luckily these are not call processing gear, they're just call verification gear.
We decided early on in the project, confirmed with Verizon. This is not a showstopper for us in terms of a maintenance window when a bricks, you know.
Isn't connected right? We just need to get it worked out as soon as we can and then.
There's there's still a Net Scout that uses us for Ethernet management. Utility servers are on their way out, or at least the the version of utility servers that use VMware with multiple multiple.
Um.
Physical interfaces that represent different VMware machines, virtual machines.
On virtual switches.
Um.
The.
Yeah, and honestly, um.
10 gig fiber versus 1 gig. Um.
This is a little bit new. We haven't been dealing with many 10 gig except for the Wan or interconnects. Um, but now we're bundling multiples of these together. That's something to watch out for. Make sure you're you're watching
You know your your.
Speeds on these ports with their if they're intended for 10 gig or one gig, because we still have.
Firewall SRX is that are using one gig fibre and 10 gig or not one gig interfaces and on the same SRX supporting 10 gig interfaces.
Um.
810, yeah.
Alliance cables which we migrated from existing notes. Yeah, we kind of glossed over this the the from and to.
Ideally we have correct information and where it's moving from.
Some of these we don't. That's why I always said, you know, anytime you audit or look at the ports available on the old existing routers, write it down once you can identify what what device it's connected to.
Um.
That way if it's incorrect here.
We can fix it. Um.
D1 and D2. Again, these are our
What we received back from the IDN group from our telemetry request requested their console ports.
Console Services, Serial Services and Ethernet.
Ah, what a good court summary.
OK, router crosslinks 8 times.
10 gig Gary, didn't you say there was some concern what you weren't sure why they were using a certain number of cross links? Was this it for the SPCS or a cross link?

<!-- image -->

**Czirjak, Gery** 1:04:55
No, I just thought that they were excessive.

<!-- image -->

**Erickson, James** 1:04:59
They were what?

<!-- image -->

**Czirjak, Gery** 1:05:00
I just thought their cross link requirements were excessive, but that doesn't mean much.

<!-- image -->

**Erickson, James** 1:05:06
Oh yeah.

<!-- image -->

**Czirjak, Gery** 1:05:12
Like all these nodes send what? Maybe a gig of traffic?

<!-- image -->

**Erickson, James** 1:05:18
Oh yeah.

<!-- image -->

**Czirjak, Gery** 1:05:18
Total.

<!-- image -->

**Erickson, James** 1:05:21
Yeah, this is new actually having 10 gig connections up to the PIP for your SPIP services or SPIP VSN.
Um.
KR is just going to be 1 gig.
One single per router.
Oh, router crosslinks. So they don't know this, but.
The distinction here is these eight are going to be AE0, and these ones are going to be AE151 through 158.
Um.
For SPIP services per per.
S PIP.
VSN.
This we still the customer side of these SPIP VSN needs to be physically separated from AE0 and all the rest of the carrier traffic that uses it. So these SPIP the the only ones that use per VSN cross links now are.
Represented by these 410 gig connections each.
Um.
And here again there these are for AE0.
E 0.
um, or a one hundred temporary, a one o four through one o nine for these temporary cross connects to the legacy.
Um.
Again, these just get ripped out anyway, but 10, 1 gig means a pair of 1 gig per VSN on a SPIP 1 through SPIP 5 node.
You don't necessarily need all that for.
Or you'd use five of them for SPIP 7 and another five for SPIP 8 if it's that kind of node.
Um. So cross links are kind of tricky sometimes to understand. Just grab me or Gary, if you have any questions, or Nick Nick's pretty well versed in that.
Yeah, having set it up all up in the lab himself. Um.
All right, yeah. And a port analyzer. Sometimes there's two, sometimes three. Um, Geo probe.
Do you mean?
I don't know which Geo probe is only connected to router one, Gary.
Mhm.
Or do you mean the?

<!-- image -->

**Czirjak, Gery** 1:08:23
That was supposed to be brick session that I got in there.

<!-- image -->

**Erickson, James** 1:08:30
OK.

<!-- image -->

**Czirjak, Gery** 1:08:31
I'll fix that.

<!-- image -->

**Erickson, James** 1:08:33
Yeah, firewall. Sometimes it's three. It's always 31 gig E That's our base, but depending on the VSN, you might have an additional 210 gig.
Um, per firewall chassis.
Um.
And.
For tap, are we talking the flex taps here or what was these?
What were these referencing?

<!-- image -->

**Czirjak, Gery** 1:09:16
Oh, I don't remember. These are the taps going to the public IP right 'cause they have 4 10 gig links now on the 40 gig node.

<!-- image -->

**Erickson, James** 1:09:17
This is probably out of sum.
Yeah.
Yeah, and they're the only information we need for them that's relevant to us is that they're LR single mode connections.

<!-- image -->

**Czirjak, Gery** 1:09:41
I guess for what it's worth, guys, the one you probably heard this from James a few Times Now. The problem with doing the ISPEC reviews is there's a lot of variations and it's very unclear what should or shouldn't be there.

<!-- image -->

**Erickson, James** 1:09:42
SM.
Mhm.

<!-- image -->

**Czirjak, Gery** 1:09:57
Unless you have a lot of experience like James does. So if you get at all confused, you can't find your answers in the all of these or whatever, you're probably best to ask James cause nobody else knows.

<!-- image -->

**Erickson, James** 1:10:11
Yeah, you get a few sites under your belt. You know with this, at least as far as config conversion, you know by the time you've done the config conversion, you'll know the site inside and out. You'll have all the notes and everything you need for that kind of.
Work. Um.
And you'll have. You should have a better understanding. Just have someone.
Check your work. Uh.

<!-- image -->

**Don Nguyen** 1:10:39
So, James, what are the typical discrepancy?
That what a typical thing that doesn't line up.

<!-- image -->

**Erickson, James** 1:10:50
This is one of the things that doesn't line up like they always this block here is easy to just cut and paste and you'll see the ordering of these in this very specific order of.
Port IDs on an SBC.
Um.
I don't know why, but it's a very
You know, it's it's pretty much just a cut and paste job, right? And you roll with it, right? Even though the use of the designation P to identify the port, there's nothing on the SBC that meant that would suggest that this port.

<!-- image -->

**Don Nguyen** 1:11:26
Yeah.

<!-- image -->

**Erickson, James** 1:11:36
Identifier should have the letter P in it.

<!-- image -->

**Don Nguyen** 1:11:39
Oh, OK, so it's not that obvious label on SBC so the cable tech on site can spot it on the money.

<!-- image -->

**Erickson, James** 1:11:48
Yeah, yeah.

<!-- image -->

**Don Nguyen** 1:11:48
It's all the cable label correctly. I mean, I don't know what is. Are they the cable pre pre-made, pre-label and they ED approved or just like I've been willy-nilly stuff?

<!-- image -->

**Erickson, James** 1:11:53
Exactly right.

<!-- image -->

**Czirjak, Gery** 1:12:00
Oh, they're never wrong. Ever.

<!-- image -->

**Erickson, James** 1:12:01
Well, no, at least there's there's there's some standardization to it, right? The fact that it is cut and pasted from here to here means you can expect to see it in the I spec in the same way.

<!-- image -->

**Czirjak, Gery** 1:12:04
Oh.

<!-- image -->

**Erickson, James** 1:12:20
Go to copper runs for.
SBC right? And you know anytime they're mentioning um P2, it'll be represented as one slash 0.

<!-- image -->

**Don Nguyen** 1:12:28
Yeah.

<!-- image -->

**Erickson, James** 1:12:43
Or this one will be represented as 0/0. This one is commonly referred to as M3, and that one's commonly referred to as 1/1. So this might be what you see in a description on the.
Existing routers.
Um.
And whether or not this makes some this might make better sense to up an operations person. So we leave it like this in the description, but for you know, installation folk.
That I don't think it matters to them.

<!-- image -->

**Don Nguyen** 1:13:25
OK, OK. They just go by two different thing and OK.

<!-- image -->

**Erickson, James** 1:13:29
Yeah.

<!-- image -->

**Don Nguyen** 1:13:31
Yeah, that's, yeah, because that's a that's a deadly deal. It misses because yeah, people refer to the same thing with do with the two different name alias and and nickname stuff, yeah.

<!-- image -->

**Erickson, James** 1:13:37
Yeah.
Yeah, what's what's really notorious for that also is the utility servers. Um.
The utility servers and I'm not seeing.
Any of those here CM zeros?
Where are LRCM0s?

<!-- image -->

**Czirjak, Gery** 1:14:03
I think this site didn't. I think this site didn't have MZZ.
The example I stole, I think I think I took from somewhere else.

<!-- image -->

**Don Nguyen** 1:14:15
So the Verizon team, they they design, they then they build a cable run list and give it to a remote hand to wire the stuff. We're only concerned about the MX connectivity only, right? The rest we assume they are correct, right?

<!-- image -->

**Erickson, James** 1:14:29
Yeah, yeah, the very underlying.
Um.
Function of this migration is to move a live or.
It's configured a specific way from one MX to another MX and the port ID will change and we have to know you know what it's changing to, but that's the the.
Underlying crux of the migration, everything else. There's really no protocols to run on these except for BGP and port mirroring and VRRP.
I mean, from the totality of the the architecture here, there's really not anything too complicated about it. It's it's just.
It.
The LLD spells out what changes are being made to the architecture and then ports are assigned even before the ice back is created.

<!-- image -->

**Czirjak, Gery** 1:15:41
Yeah.

<!-- image -->

**Erickson, James** 1:15:51
And we just need to make sure we can match up our port assignments that are given to us on the new gear with what's being moved from the old device.

<!-- image -->

**Don Nguyen** 1:16:05
So the LE is a top down and the I spec basically uh bottom up basically and they'll have to match 100% right?

<!-- image -->

**Erickson, James** 1:16:17
They don't have to match, you said, or do.

<!-- image -->

**Don Nguyen** 1:16:20
They have to. Otherwise we have quirky stuff. It doesn't work.

<!-- image -->

**Erickson, James** 1:16:21
Yeah, yeah, yeah. Well, like I said, these.
The CM0, these are utility servers and we're counting like 6 on one side and five on the other or you know, depending on what that.
Specific um utility server is used for. This is from a.
Um.
Pip Bridge site, this ISPEC.

<!-- image -->

**Don Nguyen** 1:16:55
You a different thing like guy like Chevon and the other guy, I forget the name. They should notice by heart, right? The the onsite guys.

<!-- image -->

**Erickson, James** 1:17:03
They know, yeah, they know for their gear by heart. Um.

<!-- image -->

**Don Nguyen** 1:17:07
OK, OK.

<!-- image -->

**Erickson, James** 1:17:11
Which one is this DNGBR?

<!-- image -->

**Don Nguyen** 1:17:13
Yeah, I remember the one of the guy name is Shavon. The other guys forgot name Joe or something.

<!-- image -->

**Erickson, James** 1:17:14
I'm looking for.
Well, Joe Joseph is.
a different site. There's Anas, Abid, and Shavon are all on the same team. The T6 team has Joseph. He's for Ocas. Umm

<!-- image -->

**Don Nguyen** 1:17:31
A nice, yeah.

<!-- image -->

**Erickson, James** 1:17:43
But yeah, they you you'll be surprised what they don't know about their own platform. I mean, if you ask, OK, your NSRS device, what kind of?
Uh chassis. Is it being compute chassis? Is it being run on?
And they don't know. It's a, you know.
HP net DL380, Netra 380 or whatever. So the you know it's in the I spec though or should be it's.

<!-- image -->

**Don Nguyen** 1:18:15
Nature, yeah.

<!-- image -->

**Erickson, James** 1:18:28
Uh.
Or at least when that Netro was, when that NSRS was first installed, it was it was installed with the same style of detail that you know that calls out port IDs.
And so there are engineering documents that that support it.
Or the We just don't necessarily have access to all of them. Oh, that was the new page. That's not what I wanted.

<!-- image -->

**Don Nguyen** 1:19:06
I remember you only focus on 89810, right?

<!-- image -->

**Erickson, James** 1:19:06
That's trying to.
A8A9 and A10, yeah.

<!-- image -->

**Don Nguyen** 1:19:11
8910 Yeah, those three, yeah.

<!-- image -->

**Erickson, James** 1:19:17
That's what I'm looking for right here.
You know, having this rack elevation view is definitely handy. I don't know that it's entirely accurate. Hopefully it is, but you know, I haven't always had to come back and refer to this during and install the site installer.
should know where these things are. They did the site survey. Um.
And.
You know, that looks about right for a SPIP one through five SBC RAC, you know.
S pip one has the first 42345.
This looks like fun site. I mean, all told here there's um.
5.
Well, we don't necessarily have a three and four for all of these, but you know, upwards of 50 to to 100 connections to support all of these SPCS, right?

<!-- image -->

**Don Nguyen** 1:20:44
Yep.

<!-- image -->

**Erickson, James** 1:20:45
So.
Um.
That's luckily the SP CS go pretty quick.
There I once the once you get into a groove in the migration window, the.
We we have everything identified. We need to move, what cables we need to move and just sit back and watch them.
Watch the orts go down and watch them come up on the on the new box.

<!-- image -->

**Don Nguyen** 1:21:20
Mm.

<!-- image -->

**Erickson, James** 1:21:24
Um.
I do highly recommend getting to know some of the the servers that are connecting to the MX960S in detail, the passing knowledge of what they would what.

<!-- image -->

**Don Nguyen** 1:21:44
Any particular like DODO 360 Gen. Gen. 8.

<!-- image -->

**Erickson, James** 1:21:44
What type of device they are?
No, actually focus on the SPCS first. They'll be easiest. Just take a picture of one in the in the lab at some point just so you have a reference to what it should look like in in production.

<!-- image -->

**Don Nguyen** 1:21:55
OK.

<!-- image -->

**Erickson, James** 1:22:08
Mhm.
The the other ones, yeah, the Broadsoft servers or the NSRS servers or even you know the F5 from an OCAS or a.
Um. Or an SRS F5? Get to know what those look like. Um.
And where the ports are on the back of those, that'll help your deal with things in the maintenance window when you're talking to the on-site tech and help you know, you know what they talk about when they're talking about.
A port, a specific port number on those.
Um.
Any other questions?

<!-- image -->

**Don Nguyen** 1:23:10
No, no. I don't know what to ask. Hassan Mohan, you guys already know this stuff better than I do, so.

<!-- image -->

**Hassan Rauf** 1:23:23
Yeah, no, I mean, we've been run through this, uh, a few times.
So yeah, so I have some idea. I might ask more questions when I'm gonna start working on the the cut sheet for the DSS and and.

<!-- image -->

**Erickson, James** 1:23:29
Mhm.

<!-- image -->

**Hassan Rauf** 1:23:44
Yeah, no, so far so good. Thank you.

<!-- image -->

**Erickson, James** 1:23:46
Yeah, did you follow what I was showing like when you on the I spec when you?
Um, like all these fields that have just these variables here.
Um, if you unprotect.
Uh, unhide all the columns.
Copy.
Paste.
Just the values and.
You know, that's the that's the best starting point I can give you for a cut sheet. The other thing is you see how the table. I also like to unfreeze.

<!-- image -->

**Don Nguyen** 1:24:31
Yeah.

<!-- image -->

**Erickson, James** 1:24:42
The pains. Um.
Unfreeze the ****, but you'll see when you're highlighting something in the table, you'll see the table design.
Up here, Excel treats a table separate from a range these days, and that is sad. Um.

<!-- image -->

**Don Nguyen** 1:25:11
But this is Google sheet, right?

<!-- image -->

**Erickson, James** 1:25:14
No, this is Excel.

<!-- image -->

**Hassan Rauf** 1:25:14
And this is an Excel file, yeah.

<!-- image -->

**Don Nguyen** 1:25:14
Excel. OK, OK. Oh.

<!-- image -->

**Erickson, James** 1:25:16
So what I usually do is I copy the whole table.
Come below it.
Paste.
Just the formatting first or I'm sorry or paste.

<!-- image -->

**Don Nguyen** 1:25:32
Mhm.

<!-- image -->

**Erickson, James** 1:25:36
Just the values first.
And then paste the.
Um, but now you see I can highlight any of these.
And you don't have this table design option here, yeah.

<!-- image -->

**Don Nguyen** 1:25:50
Well.
Restriction, yeah.

<!-- image -->

**Hassan Rauf** 1:25:54
Got it.

<!-- image -->

**Erickson, James** 1:25:56
And then I can, you know, I do a spot check, make sure I didn't lose any any data. Um, then
Just completely delete the freaking thing.

<!-- image -->

**Hassan Rauf** 1:26:10
Yeah, it makes life easier.

<!-- image -->

**Don Nguyen** 1:26:11
Yeah, because the the guy who built the stuff had restriction there, so.

<!-- image -->

**Erickson, James** 1:26:16
Yeah.

<!-- image -->

**Hassan Rauf** 1:26:18
Got it.

<!-- image -->

**Erickson, James** 1:26:20
I I usually clean it up a little bit more, and you know.
Like.
Clear everything out of there.
Um.
There's a couple of columns here that are.
Never gonna be used really.
There.
Let me clear these out.
And that's starting to look like a respectable cut sheet right there.

<!-- image -->

**Don Nguyen** 1:27:03
The trick, man.

<!-- image -->

**Erickson, James** 1:27:03
Um.
Um.
Pay attention to this OM4 if you don't already know that's multimode.

<!-- image -->

**Don Nguyen** 1:27:24
Is it good for duplex? Not not SCSI type? Is that the UP duplex?
Meaning the LCLC.

<!-- image -->

**Erickson, James** 1:27:33
Yeah, yeah, well, they should still have LC to LC here, but yeah, this is just a duplex cable, the two RX and TX bonded.

<!-- image -->

**Don Nguyen** 1:27:47
Yeah, not the news. Uh, ultra scuzzy type, right? Yeah, those are.

<!-- image -->

**Erickson, James** 1:27:48
In in just one pair.
No.
No, but you'll see the the difference in their notation where they use single mode for the the Wan.
Um, but all the land, say OM4 instead of MM4 or multi mode, whatever.

<!-- image -->

**Don Nguyen** 1:28:17
Yeah, that's a good notation. That's correct. Yes. Any. Yeah, yeah.

<!-- image -->

**Erickson, James** 1:28:19
Yeah, OM4 is correct. Yeah, it's it's as opposed to like OM3 or OM5 or whatever. They the installers need that information. We don't, but we just need to recognize it as being multi-mode.

<!-- image -->

**Don Nguyen** 1:28:24
Yeah.
Yeah.
Yep.

<!-- image -->

**Erickson, James** 1:28:37
Um, I don't know necessarily go into auditing which ones are straight through, which ones are cat 6, which ones are unshielded. Um.
Um.
I mean.
Ideally, they're just taking what's already on site and.
Um, or what's in the Lld?
Uh, according to.
Because this.
This one looks like it's right out of an LLD. Actually, not that I see it.
But uh, yeah.
As long as the installers and it matches the existing.
Um, I don't pay too much attention to exactly what kind of cable is being run those details. Um, unless it's fiber.
Um.
Gary, anything you feel we need to add to this discussion?

<!-- image -->

**Czirjak, Gery** 1:29:55
Oh, I feel I need a beer to add to this discussion if that helps.

<!-- image -->

1:29:59
Well, after this you get a beer.

<!-- image -->

**Czirjak, Gery** 1:30:04
It's 503, man.

<!-- image -->

**Don Nguyen** 1:30:06
No, I'm on 403. You're in Dallas Central Time. You're not in California. You're not in New York like other people. I know where you are.

<!-- image -->

**Czirjak, Gery** 1:30:18
I'm not in Dallas.

<!-- image -->

**Don Nguyen** 1:30:18
Now, like James, he got two more hours, so he's still in 3:00 mountain time.

<!-- image -->

**Erickson, James** 1:30:22
Yes, 3:00. I still got a couple hours to slave away. All right. If there's nothing else to add, let's go ahead and cut the recording.

<!-- image -->

**Kanumuru, Mohan** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-16T13:40:27.807940+00:00",
      "canonicalTerm": "ISPEC",
      "reviewCardId": 109,
      "term": "ice back"
    },
    {
      "appliedAt": "2026-06-16T13:40:29.448399+00:00",
      "canonicalTerm": "ISPEC",
      "reviewCardId": 110,
      "term": "I spec"
    },
    {
      "appliedAt": "2026-06-16T13:40:31.970579+00:00",
      "canonicalTerm": "ISPEC",
      "reviewCardId": 111,
      "term": "ice specs"
    },
    {
      "appliedAt": "2026-06-16T13:40:45.390619+00:00",
      "canonicalTerm": "Rob Lebue",
      "reviewCardId": 113,
      "term": "Rob Lebou"
    },
    {
      "appliedAt": "2026-06-16T13:40:58.048714+00:00",
      "canonicalTerm": "Gery Czirjak",
      "reviewCardId": 115,
      "term": "Gary"
    },
    {
      "appliedAt": "2026-06-16T13:41:26.894240+00:00",
      "canonicalTerm": "Rob Lebue",
      "reviewCardId": 123,
      "term": "Rob Labue"
    },
    {
      "appliedAt": "2026-06-16T13:41:26.894576+00:00",
      "canonicalTerm": "Rob Lebue",
      "reviewCardId": 123,
      "term": "Rob Le Bue"
    }
  ]
}
-->
