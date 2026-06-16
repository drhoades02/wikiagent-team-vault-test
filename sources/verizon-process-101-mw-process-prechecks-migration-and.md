---
created: 2026-06-16T05:22:35.871940+00:00
updated: 2026-06-16T05:29:53.694588+00:00
concepts:
- BGP sessions
- converted config
- go/no-go call
- health checks
- maintenance window
- MOP
- MW process
- PIP customers
- post checks
- pre-checks
- RSI
- SPIP site
- Verizon Process 101
- VRRP
entities:
- JTAC
- Junos logs
- KIRKE
- S2I
indexes:
- '[[Team Index]]'
- '[[Verizon Migration Maintenance Windows]]'
description: Transcript of a Verizon Process 101 session on maintenance-window pre-checks, migration execution, KIRK handling, post-checks, and closure tasks.
source: /Users/drhoades/VaultRaw/Verizon Process 101_ MW process- prechecks, migration and post checks Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-16T05:22:35.871940+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 2093,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ MW process- prechecks, migration and post checks Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-mw-process-prechecks-migration-and-1781587355886053000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-16T05:22:35.871940+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ MW process- prechecks, migration and post checks Transcript.docx",
  "sourceSha256": "2b41518816d0b0569bfe9a921ddc85c5c63da6da3d23ad60ca95cdef9141d116"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Transcript of a 56-minute Verizon Process 101 training session covering maintenance-window preparation, KIRK/change handling, pre-check baselines, migration-window monitoring, rollback/time decisions, post-checks, and closure tasks.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 MW process- prechecks, migration and post checks-20251217\_120533-Meeting Recording**

December 17, 2025, 7:04PM

56m 41s

<!-- image -->

**Erickson, James** started transcription

<!-- image -->

**Erickson, James** 0:09
Share out my screen.
Screen.
Alright.
So this.
This session is we're gonna cover.
Um.
Kirk tasks. Uh.
The actual events during the maintenance window and post checks.
The uh.
Let me.
Is anyone on here not sat in on a maintenance window before?
Or was or still gets extremely lost when we.
When they join a maintenance window call.

<!-- image -->

**Czirjak, Gery** 1:16
I get very lost.

<!-- image -->

**Hassan Rauf** 1:19
I think I mean I we, I don't know if we're gonna manage in the Kirk individually going forward or I I've never dealt with Kirk portal yet to start or stop or those kind of things.

<!-- image -->

**Erickson, James** 1:19
Well.
Yeah, there's. I mean, unless you're nice like Gary, you you won't be creating Kirks the it's easier to be managed, at least for the migration windows.

<!-- image -->

**Hassan Rauf** 1:35
Changes.

<!-- image -->

**Erickson, James** 1:54
It's easier to have a single person manage all those since they change so frequently. Um.
I mean maybe Risha can use use the help and we get someone else to do that. But for now I can only imagine it's it's just it would it can turn into a real big.
Um.
Uh.
Messwan.
You know, Kirk's get it.
Fail to get scheduled or or don't get approved or you know um when you if you introduce.

<!-- image -->

**Czirjak, Gery** 2:39
So I wouldn't do the migration ones either, James, and Meratia has pretty much dumped those on TJ now as far as I know, so.

<!-- image -->

**Erickson, James** 2:48
Yeah, yeah.

<!-- image -->

**Czirjak, Gery** 2:49
They're too complicated.

<!-- image -->

**Erickson, James** 2:51
Exactly so.

<!-- image -->

**Kanumuru, Mohan** 2:54
But someone, someone will monitor them, they're approved or not. So it's not the technical team or the people who attend the migration window don't have to be checking to see if they're they're ready to go.

<!-- image -->

**Erickson, James** 3:11
Well, usually, um.

<!-- image -->

**Kanumuru, Mohan** 3:12
Approved to go.

<!-- image -->

**Erickson, James** 3:29
Um.
Usually um the the go no go call.
Raisha has already checked those. You know the go, no go call is about 12 hours before we start the the thing. Maybe a little later, you know it doesn't matter some sometime the the daylight hours before we start.
We we usually have that go no go call or a couple of days in advance where we should be able to validate you know that they are approved. I actually haven't and you don't start a maintenance window unless the Kirk's approved.
Let's just put it that way, right? The so.
It is good. I mean to know about that kind of that state before we bring everybody up onto a zoom call and but you know.
We'll have that. That's the effort we're we we try to make for that. I haven't actually run into needing to cancel a a zoom, a migration window for a night.
Because of a Kirk issue, it's rare. Rish has been doing a really great job with that. I think I've only had to do it once in, you know, several years, so.
As far as pre-checks are concerned, the goal is to apply and review the converted config about, you know, a a week in advance of of the actual migration.
Migration window. Um.
The.
The health check of the existing node is.
Good to you know about a week out you need to know you know is this stuff in any kind of condition to be migrated. We ran into that with one of the DPC sites where we didn't.
Realized there was a pre-existing condition, you know, um.
The uh.
You know the part of that is you can't test that the node is fully redundant, right? You can't just take the existing production node and cut off one side or flip everything over to its backup.
Path a week in advance to know that that piece is working right. Um.
But we do the best we can with our health checks. Um.
And but then we should, you know, at least know.
Interfaces that shouldn't be down or BGP sessions that shouldn't be down. Which way VRRP is facing right?
You can also use S2I for this. Um.
Just check the alarms just just to supplement your what you know about the current health of the devices there and our application support team has started doing this where they take the daylight hours and.
And do a baseline and just assume, you know, oh, you know that it's gonna stay the same for the next 12 hours or or do it, you know?
Uh.
In advance of the maintenance window of that night. Um.
We do have an hour.
Baked into our zoom meeting invites where the first hour of the maintenance window is used for this task for to capture a baseline operation.
And you know, do then.
Do any other health checks. It's also baked into our MOPs to do that. The first sections two and three are of of the mops are usually.
Done as long as done in advance of actually opening up the the Kirk. Um.
The uh.
At the start of the maintenance window. Um.
This is what I was talking about. It's captured all the health, the start of the maintenance window that first hour before you open the Kirks.
You'll you'll be still just gathering health checks, making sure and this takes you to your head into a lot of different places. Do we have our main our application support team on the call? Do we have is the call ready?
You know, we have everything we need and that can usually take up that whole hour. So any of the tedious stuff that you can get ready for, you know, maybe get it out of the way earlier in the day.
Um.
The uh.
The baseline of these servers are just as important as the baseline of our devices. We need to make sure that they are all working and if they call out a flag, you know a certain device that you know or a certain condition on their.
On the servers, we need to listen and, you know, deal with that appropriately. Um.
One exception is sometimes these PIP customers are not provisioned correctly, um, or just plain not working for whatever reason, unless there's.
Every PIP or SPIP site has probably at least 100 customers provisioned in there and trying to error correct for all 100 of those before we even start a migration.
Is, you know, not not in our scope. So we can't error correct, you know, minimum is 100.
um 100 customers provisioned on each router, but you know you could have upwards of 200 or 300 on a super super node, a spip site. Um.
The so unless the like the last site we did, unless the HSJBR we actually we saw a large block of customers on a specific LAN interface, you know just none of them working kind of re re re reported that back.
To Verizon, they didn't.
Call that a a showstopper and we moved forward. We did not correct them. We just knew what to expect. We need to know how many.
PIP customers might be failing so that when we see a bunch of failed PIP customers after our one for one migration, you know we should see the exact same number that still don't.
Have BGP sessions or don't have connectivity?

<!-- image -->

**Kanumuru, Mohan** 12:15
This gets discovered or identified during the prechecks just before the maintenance window.

<!-- image -->

**Erickson, James** 12:22
No, it's no. Usually we discover them way in advance.

<!-- image -->

**Kanumuru, Mohan** 12:26
How can we find out this information?

<!-- image -->

**Erickson, James** 12:31
Well, for the SPIP stuff, the like I said, somebody's done a converted config on this and if they've done a converted config.
They have obvious they should have had more than enough time to check that these are which ones are down, but you know we can start doing our health check of the existing node.
Up out to a week out. That's when our Um.
Our freeze goes into place. We know after a certain, you know, T -, 7 days that we know that they aren't making any automated changes to it. Their operations team is pretty much hands off.
It's ours and you know, but the sooner we can know of any large.
Number of PIP customers that are not provisioned correctly, the the the better. And when I say a large #30 is a large #10 is not you know out of 100 or so, right?
Um.
There's a threshold there you can.
Probably just feel it out. And if you have any doubts, definitely bring it to us in this team internally and we'll make the call if we bring it to Verizon. It's, you know, they're they're used to hearing.
You know these kind of status notifications from us before saying yes, SPIP or PIP customers are down. You know they would be alarmed at 30, they'd be alarmed at 40, 50 as well, but not. I don't think they'd be alarmed at.
You know a few here or there.

<!-- image -->

**Kanumuru, Mohan** 14:40
So, so, so, so, so we get to know these from the BGP sessions, BGP sessions that are down, you know from the config or information on the routers.

<!-- image -->

**Erickson, James** 14:49
That's the.
That's the easiest way is from those BGP sessions that are down because you won't see any issue with the physical links on the SBC if they're.
Not configured correctly. You might at most see a VRRP that's master on both sides if they have a a VLAN mismatch or.
And those are really everything else is just trunked interfaces. And if the interface is up, the interface is good, you know you you can't only take.
Those the BGP session and VRRP are pretty much the only two real good indicators that something is.
Misconfigured, and it's probably not necessarily misconfigured on our end, but on some cases it might be misconfigured on the remote end.
That PE pip PE router might be at fault and again by this stage 7 seven days out from a a maintenance window if we catch it or when we catch it.
Um.
You know, we probably won't expect anything, any correction, corrective activity from Um.
From operations, if it's something else, if it's something other than PIP customers that aren't provisioned correctly, say one of our uplinks to.
The VIV, one of those BGP sessions are down, or the whole interface is down, or the configuration isn't as we'd expect it.
Those things do need to be resolved. Catching that seven days out ahead of our maintenance window will help immensely. I mean, ideally we would have cut it.
Earlier, but you know, this is probably our last chance to um.
To catch it within a safety margin where we're not. Um.
Really causing more irritation for the client, catching it too late a week in advance. If we just say we need to, this is a problem we need to.
And to reschedule, you know.
With this margin of seven days or.
We're probably good at engaging them to be able to fix the issue before we we.
Go to migrate.
Does that answer your question, Mohan?

<!-- image -->

**Kanumuru, Mohan** 18:02
Yes, yes, yes. Thank you.

<!-- image -->

**Erickson, James** 18:05
Mhm.
Um.
So like I said, our our application support team is also doing health checks on theirs. Again, verify with these support teams that all applications are working as expected.
And then also set up your your SSH terminal session to log the CLI output for all the devices you touch. We want to have a record of everything, not necessarily a a a.
A record that we, you know, um.
It.
Yeah, this is the cover our *** kind of record, right? Sorry for the language, but this is the where we.
Can.
Refer that to that.
Ourselves or or give it, you know, deliver it to Verizon as needed just just to validate you know what went on if they have any questions about what.
Or or if there needs to be an RCA or further troubleshooting, something really goes haywire, there's an outage, whatever.
Having this is mandatory. You're gonna want to save everything you do on.
Your SSH session.
Um.
Once we start the Kirk, right, this is we've we're on the Zoom call. It's been an hour. We have everybody on the call.
On the call.
Um. And let me show you also um.

<!-- image -->

**Kanumuru, Mohan** 20:22
I think on that on that Kirk thing, I think you you you did it once in the e-mail. Sometimes it looks like because there are multiple Kirks and in the e-mail we might only see one Kirk. I mean it's a e-mail application issue it looks like.
But we have to open all the Kirks.
And how to make sure that?
E-mail.

<!-- image -->

**Erickson, James** 20:48
Yeah.
Let me go back to one of these Kirk.
Windows and show you what?
We're talking about here. Show everybody what we're talking about here.
Um.
So the Kirk numbers are all.
You know this is our DNGBR invitation, right? You should see two images here. There's one.
Two and.
You know.
Usually what I do is just.
But the.
Put the things into.
Um.
Put the things into paint.
And then zoom in, yeah.
If at all better they could to one recommendation you know if as Resha or TJ or Mike are listening to this recording is to put these in a text format.
Um for us into a separate table. Um.
The the idea here is that we do need to open each and every one of these.
Um.
Well.
And the numbers change each night, right? Because they're not all.
Um.
And request ID. There we go.
So here there's.
12345 unique Kirk numbers.
Right. So when we go to open these in Kirk here for this search filter, you need to put all five of these numbers separated by a comma.
And then you can search for all those now.
Gary, isn't there a way to search by the plan ID too or?

<!-- image -->

**Czirjak, Gery** 23:49
Yeah, that works too. It's just more annoying.

<!-- image -->

**Erickson, James** 23:53
It.
The plan ID. Searching for the plan ID is more annoying if there's only three of those.

<!-- image -->

**Czirjak, Gery** 23:58
Yeah, you can use the plan ID, but then you got to still go and open all the request IDs anyway, so it's really I've made that mistake. So I I never look at that anymore cause it's too painful.

<!-- image -->

**Erickson, James** 24:06
Mhm.
Yeah.
Um.
Oh.

<!-- image -->

**Czirjak, Gery** 24:16
But it will find it.

<!-- image -->

**Erickson, James** 24:20
Yeah.
Yeah, um, so.
So like I was saying, these, you know, five unique different.
Request IDs.
Um.
And I think we've shown this before on maybe another maintenance or another one of these one-on-one calls, but.
For example, if we.
If I really want to show you how this is all.
Done. I mean what I.
2, 9, 3, 4, oh, one.
Now you can copy these.
Paste them in here.
View results.
Yeah, and occasionally you might get one of these numbers wrong. Just make sure they're all set for the same day, have similar description, you know, they're all approved, and then you go one at a time.
Um, now you'll notice this.
Dynamic bar up here will show you how many different.
Kirks you have open, you know and and tasks you you have the website doing and you can easily flip between each of these as you go opening them or.
You know, one thing I like to do is open them at the start of the Zoom meeting. Just get to this point.
Um, just so I know that status approved or pending, or you know, whatever. Um, make sure it's a valid Kirk, and then.
You know, start it.
Um, then move, you know, and and our.
Midnight local time. Just pull it U start it, move on to the next one. Ull it U.
Start it O.
Uh, Kirk. Um.
Let's see what else we got going on. Where is my notes? Um.
So yeah, you know everyone that's the in the same e-mail. Let me go ahead and pull it up.
Um.
There should also be um.
Or in the no go, go, no go call e-mail. Let me pull one of those up to see show you what that um.
Um.
Here is the.
E-mail.
Reason uh.
Response Risha puts out after go no go call. Excuse me after go no go call. Um.
Wanna kill this search? Oh well.
For one thing, it does put in here who's responsible for what, right? Um.
And you know our local site technician, their phone number. Um.
The uh.
Uh, what else do we have here?
Um.
Who's on call or who's gonna be responsible for for which support?
Worked.
Who did the health checks? For example, James Rader did health checks on the equipment previously. Teresa for the BRIX. Paul did the GeoProbe pre-check.
Um. Usually that's done behind the scenes, like I said in the in the week before. Um.
But uh, and here's a list of the public PIP PE Kirk requests.
Uh.
Yeah, any questions? If you haven't looked through this, this you know you might need to come back to it during the maintenance window just just for this information alone if they don't.
If just so you know who it is, it's gonna be joining.
Um.
Other people like Abid or Shavon or whoever, they're gonna be available on Slack. But since we don't have Slack access to these texts, e-mail and phone number right there.
And.
Our other support? Um.
Application support team are listed there.
Any other questions? Like I said, you'll get this. This is.
Part of the go no go call. You should get this before the maintenance window starts and some sometime after our go no go call and everything's been resolved that we're a green light.
The uh.
So then you check your attendance, make sure everybody's on the call that you need it. Um, you you monitor your S2I.
Um.
Is everybody at least able to monitor in S2I? I know we haven't worked out group permissions to.
Say update a filter or anything.
Update or update the non page filter, but um.
If uh.
Um.
For example.
These.
this filter. I know you guys aren't going to be able to edit that appropriately, but at the very least um being able to monitor
Um.
Our our smarts.
Should be something you're all capable of. Is there anyone that hasn't been able to?
Pull to monitor uh a site or is that?
Been resolved for everybody.

<!-- image -->

**Kanumuru, Mohan** 34:18
I think monitoring part.

<!-- image -->

**Erickson, James** 34:23
I know you you've you've been able to do it in the past, right, Mohan?

<!-- image -->

**Kanumuru, Mohan** 34:23
Oh.
Right, I I think, yeah, even I I'm thinking that even the Hassan able to and Don also able to basically manually enter this domain, I mean the DNS names to to flag them.

<!-- image -->

**Erickson, James** 34:41
Mhm.

<!-- image -->

**Kanumuru, Mohan** 34:44
The instead of going to your account and fetch copying it.

<!-- image -->

**Erickson, James** 34:44
OK.

<!-- image -->

**Kanumuru, Mohan** 34:50
On the on the left side, yeah, I think.

<!-- image -->

**Erickson, James** 34:51
Yeah.
And Gary, I don't think I'm even gonna ask you. I I don't think.
When you're monitoring these, I usually sort them by event time. I'll ask you if you are able to monitor.

<!-- image -->

35:05
What?

<!-- image -->

**Erickson, James** 35:13
Um in S2I.

<!-- image -->

**Czirjak, Gery** 35:17
Oh yeah, yeah, of course. That doesn't mean I actually do it, but yes.

<!-- image -->

**Erickson, James** 35:26
Saying the quiet part out loud. Yeah.

<!-- image -->

**Czirjak, Gery** 35:27
Oops, that wasn't recorded though.

<!-- image -->

**Erickson, James** 35:30
It was.
Um.

<!-- image -->

**Czirjak, Gery** 35:35
One of the things I do and I don't know if you do is I get I readjust all these columns and and move things around cause I can't stand the way it defaults out.

<!-- image -->

**Erickson, James** 35:44
There is a way to save that into your profile.

<!-- image -->

**Czirjak, Gery** 35:49
Yeah, never done it, but yeah.

<!-- image -->

**Erickson, James** 35:52
Yeah.
Um.
So it looks like there was an actual interface that went down recently in RTOSN one.
Um.
Which one are these?
Oh, the virtual server interfaces.
Utility server interfaces. These are expected.

<!-- image -->

**Kanumuru, Mohan** 36:23
Hello.
They all went down as we speak now.

<!-- image -->

**Erickson, James** 36:28
Well, these interface down probably won't clear until they are actually up again.
So, but given that these are virtual server devices.

<!-- image -->

**Kanumuru, Mohan** 36:45
But that's it looks like in data happened in 08/13, so it's something way back, OK.

<!-- image -->

**Erickson, James** 36:46
Um.
Yeah.

<!-- image -->

**Kanumuru, Mohan** 36:56
It's not in December.

<!-- image -->

**Erickson, James** 37:02
Yeah, well, so this these top two are in.
Um, December looks like they might have had some server side issues, but these are fully redundant anyway. I think they might be single threaded. Um.

<!-- image -->

**Kanumuru, Mohan** 37:15
Right.
One thing that's clearing them is not what I this S2I. Will it show if it got cleared? Will that go away the old record? I don't think it happening.
Unstable down cause.
How we know unless we log into the router and see if those interfaces are actually not an issue now?
So and also on the left side the icons.
There is a way to see if somebody acknowledged them, right?

<!-- image -->

**Erickson, James** 38:00
Yeah, over here is the acknowledgment column far left. It it just turns yellow.

<!-- image -->

**Kanumuru, Mohan** 38:04
How we know if it's acknowledged?
OK, so these are not even acknowledged.

<!-- image -->

**Erickson, James** 38:11
No. So these aren't even acknowledged. How long ago did we do our TOS N1?
Um.
It's probably been some.

<!-- image -->

**Kanumuru, Mohan** 38:23
Yeah, three weeks.

<!-- image -->

**Erickson, James** 38:26
Three weeks.

<!-- image -->

**Kanumuru, Mohan** 38:28
I think in the in the I think Hassan and might be able to clarify. I think Nick and Hassan might have done that, right?

<!-- image -->

**Hassan Rauf** 38:40
Which site?

<!-- image -->

**Erickson, James** 38:42
RTOSN 1.

<!-- image -->

**Hassan Rauf** 38:49
I see.

<!-- image -->

**Erickson, James** 38:52
TOSN 1 MRO 2.

<!-- image -->

**Hassan Rauf** 38:59
I'm gonna have to check that.

<!-- image -->

**Erickson, James** 39:22
Looks like most of it was done at the end of August, yeah.

<!-- image -->

**Kanumuru, Mohan** 39:28
August. Oh, so then I thought that they OK, so I'm completely hallucinating.

<!-- image -->

**Erickson, James** 39:31
Yeah, and that would.
Yeah.
Yeah, so all these alarms from the 13th of August.
Um.
I guess their configs rolled off, but um.
Admin.
Yeah, uh, or we can go to.
TVS backup.
Um.
M.
MX960.
So these started 7/24.
812820
So these were all the commits historically.
Um.
On this router.
Did you guys see how I logged into that? So the NTVS that we are using is a jump box. We're using a a Juniper PS username, but logging in with the backup username gives you access to.
Um, all the backup archived configs?
Um.
And you should see in the backup MX960 folder.
Our directory we have.
All of our sites here. Um.
Alum 9 for.
Poba.
Rialto included. Those are three Erickson engine sites.
Um.
Everything else should already be in there. All right, let's move on. Um.
Oh yeah, I was gonna check.
Yeah, A33 is up now.
737.
So yeah, I mean, I guess these two get out of sync. They don't clear automatically. Um.
Or because it's saying it's unstable, it's not a down up, you know? How often does the has this been flapping? Um.
737.
Sorry, last flap here. Um.

<!-- image -->

**Kanumuru, Mohan** 44:01
Yeah, last flap it says 20251217. Yeah, today it flapped.

<!-- image -->

**Erickson, James** 44:05
It did flap today.

<!-- image -->

**Kanumuru, Mohan** 44:07
Yeah, just a light in the middle, just two lines above three. Yeah, just I think you are right there.
In the beginning itself, go ahead, go ahead in the beginning.

<!-- image -->

**Erickson, James** 44:22
Oh, oh, I thought I was looking at the beginning. Uh.

<!-- image -->

**Kanumuru, Mohan** 44:25
Yeah, yeah, right there. Right in the center, above the counters. Go above the counter. Let's see that right there where your mouse is.

<!-- image -->

**Erickson, James** 44:35
Yeah, that's flapped.
So it did flap on the 17th.

<!-- image -->

**Kanumuru, Mohan** 44:42
So we need to. Is it optical or a copper? Is it a?

<!-- image -->

**Erickson, James** 44:43
Um.
This is an optical.
Oh, um, no, it's copper. It's on card seven. Sorry, I misspoke. Seven thirty-seven is a copper interface. Um, so

<!-- image -->

**Kanumuru, Mohan** 45:31
So there are no errors. Interestingly, dropped frame errors run.

<!-- image -->

**Erickson, James** 45:39
Yeah, no, I think this is more of a failure on the F.

<!-- image -->

**Kanumuru, Mohan** 45:44
The carrier transition number is high.

<!-- image -->

**Erickson, James** 45:49
Yeah, this is this is part of the NSRS F5 device, right?
The E oh, I'm sorry, ESX. Um.
So they have a virtual machine that kind of runs it. Um.
or or this interface runs inside this on a virtual machine for um.
For the device and.
Yeah, yeah. Actually, now that I think about it, August, RTOSN one is one that I did and it did have a lot of cabling issues. This might be one that just snuck up on us after, you know, looked good at first, but.
Um, you know, and this kind of thing will happen, but that one of those is.
Again. Um.
At this point it it's been returned back to the custody of the operation, the Verizon operations team for them. You know, if they had seen any of these.
Um, they should be able to handle it as a new issue. Yeah, it might still come back to us as being something, you know, incidental from the migration, you know, but if they had.
Seen any kind of outage?

<!-- image -->

**Kanumuru, Mohan** 47:36
But it looks like this one happened in the sometime in the December. I think if you look at the those two, it came early December, so it may be happening from December onwards, may not be there in October or November.

<!-- image -->

**Erickson, James** 47:48
Yeah, exactly.
So there's no telling we we but and we don't know if since since the migration they've made.
Changes to the NSRS server that ESX device if it's not, if it's you know.
Um.
This is interesting.
Traps came in, got parsed and left.
OK.
Let's go back to this here. And so yeah, monitor the S2I alarms, reading them, clearing them as as we were noticing here, right, we don't.
Some you won't clear. You give it a best effort, you know, you try to clear it at once, but everything should be able to be like acknowledged. I don't necessarily want to acknowledge this since it's not directly related to us. We're not.
In a Kirk.
So I don't want to take responsibility for it, but, you know, just right clicking, or you can, you know, select multiples.
Acknowledge and then clear if you want to try to clear it.
And I'm getting a 5 minute window warning. All right. Um.
Also want to monitor Junos logs as necessary and I'm going to put in here um.
The uh.
Archive uh var logs.
And take RSI.
Before and after.
Uh.
Maintenance window or or migration as after migration.
The migration task as a whole at the very first day or anytime you see start seeing these logs start rolling over.
Going over.
You're gonna want to make sure you take an archive. Um, save it somewhere. Um, covered starting the Kirk.
And yeah, there are a lot of discrepancies or updates that might need be need need to be made to either of these. If if there's a cut sheet reference that needs to be updated, you need to go back to Verizon and send them the lines.
The red line what needs to be redlined or adjusted so they can have a an as accurate as possible I spec. MOP is mainly for us.
Maybe there was a typo in the uh um.
In a command prompt, right? Or a command? A configuration command.
Managing time and rollback decisions is key part of migrating tasks. Greg usually doesn't want us to get too ambitious ahead of.
You know.
At 3 hours into the Kirk, we should be making a decision as to.
You know, holistically, are we going to need to rollback considering everything that's going on, our access to tools or our?
Uh, are we going to be able to finish certain work tonight? Uh, you know, doing?
Um. Or do we need to save it for another night? Do we need a backup window, right? Um.
And yeah, there's no.
Um, shame in at all in delaying something, saying we just don't have time for it this night. Let's let's do our final checks just so that we have a clear end time so that we make sure that we are not.
Going over our.
Maintenance window hours.
Because that they will come down on us for they won't come down on us for using a backup window, but they will if we.
Don't.
Manage our time right and go over our window. J tech every maintenance as showing you this.
No wrong.
Where are my other in?
My other emails I had up.
Um in the go, no go uh.
There should be a JTAC proactive JTAC case opened. We open it the the day of. Once there is a a go decision for the maintenance window, one of us will create the proactive case number.
It's just a matter of if we need JTAC on the call, we need to call in, provide them that night's Zoom. Um
Uh.
Zoom link and any other support we're missing is should be available on Slack post checks, final tests, tasks and checks and MOP final checks and you've seen that section at the end of the MOP if there's anything that.
You know, quick updates, process things, things. We want to make sure we, you know, mistakes we've made that we want to make sure we don't make again. Those fall at the end of the MOP. We can double check those.
The we get our final checks from our application support teams. They say everything's looking fine. We capture our new status for the new equipment.
And then?
Check S2I. If everything's looking good, we can close the Kirk, write our results e-mail and do our daytime. If anything happens, do our daytime support handoff.
All right. I think we've got another call coming up here. So um.
Go ahead and end this here.

<!-- image -->

**Don Nguyen** 55:43
Thank you, James.

<!-- image -->

**Erickson, James** 55:44
No problem.

<!-- image -->

**Hassan Rauf** 55:45
Thank you, James. Oh, which other call? I don't think we. I have another call. Just want to see who's missing. Yeah, I just want.

<!-- image -->

**Erickson, James** 55:51
Oh, was there one?
No, there's a project sync.
Or or my is is that only my calendar?

<!-- image -->

**Don Nguyen** 55:57
Yeah.

<!-- image -->

**Hassan Rauf** 55:58
Oh.
But I think it probably got cancelled.
That's why.

<!-- image -->

**Don Nguyen** 56:05
They all canceled for me, so.

<!-- image -->

**Hassan Rauf** 56:08
Yeah, probably. I I don't see any. Maybe it's just you.

<!-- image -->

**Erickson, James** 56:15
Oh well, before I.
OK. No, it's still on my calendar. Um, yeah. All right.

<!-- image -->

**Don Nguyen** 56:31
Yep.

<!-- image -->

**Kanumuru, Mohan** 56:33
So I'm dropping.

<!-- image -->

**Hassan Rauf** 56:33
Alright.
Thank you guys.

<!-- image -->

**Erickson, James** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-16T05:32:03.885117+00:00",
      "canonicalTerm": "KIRKE",
      "reviewCardId": 31,
      "term": "Kirk"
    },
    {
      "appliedAt": "2026-06-16T05:32:11.596078+00:00",
      "canonicalTerm": "KIRKE",
      "reviewCardId": 32,
      "term": "Kirks"
    },
    {
      "appliedAt": "2026-06-16T05:32:16.890356+00:00",
      "canonicalTerm": "go/no-go call",
      "reviewCardId": 33,
      "term": "go no go call"
    },
    {
      "appliedAt": "2026-06-16T05:32:23.598628+00:00",
      "canonicalTerm": "JTAC",
      "reviewCardId": 34,
      "term": "J tech"
    },
    {
      "appliedAt": "2026-06-16T05:32:27.381894+00:00",
      "canonicalTerm": "MOP",
      "reviewCardId": 35,
      "term": "mops"
    },
    {
      "appliedAt": "2026-06-16T05:32:41.353448+00:00",
      "canonicalTerm": "go/no-go call",
      "reviewCardId": 41,
      "term": "no go, go, no go call"
    },
    {
      "appliedAt": "2026-06-16T05:32:53.771884+00:00",
      "canonicalTerm": "JTAC",
      "reviewCardId": 42,
      "term": "J tech proactive J tech case"
    }
  ]
}
-->
