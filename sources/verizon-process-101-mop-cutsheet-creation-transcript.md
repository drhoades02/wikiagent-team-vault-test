---
created: 2026-06-17T02:51:24.857289+00:00
updated: 2026-06-19T13:41:16.216018+00:00
concepts:
- cut sheet
- DPC 2.5
- DPC 2.7
- FOA
- generic MOP
- I spec
- MOP
- Verizon Process 101
- VRRP failover
entities:
- Ericsson Engine
- James Erickson
- MX104
- MX960
facets:
- December 11, 2025
title: 'Verizon Process 101: MOP and cut sheet creation transcript'
indexes:
- '[[Team Index]]'
- '[[Verizon Migration Procedures]]'
- '[[Verizon Process 101]]'
description: Transcript of a Verizon Process 101 training session on creating pre-migration cut sheets from I specs and preparing, reviewing, and validating MOPs for Verizon network migrations.
source: /Users/drhoades/VaultRaw/Verizon Process 101_ MOP_Cutsheet Creation Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-17T02:51:24.857289+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 4238,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ MOP_Cutsheet Creation Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-mop-cutsheet-creation-transcript-1781664684881422000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-17T02:51:24.857289+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ MOP_Cutsheet Creation Transcript.docx",
  "sourceSha256": "49372e6864e4ca22bb40f1e28008dbdf3af23caa502819d02df01c3f7717a2c1"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Meeting transcript for a Verizon Process 101 training session covering pre-migration cut sheet creation from I specs and MOP creation/review for Verizon network migrations, including MX960/MX104 strategy differences, FOA/generic MOP reuse, maintenance-window validation, and special handling for Ericsson Engine/TDM-related migrations.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 MOPCutsheet Creation-20251211\_130020-Meeting Recording**

December 11, 2025, 8:02PM

1h 13m 12s

<!-- image -->

**Erickson, James** started transcription

<!-- image -->

**Erickson, James** 0:11
All right, uh, let me share out my screen here.
Screen here.
So this is the Verizon process one-on-one session discussing cut sheet, pre migration, cut sheet creation and MOP creation.
Um.
The uh.
The cut sheets. Let me show you an example of one that we have here. Um.
Now they're gonna look vastly different depending on the site we're doing and and who created it. Just be who created the I spec. These are all based off the I spec. It's redundant to try to create one on our own.
Um. But let's um.
These are for example.
The um.
DPC.
let me the PC project Mx. 960 cut sheets. Uh, we shouldn't see be seeing many others.
Um, any that are?
My computer just wants to go really slow with this.
That our MX104EX is um.
So.
It's as you can see, it's got the same tabs.
As the these are the as the ice back, right? We just cut out a lot of the trim off a lot of the fat. Um.
And at the same time we should be, for example, grabbing notes on.
Um.
You know, a full reconciliation at this point is usually pretty good, right? You go line by line for each of these and and for example, these all refer to.
Infrastructure. A temporary or permanent infrastructure to permanent hip links.
Make sure they're all all accounted for. This is also your chance to regroup them. That's that's usually pretty handy as you're going through on the maintenance window. You know, usually you'll have SP CS that are.
You know any reference in this line or in this?
Table might be broken up between different devices, but you know the run numbers. Keep those handy. They're they're going to be your reference numbers when you work off this with the site tech.
But whether or not they're really in order.
Isn't really a big deal. What what we're trying to pay attention to it first is just that we have all of the devices and all of the interfaces that we expect to have and this is our chance to really.
Audit them and compare them to what's currently in production and.
Record that information. This is a cut sheet that's been used and taken notes on. For example, these green shades that I put in my local copy were used, you know, just to keep track of which one's been migrated.
Um.
You know, we.
Just because they are copper and they are new runs, we also have runs for our own telemetry and our own management between the MX960s and the IDN network. These are just the runs, but over here in D1D2 our our management.
Logical information, our IP addressing and.
Our.
Console socket numbers. Um.
For for connections, serial connections the the you know these should have already been somewhat reconciled in layer one.
Again, permanent links and temporary links there. Um.
They should already be up.
Or of at least checked in layer one. It's these ones here that don't get really checked in layer one as far as in reference to.
Where which devices are currently connected? So you do a quick scan, you know you you take your time.
And you find.
You know, where is CHTLR 8 referenced in the current config on the old routers? You find it's port, you write it down and I know it's gonna be migrated from.
Giggy 706 to Giggy 702.
Um.
Now how we get this kind of list from an ice back, I mean, um.
I think I showed you before in one of these previous.
Um.
Let's look in here. Here's one. Here's a nice spec, for example.
Um.
The yeah, from the I spec. I mean we I've mentioned this before, these I specs are a little bit difficult to work with.
I just closed the one I just opened. Oh, yes, I did.
Um.
And they these always come protected.
You unprotect the sheets that you need.
To edit.
So once these sheets are all unprotected. Um.
Can unfreeze ****.
And unhide your additional columns.
Uh, then.
Because I said what I one thing I like to do is.
We have all of these.
Um.
These formulas here O you select all, you copy it.
You paste it back in as just values.
You do that for all of these.
Um.
Unhide.
Copy.
Paste values.
Select all.
Unhide all the columns.
Copy.
Paste in just the values and that that should get.
And at this point, you know, as I'd mentioned before, we still have these referenced as a table in in Excel.
If you need to, we can also go ahead and delete some of these or you know, like I said, it's it's all just trimming the fat. The goal here is just to make this more readable on the fly, make it quicker.
Um, like with the um.
Once you have all of these adjusted, unprotected and the plain text in each field, if you need to move this to a new workbook, that's totally acceptable.
Um, except for it probably won't let you until you have.
All of these changed from a table.
Form into a range and I just do that by.
Grabbing everything that's in the table.
Or trying to.
Copy it. Come down to below the table.
Then you can paste the values in.
And then paste the formatting. Now you have an Excel just range rather than one of their, especially you know that what they would designate as a table.
With with its own design and style.
You've also with with unhiding these columns, you've also uncovered a couple of other tables.
These you can just delete.
Uh, or if it or if the delete is not available, it's because you have more than one table selected. Uh.
Yeah.
Let's do this.
Clear all here the headers level.
Um.
Oh, I see what it's doing because I have, uh, multiple sheets.
Yeah, that was fun. OK, yeah.
Make sure you only have one sheet selected at a time.
Because anytime you have more than one table selected, it won't let you delete the table.
Um.
Delete that one.
And now we already have.
Like that. OK, now now we're getting a respectable kind of.
Table here for a cut sheet. The this is going to be easier to work with, for example with the table.
You you can't do things, you know, like.
Moving around. Um.
The rows, I think you guys can work that on that on your own as long as we have all the relevant information.
Um.
You know it's somewhat easy to work with, take notes on, we can hand it to our on site tech and and go from there.
Um, you?

<!-- image -->

**Kanumuru, Mohan** 15:31
But James, uh.

<!-- image -->

**Erickson, James** 15:31
You guys know where? But yeah.

<!-- image -->

**Kanumuru, Mohan** 15:33
Yeah, on that A8A9810A8 copper, A9 fiber or vice versa and A10. So what at what? How can are in A10? Will there be any?
A duplicate information from either A8 or A9 or it's always A10 that there is no overlap between them.

<!-- image -->

**Erickson, James** 15:54
They're actually they're.
There can be. It depends on who created the ice back. If they're doing us a favor, they will be putting in, you know, or you know, besides just referencing.
A new run in A8 or A9 they they have in the past referenced it in A10.
Um, that does get confusing on the install side though, so I don't think you should expect that too much. Um.
But you'll be able to kind of reason that out, rationalize it, right? Because when you take a look at the 810.
And for this one, again, you can see there's a lot of different lines. Each one of them has a from and a to.
But for example in this one it doesn't have all these copper links that are in this. Um.
For the SBC one and two, all these copper links are not in A8, so that's just how they have happened to build out the I spec. It's not a big deal. Um.
Just know that.
Yes, some may overlap, but not generally, and we don't generally see them all in 810. This just does help immensely having him here because it means they've gone through the work of.
Determining where it's moving from the existing cable and determining where it's currently connected at on the remote end or on the current.
Router, right? Um.
Doesn't mean it's always correct. They might number this differently or or now. You know, now's our chance if we do see it here to.
to rework this and and um.

<!-- image -->

**Kanumuru, Mohan** 18:28
So the so, so So what is the logic of A8 and A9? OK, besides fiber and copper, so when should we include in A8 and A9 versus A10?

<!-- image -->

**Erickson, James** 18:29
Re uh.
Always, just always, always include them.
A8A9 and A10 just.

<!-- image -->

**Kanumuru, Mohan** 18:45
OK.

<!-- image -->

**Erickson, James** 18:49
Just.
I don't think I've ever done a cut sheet I didn't include these in.
So.
Um.
You know, trimming the fat means you know those two lines or those two columns we can delete. Um.
Can at least clear these out. Any other questions besides?
That um.
Let me go back here.
Do you guys know have access to venue or are able to download I specs? We we I think we asked that question before when we were reviewing I spec.
Tasks.
Um.
But moving on to the mop, the mop is probably a little bit more crucial at this stage. Um, the the cut sheet is.
Um, yes, it's a deliverable. Yes, we hand it to our.
You are.
Our onsite tech, but that really doesn't happen until much later in the process that it really becomes crucial to the to the process what really come.
Is.
What we really need to pay attention to up front.
Are these cut sheets? I'm sorry, these I spec mops. These mops.
Um.
So.
With the mops.
We've for each type of site that we have certified and you know, run in the lab.
We have already come up with a strategy for the migration. How are we the the the task by task process step by step all the way through from the first mainten first maintenance window to the to the last.
Right. The strategy usually is reviewed with Verizon before we create the the original generic mop or the lab mop, and that strategy is.
Um.
Uh should be on our uh Google Drive. Um usually presented as a PowerPoint. Um.
log back in here really quick.
OK, so um.
If we look at say Gen. 2.5 uh.
Here we should have a.
Migration strategy PA PowerPoint. This is the one that we've, um, spent time and reviewed with, um, Verizon.
Uh, the uh.
If you look at this, this if you have the right one right, selecting the right one for the right.
Type of node is sometimes difficult. Um.
The uh.
I think this is our older one. I think this is.
Let's go back to this one.
Updated migration strategy.
Yeah, so running through these um slide decks. Um.
Should give you a little bit of color, a little bit of idea of how.
We want to um.
Run the migration the uh.
Yeah, this one included some links with ICCP and that kind of thing. Here we see our existing devices and how we extend all our layer two out to new devices.
Um.
The uh.
Is there a way to advance this to the next frame? Uh
So this has some um.
Well, at any rate, make sure you, you know you, you know or or discuss it with me or Nick or Gary, just so you know the method, right, the the overall strategy.
Ideally, whoever created the generic mop did the certification in the lab is a good resource point if you if you can't make heads or tails out of this this slide.
Um. And and you need to talk to someone that's done it. Go back to, you know, whoever did the.
The certification because part of the certification is taking and validating that the MOP works without causing excessive outages. It it we've measured our reconvergence times for.
Um.
For every step in the mop at that point, I mean, honestly, during the maintenance window, Verizon doesn't complain too much about how long reconvergence takes at each step, as long as it's not like 30 minutes, right? As long as we don't.
Have like anything over 10 minute outage, 66 to 10 minute outage just to complete one step, right? But having certified this, we know at each step we've we should have already measured.
How long the reconvergence takes at each point? Um.
I mean, they understand, yes, it's a maintenance window. It doesn't really matter that much how, you know, they just want to make sure we are.
Trying to find the simplest, you know, method without causing too much pain for the rest of the network.
Uh.
The rest of these go back to.
These mops um.
Oh, let's go with RTOS in one.
Um.
So.
The the strategy, the slide deck that I showed you. They should outline any temporary topologies, any temporary links that are needed for it, and the sequence of tasks the.
Existing or the mop or the the generic mop? Um.
Is you there will be one available for you to to kind of build up build from.
Um.
If I can find my right.
Uh, let's see.
So, for example, this is the RTOSN one.
Here, make sure you're clear about what services are running here, which VSNS. If we go to review this with Verizon and we say of and we've copied this from.
Um.
You know, OCA, an OCAS site or something. If if this is not matching what they expect us to see, you know it's gonna be embarrassing for us. We we need to have this titled and.
So update that. Um, make sure we have the right VSNs.
Uh, and and we know.
You know, this is where it starts coming together. Really nothing. Um.
After you've done a few of these, um, you kind of know.
More or less. Um, it's easier to.
Know where.
Certain keywords appear, you know where where the variables are. Um.
Um.
There, like for example the introduction, there isn't generally a whole lot that needs to be changed from one. You know, if you're reusing the template, what needs to change in in?
In the introduction or um.
There's not much to change in Section 2 either. Um.
This is actually a pretty crucial piece. Always going to be coming back to this table here. Any device you're going to be logging into, you should have, you know, access information here.
Um.
The.
Yeah, with the isec number listed here.
Um. So that section, this line gets changed. It's usually highlighted, so you're not gonna miss it. Um.
Baseline information. These don't change if you find. However, if you want to like, these are the legacy routers.
Get as correct as you can with like.
Interface IDs. You want to just cover as many as you can if they if the if a XE500 doesn't exist for example.
Um key is not to be too um.
Too many changes to this document, you know. Um.
Well, for let's put it this way, for baseline checks, we want to be gathering more information and rather than less information, right?
These so don't necessarily want to take anything off here anyway. Just make sure you're you're grabbing as much as you can, you know, on this list or even more. If you happen to think of something else that needs to be added, go ahead and add it.
Um.
The uh.
Section 4 isn't where until isn't. It's not until Section 4 that we really get into a lot of the.
Details of how this all works out the first actual steps. So these are these do need to be accurate. Um.
The uh.
This is usually about where we start when we go through a review as well when we put this mop in front of Verizon to.
To review on a call, you know.
This is down here where it starts getting interesting, where they're gonna start. Um.
Finding our finding what needs to be changed or have their questions here.
For DPC 2.72.5 you know we are anything VRRP startup silent period gets deactivated. Um.
For the rest of the migration.
OK, I've got to try not to turn this into a mop review, but if you haven't seen a mop like this for the DPC, definitely check it out. We the the idea is yes, you do need to. The steps here should all be same.
From 1:00.
Um, from one site to another. So prepare, you know, preparing um.
our Gen. 2.5 devices, you know, preparing the L2 temporary trunks.
These.
are going to be applicable no matter which DPC site, just because this is required by our strategy. So we need to fill in per VSN. You know which of these are applicable, and which of these aren't.
For example, if this didn't have I, then none of these are relevant here and none of these are relevant.
So you kinda um.
Uh.
You'll know once you've um.
Kind of run through it. Ideally though, you aren't just copying an OCAS or an SPIP mop to run on an NSRS platform or or VSN, right? Ideally we've already done a FOA.
For every type of combination of um.
Of my site that we're going to be migrating.
Where did I have that?
There it is.
OK, you're just as far as when we go to this mops place, right there are.
The generic mop. Um.
Does exist.
generic migration maps, you know, I pack, Broadsoft, Broadsoft and SRS and Pip, Broadsoft and SRS. Oh, that's another one. Broadsoft, I pack.
Ocas, Nsrs, and Pip, Sida. So these are all have a a generic generic mop that was used. It's more than likely just the same the the mop that was used in.
In the lab, right when they did the certification. Um.
But if you have a site you're migrating that um.
We've already done a FOA for, then maybe pick that that FOA say.
Our next one, HSJ SN1 very closely resembles or or has the same VSNs as MZZ SN1.
Then it it might be easier to go to the MZZ SN1 and use the most recently updated version of the generic mop.
You know.
And and start from there. That way if there was anything that happened while we did you know and I only recommend this like I said if we've already done the FOA for it if if if this is a new one that we.
Um.
Haven't done, I haven't done the FOA for then yeah, go back to the generic mop and and use that, but um.
A site specific MOP is usually has more um.
Interesting changes to it, the, you know, updates to it that we need to pay attention to like lessons learned from when we did the, you know, did it last time. Let's see an example of that here.
Um.
Like this final checklist might be something or this whole.
SEC. You know this whole table here doesn't exist in the generic mop, but you're gonna want it for the next site that's.
Next SIDA.
Pip site is gonna need this too and um.
From there, where else?
Existing mop or the the the scope of the config conversion is ideally going to get us to the first day of the maintenance window. So where the mop comes in is it fills in the gap.
Um to give us a fine, you know all the commands that are needed to um.
Turn on, say, enable interfaces, disable temporary links, that kind of thing have to be included in the mop, anything that happens during the maintenance window to the production.
You know, now that we're we're migrating production traffic onto the new routers, want every, ideally every configuration command that we use to make it work is going to be in the MOP.
And in that.
That includes clean up. Um.
That includes changes we're making to the VA routers. Now these in a very distinctive color because these VA routers need to be.
need extra attention, right? They don't have a set mop, a separate mop for their um.
For their configuration, we've bid and won that work to perform these configurations on the VA routers for ourselves without involving OPS or support teams to do it for us.
So pay special attention to when we're adjusting anything on the VAs.
Here you know like this after we adjust, you know migrate the the primary WAN link to the VA routers, we have a set of other.
WAN links, you know, we're taking it step by step. We take um.
We move our IDNS interface.
We make sure the interface is U, BGP is U. We show the routes that we expect to see. Um.
Do that for all all of the Wan links and then validate.
And uh.
You know, validate that the interfaces are still up.
We do our VRRP failover. This is a a common or VRRP failover in a mop is.
Um.
We don't try to just add it at every step in the MOP, but there are certain strategic places where we add a VRRP switchover as well as or an SRX node switchover. It's.
Probably not going to specifically be called out in the strategy or depending on the site, maybe you feel you need a little bit of extra assurance that the new path that's set up through the new, you know, new interfaces, new.
Um.
Uh.
New routers that we have to see that it's actually passing traffic as expected. So we want to fail, you know?
Not at every step, but at strategic steps we are going to be failing over our redundancy features just to make sure that everything's working and so that needs to be called out appropriately in the mop. Right now we're just using failover or restart VRRP on the MX960s.
And to serve that.
Just cause on a SPIP device there are way too many VRRP sessions to go and set a priority for each one.
Just cause every um well.
A lot of these are going to be changing. I mean, I'm accustomed to these Gen. 2.5 MOPs and know these, you know.
Pretty well, but the mop for the Gen. 2.7.
You know, that's Nick. He'll know that. But there's still other types of migrations that are coming through on chassis migrations. Um, stuff for Um.
D-SIP or I-SIP that are gonna be different. So like I said, don't just get familiar with your own one document and and just update it. Try to follow along with the other types.
Of migrations and the the strategies that at the very least these strategy slide decks so we know what process, you know how the temporary topologies are going to look.
Um.
Yeah, I think when you run this slide, this has several different um.
Uh.
Dynamic changes that it makes to it. I just don't know how to step through it without actually running the thing.
Um.
Any questions?
I'm pretty close to our time here, I know.
This isn't a whole lot of data for, you know, a pretty.
crucial part of our work here. Um.
But like I said, these these mops are too large of a scope to really cover in in just one call if we want to get into some of the more specific parts and break it up into.
Um.
The different types of strategies we might use, like the layer two, layer one migration. When we do that, how many temporary links are being used or?
Why are we, you know? When do we?
Um.
Or what's the best way to add in temporary link configuration and you know?
That kind of thing. Any of these little um very detailed questions from.
Um.
from these steps. Um
Are probably we we can maybe even set up a another call later for that, but just just to know you know a a broad overview of these mops is you know.
We live or die by these. These are pretty much, you know, if if they're not accurate, if they're not doing everything, you know, showing each step and reminding us.
You know, to of our what we need to do to validate each step. You know, we're going to get dinged on them a lot if something goes wrong, right?
They they will go through several iterations. They'll go through updates. Um.
And a lot of times we just don't know. Um.
What we don't know. So it an update just blindsides us something we um.
Or or a better way to to run a task or or to um monitor for example our firewalls um or a better way to uh.
Um.
Validate at each step, yeah.

<!-- image -->

**Don Nguyen** 50:27
So, so James, I have a question. We have done to this stuff how many years now this strategy?

<!-- image -->

**Erickson, James** 50:38
Well.

<!-- image -->

**Don Nguyen** 50:38
How long you guys been doing this for like 5-6 years?

<!-- image -->

**Erickson, James** 50:40
No. Well, the strategy is different for each one. For DPC 2.5, the strategy wasn't even up solidified until earlier in two in 2025.
Um.
We well, yeah.
Because we tried.
Like I said, it's it's chassis dependent. It it the the two DPC 2.5 uplift really did blindside us. We we thought we could do say 60 cable.

<!-- image -->

**Don Nguyen** 51:08
Right, right, right.

<!-- image -->

**Erickson, James** 51:21
Migrations in a single night, but then we found out how tedious you know is the the servers that connect to us their their requirements that you know or or the something in the site you know.
Makes it so that the tech can't find the cables or how poorly the cables are run. You know, it just.
Using the same strategy we use for MX10 fours, just could not work with the MX960s just due to port density. So these ones and like I said, we probably won't see a migration for an MX104.
Again, after we do AMS and you know.
Yeah, I think AMS might be one of the last ones, but.
You know, at least now the strategy for an MX960 with the the high port density that spans over four or five days. It should be similar enough, but honestly that wasn't.
That update came late in the game. It came just as we were doing our second FOA or trying to figure out, you know, how to how to do our first FOA when when we couldn't move as many cables as we as we needed to in in a single night.
Um.
So that was only last January, so.
Everything else like the MX104S, yeah, I I would agree with you. Those ones we have been dealing with that similar strategy is something we dealt with for many times for for many years.

<!-- image -->

**Don Nguyen** 53:23
Well, the the strategy is the same, it's just the the number of cable. It's it's just a little bit too much for one window, right? It's just too much for a tech to do in one night, right? Or two night?

<!-- image -->

**Erickson, James** 53:34
Well, well, the strategy for the MX104 was because it also included switches was to do all of the all of the secondary side in one night and then move all of the and and and then decommission all the.
Secondary equipment from the existing side, you know the existing site, you know as you just decommission, take out, take the secondary equipment out of service and then you turn off the new.
Set of secondary router and switch.
And then you do that in the first night, and then on the second night you do the same thing, take out the old router and switch out of service, move over the cables and then turn that up. That has changed, you know.

<!-- image -->

**Don Nguyen** 54:27
Yeah.

<!-- image -->

**Erickson, James** 54:32
Significantly with the well for the MX960, again it's only one chassis, but instead of doing routing L3 and switching L2 at this in the same night on the secondary device.
We split it up to do just the.
Physical connections layer one and layer two on on the secondary stuff, which means over several nights we're not taking anything out of service, completely out of service until the last two nights.
So how do we keep everything up and in service and and operational while we while we move all those cables? And so yeah, instead of doing L1L2 in the same night.
We do L2 on the secondary stuff, L2 on the primary and then L3 on the secondary and then L3 on the primary. That's four nights with one backup window. So that's this the very high level overview of.
What we're going to be doing with the MX960's? Um.
Um.
Erickson engine is a little different. It does. There aren't as many connections on Erickson engine, so we we and we know we can do them all in one night. So we kind of kept with the old paradigm.
Doing everything to to be able to take out of service the old router 1st and then bring everything up on the new router, but they also blindside us with the you know I I know you want to take.
The old router out of service, but we need everything up all at the same time.

<!-- image -->

**Don Nguyen** 56:29
Well, if I remember correctly, you keep the L3 on the old.
All these the layer 1 to the new router, but L2 is still on the layer three is still on the old router, right? If I remember, yeah, that's the strategy.

<!-- image -->

**Erickson, James** 56:42
Yeah.
OK.
Yeah, that's a strategy for Um.
For the DPC I think with with.
Uh.
With Erickson Engine, the strategy is to bring up L3 services. That means IBGP and.
And any L3 interconnects between the routers, we bring those up and put them in service without trying to decommission without recycling IPS from a decommissioned router.
Because that's that's where it comes from. We don't want to, we can't overlap IPS, so we have to take something out of service.

<!-- image -->

**Don Nguyen** 57:34
Right.

<!-- image -->

**Erickson, James** 57:37
So with Erickson engine, we had to come up with a few new IP addresses in the same range and give temporary IP out out of address assignments. You know, we had to widen a couple of masks in a couple of VLANS.
So the Erickson engine kind of got its its own process just for itself, its own high, high level.
Strategy and it makes it a little. It makes it twice as hard to to keep everything straight when you're dealing with temporary IP addresses.

<!-- image -->

**Don Nguyen** 58:24
Why? So what? Why don't you just do simple stuff but move the IPS on old to new?

<!-- image -->

**Erickson, James** 58:34
Because in Erickson engine, that's what I was trying to say. Erickson engine, those garps, those the the Erickson devices and the the way the TDM service works, they were worried about.

<!-- image -->

**Don Nguyen** 58:39
Oh, the stupid stuff. They OK. They're very picky.

<!-- image -->

**Erickson, James** 58:51
Certain traffic flows are not truly fault tolerant or redundant.

<!-- image -->

**Don Nguyen** 58:59
Oh, OK, OK. You you told me this morning the guy who built this stuff, he built from a voice perspective. It's not stretched straight up by the book.

<!-- image -->

**Erickson, James** 59:01
So we need to keep.
You.
Yeah, yeah, exactly.

<!-- image -->

**Don Nguyen** 59:11
And then viewed. Yeah, yeah, I see why.

<!-- image -->

**Erickson, James** 59:14
So what they have to do is our when we were coming up with the new strategy right was OK, so we need to be able to migrate everything without.
Losing our layer 3 gateway interfaces, those layer 3 gateway interfaces once they go down for any significant amount of time.
Um.
Then we'll start losing flows that we're not going to get back up again easily and there would and it could cause a customer impact even earlier the next morning. So that one did come into a.

<!-- image -->

**Don Nguyen** 59:55
I got you.
So yet to find another IPS on the same subnet for the new MX.

<!-- image -->

**Erickson, James** 1:00:05
Um.
Yeah, exactly. So we had to and some of them we had to expand the the.

<!-- image -->

**Don Nguyen** 1:00:17
The subnet.

<!-- image -->

**Erickson, James** 1:00:19
The subnet mask to to find those IPS and that added a lot of extra work and then to clean it up. Yes, after the old devices are out of service, yes, clean up.

<!-- image -->

**Don Nguyen** 1:00:33
We condense the IV back again on the new trap.

<!-- image -->

**Erickson, James** 1:00:36
Yep.
Yep. So those are a lot more complicated and I think those are all going to be on my plate to deal with in the coming year.

<!-- image -->

**Don Nguyen** 1:00:49
Yeah, those are not typical networking problem. This is just a bloody mess. Whoever build this stuff didn't build correctly.

<!-- image -->

**Erickson, James** 1:00:56
Yeah, but the the upcoming stuff that you guys will be interested in for, you know, the DPC uplift, the.
The there's gonna be a whole new strategy that we're trying to we're gonna have to be thinking of for like micronode collapsing micronodes into.

<!-- image -->

**Don Nguyen** 1:01:22
The bigger one, yeah.

<!-- image -->

**Erickson, James** 1:01:23
A a bigger one or upgrading 2.5/2.0 gear to 2.7 and then collapsing super nodes increasing.
Capacity on the Wan, you know that's a whole nother batch of mop different with different tasks assigned to them. So you know it's it's not necessarily for this discussion to.

<!-- image -->

**Don Nguyen** 1:01:45
Bye.

<!-- image -->

**Erickson, James** 1:01:55
To talk about every different scenario that's gonna need a mop and and and because all the tasks are gonna be different, what we need to do is, you know, understand, yes, the the role, the role of the mop, yeah.

<!-- image -->

**Don Nguyen** 1:02:06
So help me understand this stuff. Hey James, sorry, sorry, sorry to cut you up man. Sorry. So so the the DPC you mean the the new line card 2.7 with the on the slot 8910 they're gonna be is that a different the the the line card?
2.5 to 2.7.

<!-- image -->

**Erickson, James** 1:02:28
Um 8 for.
From 25 to 27, yeah, something like that. I'm, I'm, I haven't been keeping up with some of that, what they've been discussing about how to do that and whose scope that falls under.

<!-- image -->

**Don Nguyen** 1:02:43
So basically it's a it's a a a a line card with better the what you call the line card with more 10 gig and 40 gig stuff in copper right. And just the way they lay out a little bit different right. That's it my it's.

<!-- image -->

**Erickson, James** 1:02:55
Yeah.
Well the the two dot the the new 2.7 for say.
Only comes with those MPC7s that are installed in slots 10 and 11, right? So you know the strategy that anything's going from any version to do that 7.

<!-- image -->

**Don Nguyen** 1:03:12
Yeah.

<!-- image -->

**Erickson, James** 1:03:22
Is going to include, you know, moving our primary Wan interfaces from card zero to card 10.

<!-- image -->

**Don Nguyen** 1:03:30
10.

<!-- image -->

**Erickson, James** 1:03:32
Yeah, so that kind of thing. Um.
The uh.
But like I said, and that's even gonna get even more confusing cause you know that's a straight up conversion from 2.0 to 2.7 or 10 to 27. But the tasks that they're going to be asking us to do in in future migrations that are.
You know, collapsing.
Um.
Exist, existing, you know, shutting down a whole node just so we can collapse it onto an existing node. That kind of migration, we haven't even come up with a full strategy yet. We have a very.

<!-- image -->

**Don Nguyen** 1:04:26
Well, it's a concept now. We haven't built the strategy to do that and wouldn't test it yet, right?

<!-- image -->

**Erickson, James** 1:04:30
Yeah.
Yeah, exactly. Exactly.

<!-- image -->

**Don Nguyen** 1:04:37
So are we expecting to finish all this stuff by next year?

<!-- image -->

**Erickson, James** 1:04:37
O.
Yeah, actually I think, well, if not the BAU stuff, the business or the rest of network stuff will some of that stuff might even see it by the end of this year 2026.
For FOA work, but I think.
Mainly we'll be seeing rest of network stuff for.
Um.
Just getting everything on 2.7 or 2.5, whichever is appropriate. I don't know, that's a project management question.

<!-- image -->

**Don Nguyen** 1:05:23
So from from the right, but from a from a MX960 perspective, you're not moving from platform platform, you just reconsolidate some of the interface, right? That's it.

<!-- image -->

**Erickson, James** 1:05:37
On some of them, yes, but not all of them. And it and there's, you know, knowing when to do that and when it's a a complete migration, you know you'll it's and especially like I said, the role of the mop is to.

<!-- image -->

**Don Nguyen** 1:05:40
Yeah.

<!-- image -->

**Erickson, James** 1:05:55
Um.
It it, it really is kind of.
The the best practice for any network operations, you document exactly the change that you're going to make and you submit it along with the Kirk. The processes to getting that to that point is.
Yes, first you take your generic. You update it the best you can. You you you get a draft going. We we we review it internally as a team first.
Make changes and updates. Review it with Verizon. Next, make changes and updates, and then review it again as necessary with Verizon.
And then attach that as part of our supporting documentation into the Kirk system. And you know, if anything goes wrong and we haven't deviated from that mop at all.
It should be very easy to tell, you know, from where we were at the mop, you know, more or less what what happened, what where we failed, what we need, what changes we need to make in the mop.
And it's a lot easier conversation with with Verizon if our mop is as accurate as it can be and it's not and we don't deviate from it.
In the migration window, it's harder to explain to Verizon why we made configuration changes that are not in the mop, you know, during the maintenance window.
And some of that can be answered just by break fix stuff, but that's that's what we're trying to avoid is is having that discussion make sure we have you know everything is.
And that, like I said, that's that's the role of the mop. Um.
Any other questions?

<!-- image -->

**Don Nguyen** 1:08:16
No, Hassan and and Mohan, you got too cool, man.

<!-- image -->

**Hassan Rauf** 1:08:26
No, I've I'm in. I've been working on with Nick. This is gonna be I think our third site. I'm working on actually preparing the mop and the cut sheet. I'm almost done. I'm gonna send it to Nick to review.

<!-- image -->

**Erickson, James** 1:08:40
Mhm.

<!-- image -->

**Hassan Rauf** 1:08:43
And the points you mentioned about I spec and everything I understand and things are quite a lot available in the I spec before we even start and the more permanent like you said it's gonna go with the respect to the kind of SPC the side.
And breaks all those things which are connected to those things and you're gonna schedule in the same way R2 and R1 like those kind of things.

<!-- image -->

**Erickson, James** 1:09:13
Yeah, yeah. Which side are you working on with Nick? Is that a lab mob or?

<!-- image -->

**Hassan Rauf** 1:09:21
DESSN1.

<!-- image -->

**Erickson, James** 1:09:25
Oh, OK, yeah. DESSN1. OK, I'll look forward to reviewing that. Hopefully we'll have a good discussion.

<!-- image -->

**Hassan Rauf** 1:09:34
Sure.

<!-- image -->

**Don Nguyen** 1:09:35
So, so James, the anything that involve GARP is a known issue, right? They you have quirky stuff.
So that's why you have to maintain the IP all the way through until the last last step.

<!-- image -->

**Erickson, James** 1:09:48
Yeah, um.
If not the the garp, the whole platform in general. Like I said, the garps are just hosted on the AXC. Yeah, there's also an AXD.

<!-- image -->

**Don Nguyen** 1:09:58
Oh, OK. OK.
Yeah, on top of the AXC, yeah.

<!-- image -->

**Erickson, James** 1:10:08
Chassis that's also used. That's an Erickson product. Um.

<!-- image -->

**Don Nguyen** 1:10:11
So, so this is a known problem, Chao, right? You guys ran into it in the past?

<!-- image -->

**Erickson, James** 1:10:18
Yeah, well, it's it's not that we ran into a problem. It was given to us as a prerequisite from Erickson and and their operations team from the start.

<!-- image -->

**Don Nguyen** 1:10:32
Oh, OK. OK. OK.

<!-- image -->

**Erickson, James** 1:10:32
Is when when we went to go certify it, we had to prove to them, see, look all of our sessions as we migrate are still available and up. We don't lose any.
Connectivity, you know, yes, there we do expect brief, very, very brief sub second, you know.

<!-- image -->

**Don Nguyen** 1:11:00
Right.

<!-- image -->

**Erickson, James** 1:11:00
Reconvergence for like VRRP or something like that and that's acceptable, but having it down too long or keeping a a Wan interface down when you know.
That's that's problematic too, and it mainly comes from the TDM side, right? The TDM circuits that are established on the.
With the customer.

<!-- image -->

**Don Nguyen** 1:11:34
Yeah.

<!-- image -->

**Erickson, James** 1:11:36
Um, those?
Have their own keep alive systems, their own OAM monitoring and if if you know those TDM systems see something go down, they'll just.
Switch over to another. You know, if it's another carrier, it's another carrier. We we just don't. We just don't need.

<!-- image -->

**Don Nguyen** 1:12:01
Got you. OK, OK. They, yeah, they designed to fail over on the on a different on a different signal that they not aware that we are switching the swapping this system out.

<!-- image -->

**Erickson, James** 1:12:11
Yeah, yeah, 'cause they're not, you know, um.
Yeah, they're they're a little bit more sensitive to IP address changes. Let's put it that way.

<!-- image -->

**Don Nguyen** 1:12:25
Yeah.

<!-- image -->

**Erickson, James** 1:12:27
Um.
So yeah, any other questions?

<!-- image -->

**Don Nguyen** 1:12:33
Yeah.
Hassan and Mohan, you guys already knew this stuff. That's good. I'm just asking a question to get James to to refresh his memory, upgrade his NVRAM.

<!-- image -->

**Erickson, James** 1:12:40
Yeah.
Yeah, well, let me go ahead and close off this recording here again if there.
Stop sharing.

<!-- image -->

**Erickson, James** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-19T13:41:23.998555+00:00",
      "canonicalTerm": "MOP",
      "reviewCardId": 21,
      "term": "mob"
    },
    {
      "appliedAt": "2026-06-19T13:41:24.033905+00:00",
      "canonicalTerm": "MOP",
      "reviewCardId": 22,
      "term": "mops"
    },
    {
      "appliedAt": "2026-06-19T13:41:24.079619+00:00",
      "canonicalTerm": "I spec",
      "reviewCardId": 23,
      "term": "ice back"
    },
    {
      "appliedAt": "2026-06-19T13:41:24.107642+00:00",
      "canonicalTerm": "I spec",
      "reviewCardId": 24,
      "term": "isec"
    },
    {
      "appliedAt": "2026-06-19T13:41:24.132603+00:00",
      "canonicalTerm": "VRRP",
      "reviewCardId": 25,
      "term": "VRP"
    },
    {
      "appliedAt": "2026-06-19T13:41:24.157675+00:00",
      "canonicalTerm": "Ericsson Engine",
      "reviewCardId": 26,
      "term": "Erickson engine"
    }
  ]
}
-->
