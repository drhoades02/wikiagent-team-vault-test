---
created: 2026-06-17T00:28:12.205804+00:00
updated: 2026-06-17T00:44:50.789209+00:00
concepts:
- I-spec
- Layer 1 validation MOP
- Verizon Process 101 Layer1IT Assurance
entities:
- Cisco ISE / ICE
- ISNTS IP com not paged
- Jason Abercrombie
- Juniper PS user ID
- Kirk
- Rob Lebu / Rob Lebuth / Rob Lapu
- S2I
- Tacx
facets:
- Mohan automation
indexes:
- '[[Network Migration Processes]]'
- '[[Team Index]]'
description: Transcript of a December 5, 2025 team walkthrough of the Verizon Layer 1 IT Assurance process for pre-migration validation.
source: /Users/drhoades/VaultRaw/Verizon Process 101_ Layer1_IT Assurance (Gery) Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-17T00:28:12.205804+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 2682,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Layer1_IT Assurance (Gery) Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-layer1-it-assurance-gery-transcript-1781656092299017000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-17T00:28:12.205804+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Layer1_IT Assurance (Gery) Transcript.docx",
  "sourceSha256": "3b14ae67caf2ebd3d59d7f22562f8daac2e027ffb51d1b080ede2ebbcf66cfb8"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Meeting transcript documenting the Verizon Layer 1 IT Assurance / validation process after Verizon engineering handoff, including I-spec download, KIRK/maintenance coordination, base router configuration, SSH/DNS/TACACS/ISE setup, S2I alarm filtering, software/firmware checks, chassis hardware XML collection for JTAC support, and physical crosslink verification.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 Layer1IT Assurance (Gery)-20251205\_090525-Meeting Recording**

December 5, 2025, 4:05PM

1h 8m 37s

<!-- image -->

**Czirjak, Gery** 0:03
It won't be very long. Thank you, James.

<!-- image -->

**Erickson, James** 0:06
Mhm.

<!-- image -->

**Czirjak, Gery** 0:06
All right, let me find the share button, share screen, go back over here.
All right, gentlemen. So I just gonna go over the the layer one task that we do when we get a handoff from Verizon that we're supposed to go ahead and do some verification of the sites in preparation for our migration.
But basically I I threw together this little presentation just to guide us through it. I'll put that up online somewhere. Rachel will probably figure out where to put it and if you guys want to reference it or not. Note that this was written from the perspective of doing it all manually.
By hand and Mohan is going to fix all that and automate 99% of this. So the manual part will probably change dramatically here.
Thank you Mohan for that, because I would have never been able to do it.

<!-- image -->

**Kanumuru, Mohan** 1:03
Yeah, I will. Yeah. Yeah, it's, it's, yeah, it's a team effort. Thank you for your encouragement there.

<!-- image -->

**Czirjak, Gery** 1:11
Anyways, so basically, so this is triggered. We get a notification from Verizon engineering saying that it's ready to go. It usually comes from a guy named Rob Lebu.
The condition of the routers varies. Typically there are up and working and connected to the consoles and the Ethernet, but sometimes their code is upgraded, sometimes they're not. Sometimes they got a bit of a config in them, sometimes they don't.
But regardless, we do get this note from Rob Lebuth and Rachel will probably give us a poke and say get to work, right? Get this done so.

<!-- image -->

**Kanumuru, Mohan** 1:49
Is that notification happens through an e-mail? OK.

<!-- image -->

**Czirjak, Gery** 1:52
Yes, it does. Yeah. Yeah. And then, like I say, I don't recall if it's sent to us all or whether it's sent to Resha and then she sends it to us, but.

<!-- image -->

**Reddy, Resha** 2:01
It's, yeah, it's kind of hit or miss. So I think normally he'll send it to James and Gary, but he's not sure who handles it because, you know, we do change things. So he'll send it to at least one of the guys and then he'll send it to myself and and Mike. And that's why I usually poke because then I add everyone else.
in that needs to be aware.

<!-- image -->

**Czirjak, Gery** 2:24
Right, right. So like everything else, we do what we're told guys. So anyways, so just you're aware there is a MOP that was written. It was written by Nick Okerberg. Now let me see if I can show you where it is. It's.
Hanging around here in our router switch links under the operational and IT MOPs and at the very bottom you'll see something called Layer 1 validation MOP. OK, so it is available for you to reference if you like. To be honest, the first time I looked at it.
Well, it was a long time ago and the second time I looked at it was yesterday, so.

<!-- image -->

**Kanumuru, Mohan** 3:01
Oh, you you memorize the MOP.

<!-- image -->

**Czirjak, Gery** 3:02
Anyways, so that's not no, I just don't care what it says.

<!-- image -->

**Kanumuru, Mohan** 3:06
I yeah.

<!-- image -->

**Czirjak, Gery** 3:09
Well, this is a fairly simple task, so you know, really it's pretty straightforward. So the first step usually involves better download the I specs so you have some idea of what you're doing, what you need to do, how to connect to the devices, you know the usual routine.
There's the the D1 and D2 tabs in there that tell you how to connect to the devices and give you the the IP address information that you need to configure the Ethernet ports. So pull it down and pull down that I spec.
There is a CRQ required for when we do the verification of the physical interfaces between the new devices and the legacy devices. It is generally auto approved because it's a non service impacting CRQ.
Some of us like to open these or TJI guess. I always kind of felt bad because I thought, you know, it's really not that hard to do and they've all got enough to do. So I started doing them myself for these. If you ever need to do it and you're interested in opening a CRQ yourself for it, just let me know and I'll I'll walk you through.
But it's not very hard. It's just a boring point click thing.
And basically what you want to do is you want to create a base configuration, right? And all these details are in the I spec that you need in order to get this started and that the primary things you're worried about there are you need to know the host name, obviously, right?
Those go in the group configs along with the IP addresses and the for the management interfaces. We also need to define a backup router configuration and the default route to it, but that's the primary things we have to do in this area.
And if you have any questions, just bark at me so.
So essentially once once you're ready to go, you want to log into devices. You need to use the console connections initially because they don't have any IP addresses in them on the Ethernet. You want to add in that configuration. At least I feel that way because I like doing things over SSH.
I find it a lot faster and a lot safer than doing it over the consoles. So what I'm going to tell you is this is the way I tend to do it. Doesn't mean I have to do it this way. Obviously you can change things the way you see fit as long as you get the the work done that that's needed.
So basically you need to put in the the management interfaces. You need that static route to that default gateway and put in the Juniper PS user ID and and the well-known credentials that we all know and love. I put in here to verify SSH login because sometimes I'm stupid and I forget to add the Juniper PS user ID.
And then you wonder why you can't log in using SSH as root. And that's because root login denies the default these days in the code. So but if you put in the Juniper PS user ID, you should be fine. Let's make sure it works.
One of the things I find. Sorry, go ahead.

<!-- image -->

**Erickson, James** 6:14
Uh.
Oh, one thing I was gonna add here, the just SSH ING want to or you know, connecting via SSH to the new devices.
The the fully qualified domain name should work after telemetry. Is that what you've noticed?

<!-- image -->

**Czirjak, Gery** 6:38
It it does. I do not do what you wanted us to do, which is to add it into the local host list because I really don't care. So I've never done it to be honest, but I never use that. I use the IP address all the time.

<!-- image -->

**Erickson, James** 6:45
Yeah.
Yeah.
Yeah, yeah. And that's it does well, well, the.

<!-- image -->

**Czirjak, Gery** 6:55
That way.
It always works, right? You don't need to go to DNS, so.

<!-- image -->

**Erickson, James** 7:07
If if we had um.
Well, yeah, and we we do have it with the adding it to the file, the local SSH config file and I've come back in later and added these in for things you know when.
And I that's not a big deal. It's really kind of an easy process. I just the being able to just use the host name really.
Adds value to the whole process, I think, rather than having to go look up an IP address or or remember that full domain name, you know.

<!-- image -->

**Czirjak, Gery** 7:54
Yeah, whatever works. I just don't like typing any more administrivia than I have to, so that's why I haven't been doing it to me.

<!-- image -->

**Erickson, James** 7:55
Um.
Yeah.
If it if, if, if nobody's looked at that, I've shown Mohan a couple of times or you know the but having.
Some literacy with VI or whatever other text editor you want to use for it on in their bash shell. You know, just being able to edit that config local SH config.
To add host names to it if well and and for anyone that needs more information on how to do that.

<!-- image -->

**Czirjak, Gery** 8:31
Yeah, I get you.

<!-- image -->

**Erickson, James** 8:42
Um, yeah, contact me.

<!-- image -->

**Czirjak, Gery** 8:42
Contact James.

<!-- image -->

**Reddy, Resha** 8:46
I.

<!-- image -->

**Czirjak, Gery** 8:46
Yeah, and hope they don't change the server that we use again, so you get to move it all, but that's OK.

<!-- image -->

**Erickson, James** 8:51
I don't think this one's going anywhere. I think it's pretty stable, but yeah, go ahead. Sorry.

<!-- image -->

**Kanumuru, Mohan** 8:52
So I'm.

<!-- image -->

**Czirjak, Gery** 8:55
Probably not. Yep. But who knows?

<!-- image -->

**Kanumuru, Mohan** 8:56
So I I'm just curious, so at what point the the Verizon DNS supposed to work?

<!-- image -->

**Czirjak, Gery** 9:04
It should work by the time we get the I spec because it's actually triggered. It's done by the in the background by the telemetry folks. They actually assign those names. From what I understand we.
The guys in engineering request them, and my understanding is that the actual name assignment is done by the IDN folks, and that's why you'll find sometimes they're wrong in the I spec.
We have seen that and if they're wrong, we sorry.

<!-- image -->

**Kanumuru, Mohan** 9:35
So yeah, so usually that that should happen within a matter of days after this layer one testing L1 testing time frame.

<!-- image -->

**Czirjak, Gery** 9:46
Well, correct me if I'm wrong, James, but I have never seen it not be there before we even got the ice back.

<!-- image -->

**Erickson, James** 9:58
That yeah, no, we we we've always had the telemetry request in the I spec every time we've got it.

<!-- image -->

**Kanumuru, Mohan** 10:07
OK.

<!-- image -->

**Czirjak, Gery** 10:07
And Mohan's asking if it's in DNS by then, I believe it is.

<!-- image -->

**Erickson, James** 10:09
So and and the.
In the in DNS, yeah, yeah and.
Um.
But we still don't know how that's matched up with like the TACACS+, the ISE entry. It's not at all. Do they use the ISE for for DNS or create another record for it?

<!-- image -->

**Czirjak, Gery** 10:27
Oh, it's not. Yeah, it's not now.
Nope.
No, no, you know that you're the one that taught me how to do it.

<!-- image -->

**Erickson, James** 10:39
Well, I I know I put it in. I taught you how to put it in ISE. It's just what happens on the background with the once we add a node in there.

<!-- image -->

**Czirjak, Gery** 10:48
Well, the names aren't even the same in ice. They're slightly different, right? So.

<!-- image -->

**Erickson, James** 10:52
Yeah.

<!-- image -->

**Kanumuru, Mohan** 10:53
So wait, wait, wait. So I'm sorry. So what is the Tacx connection here? Is it? Is it?

<!-- image -->

**Czirjak, Gery** 10:54
So.

<!-- image -->

**Erickson, James** 10:54
So.

<!-- image -->

**Czirjak, Gery** 11:01
There's a Cisco ISE server that provides TACACS+ control to these devices. So when you log into the device, let's say you're you're logging in one of the production boxes that we migrated already.

<!-- image -->

**Kanumuru, Mohan** 11:04
OK.
Right.
Mhm.
Mhm.

<!-- image -->

**Czirjak, Gery** 11:17
It'll send out TACACS+ request to the server with your credentials to make sure you're allowed in. That's that's an ISE box from Cisco. It's 1000 years old and it's pretty flaky.

<!-- image -->

**Kanumuru, Mohan** 11:20
Right.
Yes.
OK, so.
So OK that's that's for the TACACS+ authentication and but we have a the moment we have went through the layer one testing phase basic configuration.
At least at that time, local Juniper PS will be there.

<!-- image -->

**Czirjak, Gery** 11:50
But when we get it, nothing is there, right? We connect via console. It's probably, you know, amnesiac or not. It varies, but you can log in at that point and add the Juniper PS user ID and credentials. Later on you'll see in in slides coming we add it to ICE.

<!-- image -->

**Kanumuru, Mohan** 11:51
Uh.
Right, right.
Mhm.

<!-- image -->

**Czirjak, Gery** 12:10
It's not there yet.

<!-- image -->

**Kanumuru, Mohan** 12:10
Got you.
We add the TACACS+ configuration on the on the device the the I the on the ISE server.

<!-- image -->

**Czirjak, Gery** 12:15
Yes.
In the device and into the server both. Yes, Sir. And you'll see it in a few minutes.

<!-- image -->

**Kanumuru, Mohan** 12:20
Oh, we add that into the server. The information about the device we OK.

<!-- image -->

**Erickson, James** 12:22
Yeah, yeah, there's a self, yeah.

<!-- image -->

**Kanumuru, Mohan** 12:28
OK, so OK, so that's the one and on the DNS part, once the Verizon DNS is provisioned with the device information, do we need to include a domain in the in the host name or just typing host name is will will be enough?
When we want to do the through the name name, when we want to connect to the device through name instead of IP address.

<!-- image -->

**Czirjak, Gery** 12:56
I really doubt you need a domain, but I I've never tried.

<!-- image -->

**Kanumuru, Mohan** 13:00
OK.

<!-- image -->

**Don Nguyen** 13:02
So, Gary, are you the one who add the new device into ICE or somebody else? Oh, you're the one, OK?

<!-- image -->

**Czirjak, Gery** 13:06
Yes, Sir.

<!-- image -->

**Kanumuru, Mohan** 13:09
But not the DNS part. The DNS servers. Verizon is doing it.

<!-- image -->

**Czirjak, Gery** 13:14
I think this is it. Min MGT or is there a dash there? I don't remember.

<!-- image -->

**Kanumuru, Mohan** 13:17
Mhm.

<!-- image -->

**Czirjak, Gery** 13:21
Yeah, so you don't need a domain. That answer your question, Mohan?

<!-- image -->

**Kanumuru, Mohan** 13:24
Yes, thank you.

<!-- image -->

**Erickson, James** 13:28
That's when you use the the host name that's written in the ice back, right?

<!-- image -->

**Czirjak, Gery** 13:34
Correct. Well, otherwise DNS wouldn't work, right?

<!-- image -->

**Erickson, James** 13:35
Yeah, OK.
Yeah.
OK, so you don't need actually the whole if fully equal if I don't mean you. All right, that's fine. I I just never really. I've been doing this so long and I I didn't even link those two, but you know again those.

<!-- image -->

**Czirjak, Gery** 13:41
And I didn't, yeah.
Correct. Right. Yeah. Yeah, I'd be surprised.

<!-- image -->

**Erickson, James** 13:57
Um.
Yeah, sorry.

<!-- image -->

**Czirjak, Gery** 14:02
No worries, no worries. All right, so so while you're in the boxes, one of the tasks we have to do for layer one is provide the output of show chassis hardware in XML format for the devices that is needed.

<!-- image -->

**Erickson, James** 14:04
Go ahead.

<!-- image -->

**Czirjak, Gery** 14:19
Needs to be sent to the service manager who happens to be Jason Abercrombie these days, and he uses that to provide to enable access for JTAC support. So you need to pull that stuff at some point during layer one. I do it here because that way I'll remember.
To do it and I basically just save it in a file. I'm sure you guys have seen this before, right? It looks here's Tes for example. It just looks like this, right? The show chassis hardware just in XML format.
Not very interesting, right?
Anyway, so yeah, at some point you will need to send that to Jason Abercrombie, and I do have that noted further down in the slides as one of the steps, but I extract it at this point. Personally, you don't have to do it at this point. Like I say, it's just the way I do it.
You need to verify the software in the devices. Sometimes it's current, most times it's not. So if you do need to update the software in them, you can do it at this stage or you can do it later on. Again, for me, I prefer to do it up front so that the code is in there already.
The code is on all of our jump servers, so should be readily available. I just put this note in here. It's 4400, double check the firmware version. I don't think we've had a problem with this in a long time, but way back when they were shipping them out with some dated firmware.
Just make sure you do that.
Carry on, need to update the base configs and you guys have all seen the templates for the base configs that James put together. So all that data is there. Bear in mind there's a couple of silly things when we do this.
SNMP V3 is just goofy. Now look, why is this bracket in there? It requires a second commit when we do it. The first time you dropped the user ID and password information in, it goes and generates the engine ID and.
Creates this this set up, but for some unknown reason, Junos doesn't bother to update the password information when it does that, so it just won't work when you try to use it afterwards. So you need to do a second commit of all that authentication information.
In order to get that to work and this is just a very famous problem. And when you when you go ask the SNMP guys, the network management folks to add it, they'll come back and say we can't get to it and that's 99% of the times this is what it is.
As well. Sorry, go ahead.

<!-- image -->

**Erickson, James** 17:14
Yeah, no.
Oh yeah, SNMP also doesn't like the the hash version of the keys to be pasted in to the configuration.

<!-- image -->

**Czirjak, Gery** 17:26
Yeah, I think that's cause the engine ID thing. I think it's embedded in there.

<!-- image -->

**Erickson, James** 17:31
Yeah. So uh, when if you reset it, you paste it in with the clear text. Um.
But again, this is what's that?

<!-- image -->

**Kanumuru, Mohan** 17:43
So it it's.
No, no, go ahead to.

<!-- image -->

**Erickson, James** 17:48
Oh yeah, it's just the clear text we need to not.
Put into temp or.
Uh, config conversion. You know, like a.
Um.
How to say it? Uh.
The automated templating it it should be a manual step.
I'm thinking, but that's neither here nor there. OK, sorry.

<!-- image -->

**Czirjak, Gery** 18:21
Yeah, we can argue that out when Mohan does his coding. But but yeah, I personally I would rather have him just do it in code because if you're talking about security, all the user, all the IP address and everything are there as well. But but anyway, whatever, I I don't care either way.

<!-- image -->

**Erickson, James** 18:26
Yeah.
Yeah, OK. Yeah.

<!-- image -->

**Czirjak, Gery** 18:40
Bear in mind when you create the file. Sorry, go ahead Mohan.

<!-- image -->

**Kanumuru, Mohan** 18:42
So.
No, on on that second commit. So it's a just a commit, right? It's not like we need to reapply those set commands. Oh, we need to paste. I see. OK, OK.

<!-- image -->

**Czirjak, Gery** 18:53
No, you paste it back in. You paste it back in the set commands, yeah.

<!-- image -->

**Erickson, James** 18:57
Yeah.

<!-- image -->

**Czirjak, Gery** 18:58
Yeah, it's really stupid. They could have done this in Junos for us, but they didn't.

<!-- image -->

**Erickson, James** 19:00
And.
And I found it easy when you're doing the second commit just before you do that, add in that SSH line or SCP line for security.
Therefore.
The commit archives.
Um.
Because that needs to be done manually as well.

<!-- image -->

**Don Nguyen** 19:28
The back up to the remote FTP server.

<!-- image -->

**Czirjak, Gery** 19:32
No, this is, this is, this is the archiving of the config, the auto archiving, right? And so it it's got a it prompts you to accept the key generation. So you have to respond manually. That's where he's going with that. That's why I put it in here.

<!-- image -->

**Erickson, James** 19:33
It's.
Yeah.
Yeah, yeah, it if you if you put it in as a um.
As a script, you know, like a load from a file or load from the terminal or you know several commands at once and right into the command line it it tends to skip that key generation bit.
It and and then fails when it the first time it tries to.
uh archives to commit. So uh

<!-- image -->

20:21
Right.

<!-- image -->

**Erickson, James** 20:25
Take that line, you know, like delete the archival if it's already there, add it back in manually and it will ask.
For that key.

<!-- image -->

**Czirjak, Gery** 20:36
Yeah, yeah, it probably will. I've never seen that be there in advance. That's not something I've ever seen Rob Lapu do, but but you're right, if it's there, get rid of it and put it back. One of the things you may want to do is go to the backup server and make sure the appropriate directory is there that's available.

<!-- image -->

**Erickson, James** 20:37
So.

<!-- image -->

**Czirjak, Gery** 20:53
It should be for the 960s because they're already there, but they may not be. It's always worth and and you should check it anyway to make sure that the archival is actually working. And that's pretty easy. Just, you know, make sure you commit some config, do some committing and you should start seeing some files popping.

<!-- image -->

**Erickson, James** 20:59
Yeah.
Mhm.

<!-- image -->

**Czirjak, Gery** 21:13
up in that directory.

<!-- image -->

**Erickson, James** 21:14
Mm-hmm. It and it does take a couple minutes sometimes, especially for the backup RE, but that's all right.

<!-- image -->

**Czirjak, Gery** 21:19
Yeah.
Yeah.
Yep, Yep, exactly. One of the things I always like to do is to verify that NTP is synchronized. That's usually pretty quick too, but but it's another handy way to make sure things are working.

<!-- image -->

**Erickson, James** 21:32
Yeah.

<!-- image -->

**Czirjak, Gery** 21:38
You need to add the devices these new guys into the S2I filter that's called ISNTS IP com not paged. Just pop over there and show you this if I can.
So if you're familiar with S2I, it looks like this. On the left hand side there's a well-known filter called ISNTS IP com not paged and you need to add your new device in here. For example, here's Tes MR01.
And the idea is simply that once these things become active and alive on the network, they're going to start barking out messages and alarms and things, and you don't want anybody to get paged out at 3:00 AM to try and go look at something that isn't really alive yet in production.

<!-- image -->

**Kanumuru, Mohan** 22:26
So I this this step is we need to reach out to you or James it looks like because not everybody has the credentials on this do I.

<!-- image -->

**Czirjak, Gery** 22:35
Hmm, Resha hasn't fixed that yet.

<!-- image -->

**Kanumuru, Mohan** 22:37
It's not going to be fixed. I think, yeah, that process I think, yeah, I think it's each of us for for me, I don't think I I tried to go in there. I'm not seeing that that particular one you are showing now and for Don.
And Hassan, I think they don't even have access to any of those, right?

<!-- image -->

**Czirjak, Gery** 22:58
So they can't edit this file is what you're saying, but they can control S2I, can't they?

<!-- image -->

**Reddy, Resha** 23:01
Really.

<!-- image -->

**Kanumuru, Mohan** 23:03
Yeah, they can manually go there and add what devices to be monitored during maintenance window.

<!-- image -->

**Czirjak, Gery** 23:10
Right, right. And clear alarms and do that kind of thing. But they can't edit this file, is what you're saying?

<!-- image -->

**Kanumuru, Mohan** 23:11
That's about it. Yep, yep, yep, yep, yep.

<!-- image -->

**Erickson, James** 23:16
Yeah.

<!-- image -->

**Reddy, Resha** 23:16
Interesting. I didn't know that. So I can we can look into that a little bit more, Mohan.

<!-- image -->

**Kanumuru, Mohan** 23:22
No, I'm I'm just wondering if maybe from the process point of view also instead of unnecessarily going behind Verizon team, at least two of us have access within our team. I think it's better to to.

<!-- image -->

**Czirjak, Gery** 23:23
Yes.

<!-- image -->

**Reddy, Resha** 23:34
Yeah, yeah.

<!-- image -->

**Kanumuru, Mohan** 23:38
At least two of them have one of us on vacation or anything. It's not an issue.

<!-- image -->

**Reddy, Resha** 23:43
I.

<!-- image -->

**Kanumuru, Mohan** 23:43
It's a.

<!-- image -->

**Erickson, James** 23:44
Didn't we? Last time we were talking about this with Verizon, didn't they tell us Abid was responsible for the groups now?

<!-- image -->

**Reddy, Resha** 23:46
Yes.

<!-- image -->

**Kanumuru, Mohan** 23:51
The.

<!-- image -->

**Reddy, Resha** 23:54
I don't remember that, is he?
Because I've never gone to him for S2I. I've always been told to create an AOAS ticket for it.

<!-- image -->

**Erickson, James** 24:03
Yeah.

<!-- image -->

**Donaldson, Michael** 24:03
Yeah, I don't remember that either.

<!-- image -->

**Erickson, James** 24:07
Um, I think it was Travis I was talking to, yeah.

<!-- image -->

**Reddy, Resha** 24:08
I think we need to have a conversation with Travis. Yeah, I think we need to have a conversation with Travis and just tell him, like, we need to show him specifically what we can't do because this isn't an overall access issue, right? It's a layer down.

<!-- image -->

**Erickson, James** 24:23
Yeah, it's it's permissions within a specific group that that do that and Clint Wagner was helping with this.

<!-- image -->

**Reddy, Resha** 24:26
Mhm, exactly.

<!-- image -->

**Czirjak, Gery** 24:29
No.
And The thing is, it's not just a layer one thing, right? This this is gonna happen again when you do the migration. You have to pull these out and you have to put the old ones in.

<!-- image -->

**Erickson, James** 24:39
Yeah.

<!-- image -->

**Reddy, Resha** 24:40
Yeah, I want. I want a room.
I want everyone to have the access. I don't want us to rely on just two or three people we've done. We we have that situation with ITP and with JIRA already. I don't want to create that as we keep moving ahead.

<!-- image -->

**Kanumuru, Mohan** 24:48
OK.

<!-- image -->

**Czirjak, Gery** 24:52
Yeah, that's bad.

<!-- image -->

**Erickson, James** 24:53
Jira, yeah.

<!-- image -->

**Kanumuru, Mohan** 24:59
OK, I think it makes sense because I think on the day of migration we need to make sure that it's activated.

<!-- image -->

**Reddy, Resha** 25:04
Mhm.
Yes.

<!-- image -->

**Czirjak, Gery** 25:07
Yes, yes. And if you ever do a decom, you'll be ripping out the old one. So, so it it just goes on and on.

<!-- image -->

**Reddy, Resha** 25:10
Mhm, mhm.
Yeah, yeah, I'll add that to my list because there is. I still have to follow up on the JIRA access. I did ask. I did send a note in just as a side note for Nick because we have to try the access and then I sent a note in to Carla, but.
Carla doesn't respond to anything at this point. I don't know if she's affected by anything, so I'm gonna ask Travis if he has any idea who we can contact.
But that's a sign in.

<!-- image -->

**Czirjak, Gery** 25:39
Thank you. You can add it to that little bitty list of yours.
Which back in the beginning, guys, remember I said do your own CRQs because Resha's got nothing to do, right?
I thought I'd share this with you as well. This is not important. Again, this is just the way I do it. So on the server, what I did is I grabbed the templates that James had put on the spreadsheet templates.
And what I do is I just edit this file here, this template file. It just again, it's the way I do it doesn't mean it's right or wrong. It just works conveniently for me, right?
So basically, up here are all the things that need to be changed in a given site, right? And below there is all the stuff that's always the same, so nobody cares, right? So basically, if you're a VI hack, right, it's pretty easy.
Need to go, you know, just edit these addresses out right? And it means basically I have to do 5 changes to make a change from one site to another and it's as simple as you know escape colon percent S slash like very obvious like editing commands right?
Slash 1.1 dot 1.1 slash global done. It's changed all of those, right? So basically I do that for five different things and then it's done. But you know, that's just the way I do it. Doesn't mean you have to do it that way. It just it's something that does need to be created.
Created when you do the layer one.

<!-- image -->

**Kanumuru, Mohan** 27:24
In a nutshell, it says that that's exactly the same. No, in a in a. Yeah, I think James, I think Jerry, I mean, sorry, I think Jerry, it's a it's a nutshell. It's the same thing that the Jinja2 is doing exactly in the background. We just captured in one file all the variables and.

<!-- image -->

**Czirjak, Gery** 27:25
And Mohan's gonna make this all go away. Sorry.
Yep.

<!-- image -->

**Kanumuru, Mohan** 27:40
It it substitutes those values into that same thing.

<!-- image -->

**Czirjak, Gery** 27:43
Yep. Yep. So like I say, Mohan's our hero. He's gonna take care of all this pain for us.
I don't think he's gonna add this S2I filter input though, but anyway.

<!-- image -->

**Kanumuru, Mohan** 27:52
It is.

<!-- image -->

**Czirjak, Gery** 27:58
OK, so we need to add these devices to ICE and then we need to make sure it works. So you'll need to go through those steps to log into ICE, add the IP address, host name in there and then save it. And it does usually take a little bit.
It before it wakes up and notices, but at some point you should make sure that your TACACS+ access to all of the things that you've entered actually work right. Be careful when you do this because you can't change it after you've.
Entered it. You need to get their ISE guy to go in and either rip it out so you can redo it or change it. So that's I always makes me very nervous to do this step because if you if you mistype it, you ****** it up, save it. It's it's in there. Period.
I should have. I should have copied this in to show you. I can, but I don't think it's terribly interesting. If you ever end up doing it, probably easier to show you at the time because you'll forget how to do it if you don't do it.
Is that reasonable to you guys?

<!-- image -->

**Erickson, James** 29:08
There is.
Yeah, there's.

<!-- image -->

**Czirjak, Gery** 29:12
I can step through it if you want.

<!-- image -->

**Erickson, James** 29:14
Well, let I think we should because there's one drop down box that I think is is important that we discuss.

<!-- image -->

**Czirjak, Gery** 29:17
OK.
All right.
Let me shrink this. Let me shrink this. Let me start this.
And I apologize, my hands are very shaky today, so.
Oh.

<!-- image -->

**Don Nguyen** 29:37
It's OK, Gary, you're a little bit cold.

<!-- image -->

**Czirjak, Gery** 29:40
No, it's just it's it's the surgery stuff.

<!-- image -->

**Reddy, Resha** 29:41
Physical therapy.

<!-- image -->

**Czirjak, Gery** 29:44
So James, you were talking about access to venue the other day there. That's what it does for me. Same as Resha.

<!-- image -->

**Erickson, James** 29:50
Yeah.

<!-- image -->

**Czirjak, Gery** 29:54
Anyway.

<!-- image -->

**Erickson, James** 29:56
Oh.

<!-- image -->

**Czirjak, Gery** 29:56
So ISE. Oh, wrong one. Sorry, that's the old one. You don't want that one. ISE new.
Hell does it want now?
Uh.
I haven't done this in a while.
Are you logging in? Yes.
Oh, you piece of junk.
All right, so I really don't. I really want to be careful doing this because I don't want to add something that doesn't belong here.

<!-- image -->

**Erickson, James** 30:51
Yeah, no, we shouldn't need to add anything, just or click the add network devices. We won't submit it though.

<!-- image -->

**Czirjak, Gery** 30:58
Yeah, it's just I don't want to actually do one, right? So, but basically, so you enter an IP address, right? 10101. You enter its host name, which is a little different than the one from DNS I don't know why, but we've decided to do it that way.

<!-- image -->

**Erickson, James** 31:04
Yeah.
1.
Yeah.

<!-- image -->

**Czirjak, Gery** 31:19
And you'll need to put in all three, the VIP, RE0 and RE1.
OK, and then this is what he's talking about here is the device type and God knows what it really should be.

<!-- image -->

**Erickson, James** 31:27
Yeah.

<!-- image -->

**Czirjak, Gery** 31:35
But way down here somewhere it says Juniper VoIP.
Where is it? Am I missing it? There it is, Juniper VoIP.

<!-- image -->

**Erickson, James** 31:42
Yeah, up five. Yeah, so.
Well, show show the other options there, because you know this is in production, right? We're gonna be choosing Juniper VoIP. The old ones you shouldn't use at all.

<!-- image -->

**Czirjak, Gery** 31:56
Yep.

<!-- image -->

**Erickson, James** 32:03
And then the VoIP for the lab. Those are the only four that are even related, relevant to us, yeah.

<!-- image -->

**Czirjak, Gery** 32:06
Yeah.
And don't use the Fujitsu or Ciena.

<!-- image -->

**Kanumuru, Mohan** 32:14
So the so it looks like there is Juniper QFX so so there is nothing like MX and EX. No differences for all the three device types that you are currently playing 960.

<!-- image -->

**Erickson, James** 32:15
And then?
Good.

<!-- image -->

**Czirjak, Gery** 32:29
I've always used this.

<!-- image -->

**Kanumuru, Mohan** 32:30
One one thing. OK, that's good.

<!-- image -->

**Erickson, James** 32:33
Yeah, now you do need to pay attention to the country. Um, because we are doing it just those few that are out of.

<!-- image -->

**Czirjak, Gery** 32:39
Yeah.

<!-- image -->

**Erickson, James** 32:44
Out of the country, but yeah.

<!-- image -->

**Kanumuru, Mohan** 32:48
OK, so for the MX we create 3 entries, VIP RE0RE1 all lower case. And what about for the EX? It's just the.

<!-- image -->

**Erickson, James** 32:57
Mhm.

<!-- image -->

**Czirjak, Gery** 33:01
Yeah.

<!-- image -->

**Erickson, James** 33:03
Just the one.

<!-- image -->

**Kanumuru, Mohan** 33:04
No, no dash. It's just E switch E switch 01.

<!-- image -->

**Erickson, James** 33:07
Yeah, just just use the.
Yeah, mm-hmm.

<!-- image -->

**Kanumuru, Mohan** 33:10
OK.

<!-- image -->

**Czirjak, Gery** 33:12
And in a VC case, what do you do then, James?

<!-- image -->

**Erickson, James** 33:15
If there's still only one IP address, so it's still just.

<!-- image -->

**Kanumuru, Mohan** 33:20
OK.

<!-- image -->

**Erickson, James** 33:21
ESW 01 or 02, just the host name. Yeah.

<!-- image -->

**Czirjak, Gery** 33:24
OK, so that's the point I was trying to make, even though there are other IP addresses assigned to it.

<!-- image -->

**Erickson, James** 33:32
Yeah, it's not a per interface thing.

<!-- image -->

**Czirjak, Gery** 33:33
OK, let me get out of here before I screw something.

<!-- image -->

**Erickson, James** 33:35
Yeah.

<!-- image -->

**Czirjak, Gery** 33:38
This is what I mean. If you mistype this and I have, then you have to go get someone to help you fix it.

<!-- image -->

**Kanumuru, Mohan** 33:44
Could you please put put this link also in the chat please?

<!-- image -->

**Czirjak, Gery** 33:49
I can bear in mind this is accessible via the VDI, right?

<!-- image -->

**Kanumuru, Mohan** 33:50
The ice.
Yeah, yeah.

<!-- image -->

**Czirjak, Gery** 33:57
Uh, where's the chat? Uh oh God, now I have to remember how to get to it.

<!-- image -->

**Erickson, James** 33:58
Yeah.
Now that self-service tool.
That self-service tool also has a search feature that lets you search for an IP address, you know, or or a host name I believe to see if something's already in there.

<!-- image -->

**Czirjak, Gery** 34:14
I have no idea how to get to the chat.

<!-- image -->

**Erickson, James** 34:17
So.

<!-- image -->

**Czirjak, Gery** 34:20
I have no idea how to get to the chat. Sorry.

<!-- image -->

**Kanumuru, Mohan** 34:24
Yeah, that's fine.

<!-- image -->

**Czirjak, Gery** 34:26
I've always had this problem with this thing.

<!-- image -->

**Reddy, Resha** 34:28
The What link are you looking for, Mohan?

<!-- image -->

**Kanumuru, Mohan** 34:32
The I server.

<!-- image -->

**Czirjak, Gery** 34:32
He wants me to put the ISE link in.

<!-- image -->

**Reddy, Resha** 34:34
Uh, OK.
You can put it in after you're done, Gary.

<!-- image -->

**Czirjak, Gery** 34:41
OK, yeah, yeah. Then maybe that'll be easier. Where were we? OK, so we're here. All right, so we've done ICE. Like, say, verify it. Make sure it works. Because if you don't, it'll be embarrassing when the guys can't get to the box to verify their access.

<!-- image -->

**Reddy, Resha** 34:44
Mhm.

<!-- image -->

**Czirjak, Gery** 34:58
They they do use TACACS+ to get into the box to verify it.
All right, so a little more nitty-gritty stuff here. So when you're logging into the boxes, you got to make sure the hardware build is right. Ideally reference the ispec if you need to look at the LLDS because sometimes the ispec is missing something or isn't clear.
I'm sure the LLD will always clarify because nothing in there makes any sense, but that's OK. And it's, I think, worth going to the legacy equipment side and making sure that things match the way you expect, right? At this point, if you're logging into the legacy gear, it's probably worth making sure.
That the transceiver components you need for the crosslinks, the migration crosslinks are available. OK, make sure that they are there.
Should have been done already before this, because what you're going to do at some point is you're going to go in here and try and bring these up and make sure they work. But but make sure that like James says, half the time we have to steal these from somewhere else, but that should have already been done.
Make sure the line cards are there that you expect. You know the SC BS, this and that, all the transceivers and and while there is the point about the XF BS.
Open that non-service impacting CRQ when you're ready to go do this verification. OK, and all this stuff is in the MOP, right? Verify all the connections. There's crossovers between the new routers. There's crossover connections between the new and the old.
When you do these, the new devices, Juniper defaults up, right? So you basically want to disable them one at a time, make sure the right one goes down, and you can turn it back up or not turn it back up depending on what mood you're in.
From a migration point of view, I think it might depends on the site whether it makes it harder or easier for the poor migration guy, whether he has to turn them all down or bring them back up. I think it's kind of site dependent on what works better that way.
The old micronodes was easier just to leave them up with the 960s. I don't know. Yeah, James, it might be easier if we left them down. I don't know what you think of that.

<!-- image -->

**Kanumuru, Mohan** 37:32
So for the L2 layer layer one testing, so the.
The interconnection between the new and the legacy is supposed to be done. The wiring is supposed to be done.

<!-- image -->

**Czirjak, Gery** 37:42
Yes, at at the point where you're doing this, it should have been done.

<!-- image -->

**Kanumuru, Mohan** 37:43
OK.
OK, so it's a it's a matter of if it is disabled physically we we through the CRQ we go and enable physically and see the light or the link be coming up.

<!-- image -->

**Czirjak, Gery** 37:57
Yes, yes, you should. So with the CRQ open, you can go to the legacy equipment. You first you check and make sure there's nothing weird on those connections. That is scary, right? In case you bring something up that you shouldn't, it should be clean.
And then bring it up, make sure that the connection comes up on both sides, and then make sure you tear it back down again because you don't want to turn it up and leave it up. It is their production equipment.

<!-- image -->

**Kanumuru, Mohan** 38:29
Thank you.

<!-- image -->

**Czirjak, Gery** 38:31
And then you can wander into S2I and get rid of any alarms that happened while you did that, although between you and me, that's a pretty questionable value because nobody looks at S2I alarms anyway.
Um.
Anyway, point here, you can't verify some of the connections, right? Like stuff that's currently in production, the firewall connections, the SBCs, it's not. You can't really verify those as having been.
That are saying they're ready for use 'cause they're not connected yet, right? So all you can do is make sure that the actual expected physical ports are present and available, and that's about all you can do with those.
And don't forget to close the curtain when you're finished. OK, now you this may have worked just perfectly and everything's wonderful, in which case you can send a nice little e-mail back to the triggering e-mail that you got from Rob or Raysha and you can say this is all good. The world is a wonderful place.
Or you'll have to reply and say, oh, by the way, this didn't work, this didn't work, this didn't, that didn't work. And then usually what we do is we get them like a little spreadsheet sort of thing that shows what should have been and what did not happen. And you can just steal that directly from the I spec and drop it in.
If there were, sorry.

<!-- image -->

**Reddy, Resha** 39:54
So the one comment I'll make there though, if you when you reply back, reply all because there are several people on that e-mail chain that need to know when layer one is complete.

<!-- image -->

**Czirjak, Gery** 40:06
Right, right.

<!-- image -->

**Reddy, Resha** 40:06
So don't just don't just do a reply or don't reply to just a few of the people reply all.

<!-- image -->

**Czirjak, Gery** 40:11
Yeah, I am. I've always been on the impression that anything that we get from Verizon, I reply all unless it's very, you know, friendly conversation between two people.

<!-- image -->

**Reddy, Resha** 40:14
I.
Mhm. Thank you.
Well, the reason I say that is sometimes when you reply with issues, as you're going through the issues, you feel bad including everyone on those replies back and forth. And so you pare down that discussion, right? But then when you get to a point where you say, OK, looks like everything's resolved.

<!-- image -->

**Czirjak, Gery** 40:34
Yeah.

<!-- image -->

**Reddy, Resha** 40:43
That resolution, everyone needs to know, yeah.

<!-- image -->

**Czirjak, Gery** 40:44
Everybody needs to know. Yep, Yep, agree. Yeah, bear in mind. One thing guys, if you do run into problems, once they get addressed, you get to do this all over again. But the physical verification, you'll need a Kirk. You'll need to do the physical verification because think about it, the tech went out and maybe.

<!-- image -->

**Reddy, Resha** 40:56
Mhm.

<!-- image -->

40:57
Yeah.

<!-- image -->

**Czirjak, Gery** 41:04
He reran a cable or did this or did that and may have broken 15 other things while he was at it. So unfortunately you got to go recheck them and with the 960s that is ugly because there's so many connections.

<!-- image -->

**Erickson, James** 41:12
Yeah.

<!-- image -->

**Reddy, Resha** 41:18
Yeah, and and and it could be that you're resolving issues over. It could be just one week. Sometimes it's taken us two or three months.

<!-- image -->

**Erickson, James** 41:18
Yeah.

<!-- image -->

**Czirjak, Gery** 41:26
Yep, Yep, Yep.

<!-- image -->

**Reddy, Resha** 41:27
That's another reason why, because it's been so long, so you don't know who's done what.

<!-- image -->

**Erickson, James** 41:28
Yeah.

<!-- image -->

**Czirjak, Gery** 41:31
Yeah, which was the one we did recently where they put all third-party copper SFPs in and none of them worked. We had like 30 of them.

<!-- image -->

**Reddy, Resha** 41:39
Oh yeah, was that DNG?

<!-- image -->

**Czirjak, Gery** 41:42
I don't remember, but it was one of them.

<!-- image -->

**Reddy, Resha** 41:43
I think it was, yeah, yeah.

<!-- image -->

**Czirjak, Gery** 41:46
Yeah, it was the one of the the 27 node, I think the new 27 node that we did. So that took a long time. They had to go get all new optics, ship them out, replace them all. So thank goodness Damian did that and I did.

<!-- image -->

**Reddy, Resha** 41:50
Mhm, Yep.
Eating.

<!-- image -->

**Erickson, James** 41:57
Yeah, sometimes there's.
Yeah.
You know, especially if there's a telemetry, um.
Mess up like the IDN Ethernet doesn't work. That's.

<!-- image -->

**Reddy, Resha** 42:10
Yes.
Time consuming.

<!-- image -->

**Erickson, James** 42:15
Yeah, 'cause that just adds another team and another process and all that. Um.
Putting in SF PS in the right place, you know, assuming they're even correct.
Firmware. If there's another PR that comes out, this is your chance. You need to make sure you're running the right firm firmware if if if we need to. That was an issue with some of the EXS. It's been resolved with the ones, the new ones that we've been shipping to them.
Um, but this is the chance to catch not just the version, but firmware.

<!-- image -->

**Czirjak, Gery** 42:55
I'd be cautious about that statement a bit though, because certainly I agree with you 100% about the 4400 firmware issue. I don't think we really should be messing around with, say, MX firmware or whatever.

<!-- image -->

**Erickson, James** 43:05
OK.

<!-- image -->

**Czirjak, Gery** 43:10
Without having that approved by Verizon, because there there are sometimes updates that are done in that sense and they need to agree to it or not you.

<!-- image -->

**Erickson, James** 43:15
Yeah.
Well, don't get me wrong. Even the EX4400, they knew about it. We tested the new firmware in the lab during the certification, yeah.

<!-- image -->

**Czirjak, Gery** 43:26
Yep.
Right, right.

<!-- image -->

**Reddy, Resha** 43:30
That's what I was going to say. Yep, that's what I was going to say. You can't just say, you know what, there's new firmware out there. Everything that we put in from that standpoint, from a configuration, anything touching that has to be tested in the lab.

<!-- image -->

**Czirjak, Gery** 43:32
Yeah.
Yeah, yeah, and approved.

<!-- image -->

**Erickson, James** 43:44
Yeah.

<!-- image -->

**Kanumuru, Mohan** 43:45
So, so we have A and if so we have a what version of what firmware version and what Juno's version for each device type that we need, we can say just match for it. That's it.

<!-- image -->

**Reddy, Resha** 43:51
Yes.

<!-- image -->

**Erickson, James** 44:00
Yeah.

<!-- image -->

**Kanumuru, Mohan** 44:03
So it's in the LLD document or where do we have this firmware ID information?

<!-- image -->

**Czirjak, Gery** 44:07
It's in the back of your mind.

<!-- image -->

**Erickson, James** 44:11
Yeah, we haven't been tracking firmware except for in discussions with with Verizon in our weeklies.

<!-- image -->

**Czirjak, Gery** 44:18
Yeah, I'll tell you what, I'll, I'll put a note in here on the 4400 one because that's the only one that's really concerning at the moment.

<!-- image -->

**Erickson, James** 44:26
Yeah, that's the only case we've run into it. Yeah, and anything Rev 13 and higher on that specific hardware has the right firmware.

<!-- image -->

**Czirjak, Gery** 44:30
The code.
And the code as far as the Junos goes is is a is a standard across the board basically and if you you will know what to put in there because it takes a long time to get it started and approved to make a change to that.

<!-- image -->

**Erickson, James** 44:40
Um.

<!-- image -->

**Czirjak, Gery** 44:55
And right now you saw the PIIR stuff coming out. That's for their next going to their next version of code 24 dot whatever they end up doing.
So right now it's 21.2R3S7.7, which is reasonably quite obvious, isn't it? Oh, but anyway.

<!-- image -->

**Erickson, James** 45:13
Only four years behind.

<!-- image -->

**Czirjak, Gery** 45:17
But yeah, I'll put in the I thought about putting in the firmware number for the 4400. I did not because I didn't want it to be static in a document, but maybe I'll maybe I'll stick it in the chat.

<!-- image -->

**Erickson, James** 45:26
Right.
Oh, no, just.
Just put the FPC revision 13.
Or higher.
That because we know that that those revisions of those, that hardware revision has the firmware. Don't have to limit them to a specific.

<!-- image -->

**Czirjak, Gery** 45:55
I've always done a show chassis firmware, but whatever. Yep, that'll work.

<!-- image -->

**Erickson, James** 45:58
Well, I do both. I mean, I I like I said it was only when they were shipping the Rev 12.

<!-- image -->

**Czirjak, Gery** 46:06
Yeah.

<!-- image -->

**Erickson, James** 46:08
Devices you know we that's where we caught it. Then the PR said says anything Rev 13 or higher is fine and I I went and double checked that. I did double check that so.

<!-- image -->

**Czirjak, Gery** 46:20
Thank you. Actually, you know what I'll do?
Yeah, I'll put a link in the to the TSB in in that where I put the note about the 4400. That'll probably be the best way to do it because then you can go look at it and see what's relevant. I'll do that. I'll add that in.

<!-- image -->

**Erickson, James** 46:31
Yeah, yeah, that that.

<!-- image -->

**Czirjak, Gery** 46:40
OK. So that is that basically.
And now to the paperwork, which we all know and love here. So obviously this is already wrong as of well or will be in another 14 days. So you need to send notifications out to the smarts and S&amp;M folks.
The Smart's alias is smarts voip dev as shown there. The SNM folks is well unknown at the moment. At the moment it's probably Matt Trostel as Carol.

<!-- image -->

**Reddy, Resha** 47:16
Yeah, I confirmed that.

<!-- image -->

**Czirjak, Gery** 47:17
Was executed recently. Sorry, I'm still annoyed about that.

<!-- image -->

**Reddy, Resha** 47:19
Oh, ouch. No. But no, I I did. I I know she. I did check in with Matt Trostel separately. And he said that he as of right now. Yes, you're right. It's him. When I asked him, you know that he said he had told you. I said, yeah, I was aware of.
That I wasn't sure if it was a one time thing or a temporary and he I don't think he has a plan to give it to anyone else.

<!-- image -->

**Czirjak, Gery** 47:45
That's gonna be very strange, but anyway, we'll see. I I really wish they would use an alias rather than a person, but whatever.

<!-- image -->

**Reddy, Resha** 47:47
Mm-hmm. Mm-hmm. Yep.
Yeah, it's very single threaded.

<!-- image -->

**Czirjak, Gery** 47:55
Yep. So I put in here confirmation is required within two weeks. This is really driven by the smarts voip guys because there's I think only 1 1/2 people actually doing this work over there now. So we used to give them one week to get back to us. They asked for two weeks.
So I figure, well, we'll get a two weeks for both sides. And now that Carol's gone, God knows how long it'll take to get that done. Cause if, you know, Matt's the manager, he's got 500 things to juggle. I don't know how that'll work, but anyway, we'll see how it plays out.
Do you want me to update this in here, Resha? So it doesn't say Carol Davis. I don't know. It's it's wrong, obviously.

<!-- image -->

**Reddy, Resha** 48:38
Um.

<!-- image -->

**Czirjak, Gery** 48:40
I know what I can do X dot Y.

<!-- image -->

**Reddy, Resha** 48:40
Mhm.
No, you can put Matt Trostel 'cause he's always copied on them anyway, I think.

<!-- image -->

**Czirjak, Gery** 48:47
Yeah, it just that may change again, right?

<!-- image -->

**Reddy, Resha** 48:50
Yeah, but it'll still be someone on his team.

<!-- image -->

**Czirjak, Gery** 48:53
No, that didn't work. I'll have to fix that anyway, OK.

<!-- image -->

**Donaldson, Michael** 48:55
Yeah, he he made it sound like it would be him for a while, that way he responded.

<!-- image -->

**Reddy, Resha** 49:00
Yep.
Exactly. It'll be him for a while, but even if he does hand it off to someone, I think he'll he'll keep track of it for a while. So I think you're fine keeping his name there.

<!-- image -->

**Czirjak, Gery** 49:11
All right. All right. We'll leave it there for now, OK?

<!-- image -->

**Reddy, Resha** 49:13
Mhm.

<!-- image -->

**Czirjak, Gery** 49:15
And anyway, so when you send this e-mail to the smarts guys, you know if you ever have a problem 90% of the times because because of that SNPV 3 idiosyncrasy we discussed earlier and SNM needs Tacx to work. So Matt or whoever.
Be doing that will complain to you if Tacax isn't working. So try and make sure those things are are done before you bother Verizon because it gets kind of embarrassing. The the SMP V3, we screwed that up about half a dozen times before we figured it out.
So it's gets kind of tiring.
There's another e-mail that goes out to an assortment of people confirming that the device archival is operational and ready to go. Again, that people in that list is somewhat variable, but.
The important guy, as far as I know, is Travis Irwin in that one. There's some other names in there as well, but again, it's a little fuzzy as to who's really cares about that.
You also need to make sure that James Rader is in that list. You need to know these things.
Don't forget to send the XML hardware extract to the Juniper service manager. Like I say, it's Jason Abercrombie at the moment. One thing he asked, put the site address in there in that e-mail for him. He does need that.
And it obviously doesn't come out of the throw chassis hardware. You'll have to suck that out of the I spec or wherever you happen to find it. When you put in the address information for the SNP location, you can just Steve that and cut and paste it in there.
Don't forget this like I always do. Don't forget to add the new device to JSI. I know you all know exactly all have access to it and know how to use it, right? That's not a problem.
Is that another thing we're gonna have to walk through at some point, Risha? I don't know.
Does everyone have JSI access JSI?

<!-- image -->

**Reddy, Resha** 51:24
Wait, I'm sorry, which part the other site?
That's a good question. I can't remember if I had it in my checklist. I don't remember requesting it. How did you guys get access to JSI?

<!-- image -->

**Czirjak, Gery** 51:38
You have to get added to it from the account team as I recall.

<!-- image -->

**Donaldson, Michael** 51:46
I thought Mike Stone, I thought Mike Stone was adding those guys.

<!-- image -->

**Czirjak, Gery** 51:46
Or sorry, not account team, not accounting. No, it's what's his name. Art Brenton was doing it.

<!-- image -->

**Donaldson, Michael** 51:53
Oh, that's interesting.

<!-- image -->

**Reddy, Resha** 51:53
Really.

<!-- image -->

**Czirjak, Gery** 51:54
Now how it continues, I don't know. Maybe it's Mike now, I don't know. But when I did, it was Brunton, I think added it for me.

<!-- image -->

**Reddy, Resha** 51:56
Huh.
OK. I'll follow up on that.

<!-- image -->

**Czirjak, Gery** 52:08
And they took off my Comcast, which was I'm happy about because I had GSI access via Comcast sign up.
Oh, and then this last thing, which I really, really, really, really hate, is that we have to ensure that the appropriate documentation updates are completed as directed by Juniper Project Management. And that's as much as I'm going to say about that.
The important thing in my mind is the site checklist and let me show this to you just so you see it. So this is the site checklist for layer one stuff and it's supposed to be all filled in nicely for all these sites that have been done.

<!-- image -->

**Reddy, Resha** 52:36
Yes.

<!-- image -->

**Czirjak, Gery** 52:49
I would really like ratio if you could go through this and and clean it up cause some of this stuff doesn't make any sense.

<!-- image -->

**Reddy, Resha** 52:54
Yep.
Agreed.

<!-- image -->

**Czirjak, Gery** 52:57
But you'll see that there are all these steps just to make sure we don't miss things, right? Basically, you know, did we, did we find all the layer one stuff? Did we fix it all? Did we upgrade the OS? Did we put the base config in? Can you get to the box?

<!-- image -->

**Reddy, Resha** 53:02
Mhm.

<!-- image -->

**Czirjak, Gery** 53:14
What is the upstream PP router type? Which is half the time I guess right? Loop back IP for micro BFD. This is a list which I think Risha has in this second tab here.
Isn't that this OOB IPS for PE?
Think.
No, it's not that. Never mind. I know it's somewhere.

<!-- image -->

**Reddy, Resha** 53:36
Yeah.

<!-- image -->

**Czirjak, Gery** 53:39
Anyway, there's a whole bunch of things we have to do here, right? Basically.

<!-- image -->

**Reddy, Resha** 53:42
Yeah, some of these are confirmation that it's done. Some of them are just reminders. So yes, this does have to be cleaned up and I can consolidate it a bit more, but they're so there. I put it into sections. Yeah, I put it into sections, right. So the whole top part is layer one, you know, all of those checks. Second part is access.

<!-- image -->

**Czirjak, Gery** 53:51
Yeah, we we can work on it together if you like. Yeah.
Right.

<!-- image -->

**Reddy, Resha** 54:02
The third section is all MOP, Kirk, you know, configs, that type of stuff. And the last section is IT assurance related and the reason we have.

<!-- image -->

**Czirjak, Gery** 54:05
Right.
Right, but things like this. We should get rid of this one. For example, plunk configuration that's already in the template done.

<!-- image -->

**Reddy, Resha** 54:14
Yeah, you and I can work on this. Yeah, yeah, we can work on this and we can clean it up. But the the whole reason I've created this, so the way we used to do things is we have a separate planning sheet that's in Google, fully visible to Verizon. And what we normally used to do on our daily calls is go through that planning sheet per.
Site that was it was falling to the wayside because there were so many other things that were going on that we had to discuss. So what I did was I created this sheet that's internal only and it's a you guys updated.
As you move along, that way I don't have to keep asking. You don't have to keep waiting for me to, you know, do that. And then I pull this information and update the Google sheet accordingly.

<!-- image -->

**Czirjak, Gery** 55:00
Oh, thank God.

<!-- image -->

**Reddy, Resha** 55:00
So there's no conversation about this, right? I don't. I don't. Normally we used to have a conversation about all this stuff every single call. There's no conversation anymore unless there's an issue.

<!-- image -->

**Czirjak, Gery** 55:10
Right. Or unless one of us lazy layer one guys forgets to update it and Rasha says how come you haven't updated this?

<!-- image -->

**Reddy, Resha** 55:17
Yeah, exactly. Yeah.

<!-- image -->

**Czirjak, Gery** 55:19
So you so you'll notice here somebody made sure that this was updated today in 12/5 here.

<!-- image -->

**Reddy, Resha** 55:23
I was gonna ask about that because TJ actually created the Kirk for it and it didn't show up in inventory, so I have to see what happened with that.

<!-- image -->

**Czirjak, Gery** 55:35
Yeah, I had to chase Carol. I had to chase Carol about it this morning. She hadn't edited it.

<!-- image -->

**Reddy, Resha** 55:37
Oh.
So, so you knew that I was gonna ask. Good.

<!-- image -->

**Czirjak, Gery** 55:43
No, I just figured I better not have any holes here, but at least none that are my responsibility anyway.

<!-- image -->

**Reddy, Resha** 55:46
But yeah, but that was the whole purpose of this. That's a new process we put in place this year just to make the process easier so we don't have to keep pulling information manually. And then that second tab that Gary talked about, that's for.
The purposes of when you go in because we have to update the descriptions during the maintenance window, so you have all of your information that you need in the right place. So it has all of the VA router details per site and I'll be doing the same thing for all the sites next year. I have to clean this whole thing up.

<!-- image -->

**Czirjak, Gery** 56:22
So anyway, this one I don't find overs to be honest. I don't mind updating this one and it helps me because if when I send out, say the e-mail to Matt, Carol, whoever you want to call it here, you put in the start date here and then you can go back and reference say, oh, did I ever get an answer to that?
Now I was going to ask Rasha this question. This is probably the wrong place to ask this, but what I did personally, because I can't remember these things, is I created a follow-up.

<!-- image -->

**Reddy, Resha** 56:43
Um.
That's not what I would have thought that that acronym stood for, but OK.

<!-- image -->

**Czirjak, Gery** 56:55
Thing here is where I put a copy of the e-mail.
Pretty close. Same concept.

<!-- image -->

**Reddy, Resha** 57:01
No, I like that you do this though, because then if you if you're done with it and you've got your answer, you move it out of here, right? Yeah, that's great.

<!-- image -->

**Czirjak, Gery** 57:09
Exactly, exactly. So I put a copy in the decom file that I've done it. I put a copy here to watch for and then I have to remember to clean it up, which I tend to forget as well. So anyway.

<!-- image -->

**Reddy, Resha** 57:14
That's great.
But I it's and this goes back to this whole and I think I may have mentioned it a couple of times, but for things like that, you do what works for you, right? There are certain things like this sheet that this is what works for the team and that's why it's set up this way. So this is something that will make everyone's lives easier.

<!-- image -->

**Czirjak, Gery** 57:30
Exactly, yeah.

<!-- image -->

**Reddy, Resha** 57:40
Easier, but how you handle the emails that you send out and the follow-ups and keeping track of the things that you have to do. Do it however works for you.

<!-- image -->

**Czirjak, Gery** 57:51
Right. Except I'll I'll add a wrinkle to that though, Raisha, that the how I agree with you. The actual e-mail content is kind of, I don't want to say rigid, but it's defined, right? Raisha and Mike defined it along with Verizon, so you don't want to mess around with those.

<!-- image -->

**Reddy, Resha** 57:57
Yeah.
The.
Yes.
Mhm, yes.

<!-- image -->

**Czirjak, Gery** 58:08
And to be honest, I don't think we have the layer ones written down anywhere conveniently for people, so I should do that.

<!-- image -->

**Reddy, Resha** 58:11
Yeah.
OK.
Layer one, we don't. You're talking about the IT assurance emails.

<!-- image -->

**Czirjak, Gery** 58:18
Yeah, yeah. I don't know if we have. Do we have those somewhere? OK, good. Because I haven't been looking at them. I've just been doing them myself.

<!-- image -->

**Reddy, Resha** 58:18
We do.
Mhm.
Yeah, no, I do. I I created one file that has all of the e-mail templates for all of the IT assurance and for DCOM. Everything's in there. Mm-hmm.

<!-- image -->

**Czirjak, Gery** 58:32
Oh, excellent. Oh, very good. We should add that in here somewhere.

<!-- image -->

**Reddy, Resha** 58:36
Yes, let me find the link. I'll send it to you.

<!-- image -->

**Czirjak, Gery** 58:40
Thank you. All right. So is that reasonably clear, guys? So on that note, IT assurance.
Again, this is the way I do it. This this is a table. This is a template of what it looks like. This is the information that we need to send to half a dozen people, half a dozen different emails. For whatever reason, it seems that Verizon guys.
If the e-mail is not sent to them directly, if they're one of a list, they never look at things. So we have to send these sort of individually, right? So you you send one to the the SNM folks, you send one to this, these people, you send one to that people, but you reuse this.
Table a lot. So I create this table in Excel when I do the layer one stuff and I guess I could show you that. Not that it's terribly interesting, but again, this is again the way I do things right? So I have this table created.
And you see here, this is the address that our friend from service management Jason wants and it's stolen right out of the SNMP location list. And I also stuff this stuff in here, the show chassis hardware, because to me this is an easy way of verifying these devices are pretty much always symmetric.
So this is an easy way to make sure that you know all the transceivers and optics and everything look right. Again, how you work it up to you. It's just the way I happen to do it.
And I think I have one more slide and then I'll shut up. And one more slide is this one, which is just a summary of everything we just talked about.

<!-- image -->

**Reddy, Resha** 1:00:36
Uh.

<!-- image -->

**Czirjak, Gery** 1:00:36
It was just I thought it would be handy to have it. Sorry James, go ahead. Did I miss something?

<!-- image -->

1:00:36
Uh.

<!-- image -->

**Erickson, James** 1:00:40
Really quick, when you say update JSI, that's just putting in the IP at the end of that list, right?

<!-- image -->

**Czirjak, Gery** 1:00:43
Yeah.
Yeah, that's the update. Yep, that's the update. Yep.

<!-- image -->

**Erickson, James** 1:00:49
Yeah.
It's the management IP, the VIP, not and you only need one per router, yeah.

<!-- image -->

**Czirjak, Gery** 1:00:54
Correct. Just the VIP. Yep.
Let me type that so there that's maybe not self-evident, just the VIP address.
I say VIP or master. We always call it VIP. I guess VIP is better because it's not really a master on VX.

<!-- image -->

**Erickson, James** 1:01:18
Yeah.

<!-- image -->

**Czirjak, Gery** 1:01:24
Any questions or is anyone still awake?

<!-- image -->

**Don Nguyen** 1:01:32
Well, very good, Gary.

<!-- image -->

**Czirjak, Gery** 1:01:32
OK.
Like, like it's it's a very simple task. It's just, you know, takes a while.

<!-- image -->

**Don Nguyen** 1:01:35
I do. I do. I do.
So I want to talk to you about these global search replace in VI. How many is instant that you have to stop? If you can write in set you can do it as step is is I think it's more more efficient than Ansible way.

<!-- image -->

**Czirjak, Gery** 1:01:58
I'm not sure what you're saying.

<!-- image -->

**Don Nguyen** 1:01:59
If you know what pattern to replace, yeah, you write that instead of doing S global S in VI stuff, you can write and set a script. Yeah, that will solve all this text editing. A lot more equation, yeah.

<!-- image -->

**Czirjak, Gery** 1:02:09
Oh, I see what you're saying. I think this is all going to go away next week when Mohan shows you how to do it in the future. He's he's going to just have automation to do it. You enter the information in a template file. I I don't want to take Mohan's Thunder away, but basically he's.
You take stuff out of the I spec, enter it into a into a configuration file and then push a button and it goes and creates all these configs for you.
We there's talk Mohan and I have kicked around weird ideas which are probably down the road things of slurping that information right out of the I specs so you don't have to do it about having the system actually connect to the.
End systems and do all that work for you. So Sudhir's doing some of that kind of stuff for some of his automation, but but that's probably not day one stuff, right, Mohan?

<!-- image -->

**Kanumuru, Mohan** 1:03:04
Yeah, yeah, those are all trying to take the existing working models and integrating it.

<!-- image -->

**Czirjak, Gery** 1:03:13
Yeah.
I mean, it's good we have, you know, young people with full of energy, enthusiasm to do all these things like Mohan and Hassan and all that, as opposed to old people like me that can be barely bothered to get up in the morning.

<!-- image -->

**Kanumuru, Mohan** 1:03:28
Yeah, I think it's a it's a maybe we have to in a conversation with Hassan, he mentioned that he's very comfortable. He had done some work before in in his other projects. I think even Don it seems to be he's comfortable maybe.
If you have some thoughts and if you have comfort in in bringing some puzzle pieces to make it efficient for us, yeah, let's let's collaborate.

<!-- image -->

**Czirjak, Gery** 1:04:01
Yeah, yeah, I'll let you and Don work and Hassan work that out, 'cause I have no value at there, so.

<!-- image -->

**Don Nguyen** 1:04:07
Gary, you always play like you.

<!-- image -->

**Kanumuru, Mohan** 1:04:08
Yep.

<!-- image -->

**Don Nguyen** 1:04:12
We depend on you, Gary.

<!-- image -->

**Czirjak, Gery** 1:04:14
Boy, are you in trouble, dear.

<!-- image -->

**Don Nguyen** 1:04:20
So I mean do you have a sample files in in the in TVs or do we have a sample files and I take a look at it. I will see if I can set it for you.

<!-- image -->

**Czirjak, Gery** 1:04:33
You can, but I would suggest you talk to Mohan first because you may be doing work that's just not needed anymore, right?

<!-- image -->

**Don Nguyen** 1:04:42
Right, right, right.

<!-- image -->

**Czirjak, Gery** 1:04:43
Because he his approach is gonna be very different from from what I'm doing, like totally different. He's using Jinja and YAML to do it.

<!-- image -->

**Don Nguyen** 1:04:50
Bye.
Yeah, that's ancible approach, yeah.

<!-- image -->

**Czirjak, Gery** 1:04:57
So I'll let you guys fight that out because I don't know anything about that stuff.

<!-- image -->

**Kanumuru, Mohan** 1:05:03
Yeah, there are several ways to solve problems, but the one you are doing also is and using who are comfortable with VI and typing the half a dozen variables that are there and replacing efficiently.
It's basically different tools are helping us do this. What we want to do is slowly, slowly, small, small baby steps with the right end goal is the incrementally adding value rather than each of them stays.
And then no interconnection between them.

<!-- image -->

**Czirjak, Gery** 1:05:42
Yeah, yeah, I agree. I'll make a point though, is is that it's not just adding value per SE, it's also adding rigor and consistency. Because if you look at this stupid file, OK, this is the way I do it, right? Right or wrong, but sometimes I forget to update.

<!-- image -->

**Kanumuru, Mohan** 1:05:51
Right.

<!-- image -->

**Czirjak, Gery** 1:06:00
Stupid mask, right? Or sometimes I forget to update the connection information here. So if that stuff is automated with whatever process is the appropriate one, that also gives us a lot more consistency and rigor in our work.

<!-- image -->

**Kanumuru, Mohan** 1:06:18
Yeah, the consistency and higher bar for accuracy, yes.

<!-- image -->

**Czirjak, Gery** 1:06:23
Exactly. Yeah. So. So anything you guys, you know, you and Don and Hassan and Sudhir and whoever want to do that, I'm all for it. It's just beyond my skill set.

<!-- image -->

**Kanumuru, Mohan** 1:06:32
Don, how, how, I mean how comfortable are you with going through the high spec and pulling out the relevant information?

<!-- image -->

**Don Nguyen** 1:06:45
I.
I saw the I spec you guys work on the this week and last week, but I haven't seen the actual raw data of the I spec format. Are they kept in the NTBS server?

<!-- image -->

**Czirjak, Gery** 1:06:58
No.

<!-- image -->

**Don Nguyen** 1:06:59
No.

<!-- image -->

**Czirjak, Gery** 1:07:00
No, they're not. They're in venue. That thing I showed you earlier where I was showing James how that we connect to it.

<!-- image -->

**Don Nguyen** 1:07:03
Right.
If I in the.

<!-- image -->

**Czirjak, Gery** 1:07:09
You know what? Nick is, I think, extracting straight from the ice back.

<!-- image -->

**Kanumuru, Mohan** 1:07:09
It's a. It's a basically an Excel file.
It's an excellent.

<!-- image -->

**Don Nguyen** 1:07:14
If I know if you have a a like a CSV file or something in the in the jump box, I can take a look and see how what kind of stuff extract. I can write a script to extract data from there.

<!-- image -->

**Czirjak, Gery** 1:07:26
I'll leave you guys to figure that out because I I don't know what's involved there. These are, I believe, XLS files, XLSM or whatever they're called. I don't think they're CSV. I don't know what the difference is, but I know there's a million macros in there.

<!-- image -->

**Kanumuru, Mohan** 1:07:28
Yeah.

<!-- image -->

**Don Nguyen** 1:07:35
Yeah.

<!-- image -->

**Czirjak, Gery** 1:07:41
And so I don't know any equations.

<!-- image -->

**Don Nguyen** 1:07:42
Yeah, the the macro they they did not CSV format. Yeah, and I I saw the game. He had a trick to get around the restriction by disable the something to just to get the the data into a different table to get around the macro restriction.

<!-- image -->

**Czirjak, Gery** 1:07:46
So.
Yep.
Yeah, yeah.
Yeah, yeah, we do the same thing when we differently. I do the same thing, but I create my own spreadsheet with it. But anyway, same thing, same idea.

<!-- image -->

**Don Nguyen** 1:08:03
Yeah, I mean.

<!-- image -->

**Czirjak, Gery** 1:08:12
So I don't know. Again, I'll let you and Mohan work that out. Nothing, no value add for me there.
James, do you want to shut down this conversation? The the recording, please? If you did, I think you recorded it.
Oh, can I turn it off? I don't think I can.

<!-- image -->

**Erickson, James** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-17T00:52:26.115740+00:00",
      "canonicalTerm": "I-spec",
      "reviewCardId": 43,
      "term": "I spec"
    },
    {
      "appliedAt": "2026-06-17T00:52:27.086099+00:00",
      "canonicalTerm": "Cisco ISE",
      "reviewCardId": 44,
      "term": "ICE"
    },
    {
      "appliedAt": "2026-06-17T00:52:27.936609+00:00",
      "canonicalTerm": "Tacx",
      "reviewCardId": 45,
      "term": "attack hacks"
    },
    {
      "appliedAt": "2026-06-17T00:52:28.571939+00:00",
      "canonicalTerm": "Jinja2",
      "reviewCardId": 46,
      "term": "Ginger 2"
    },
    {
      "appliedAt": "2026-06-17T00:52:30.363364+00:00",
      "canonicalTerm": "Rob Lebu",
      "reviewCardId": 52,
      "term": "Rob Lebuth"
    },
    {
      "appliedAt": "2026-06-17T00:52:30.363780+00:00",
      "canonicalTerm": "Rob Lebu",
      "reviewCardId": 52,
      "term": "Rob Lapu"
    }
  ]
}
-->
