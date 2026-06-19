---
created: 2026-06-17T02:51:29.669325+00:00
updated: 2026-06-17T03:35:11.233641+00:00
concepts:
- Behavioral differences
- Cable matrix
- CCR
- I spec
- Lab certification
- LLD
- MOP
- Nessus security scan
- Provisioning guidelines
- TER
- TREC
- Verizon migration process
entities:
- IPCME
- JIRA
- SIT environment
- VVE team
title: 'Verizon Process 101: Milestones, Gates, and Prerequisites'
indexes:
- '[[Team Index]]'
- '[[Verizon Migration Process]]'
description: Transcript of a Verizon Process 101 meeting covering migration milestones, gates, prerequisites, lab certification, TER/MOP review, and site-specific CCR/NFID workflows.
source: /Users/drhoades/VaultRaw/Verizon Process 101_ Milestones_Gates_Prerequisites (Resha) Transcript.docx
---
<!-- wikiagent:source-metadata
{
  "agentExtractionStatus": "pending",
  "captureKind": "file",
  "capturedAt": "2026-06-17T02:51:29.669325+00:00",
  "conversion": {
    "converter": "/Users/drhoades/WikiAgent/src-tauri/sidecars/.venv/bin/python3",
    "detail": {
      "converter": "docling",
      "doclingVersion": "2.102.1",
      "durationMs": 2481,
      "inputPath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Milestones_Gates_Prerequisites (Resha) Transcript.docx",
      "outputPath": "/Users/drhoades/WikiAgentVault/.wikiagent/cache/docling/verizon-process-101-milestones-gates-prerequisites-resha-transcript-1781664689722034000.md",
      "status": "succeeded"
    },
    "required": true,
    "status": "succeeded"
  },
  "detectedOriginalUrl": null,
  "email": null,
  "fetchedPage": null,
  "importedAt": "2026-06-17T02:51:29.669325+00:00",
  "ingestStatus": "normalized",
  "originalUrl": null,
  "privacyLane": "team",
  "schemaVersion": 2,
  "sourceKind": "word",
  "sourcePath": "/Users/drhoades/VaultRaw/Verizon Process 101_ Milestones_Gates_Prerequisites (Resha) Transcript.docx",
  "sourceSha256": "0f2c2fbc7b14ddd526ca3915fdc4392f548a7dba95164c9312a7e5e3cd0fb26b"
}
-->

<!-- wikiagent:agent-summary:start -->
## Agent Summary

Transcript of a December 3, 2025 Verizon Process 101 session explaining Verizon migration gates and prerequisites, including LLD review, TREC approval, lab certification preparation and execution, cable matrices, TER/MOP review, and transition into site-specific CCR/NFID and VVE/I-spec workflows.
<!-- wikiagent:agent-summary:end -->

**Verizon Process 101 MilestonesGatesPrerequisites (Resha)-20251203\_140349-Meeting Recording**

December 3, 2025, 7:03PM

1h 5m 35s

<!-- image -->

**Reddy, Resha** started transcription

<!-- image -->

0:04
Yes.

<!-- image -->

**Erickson, James** 0:05
Yeah, yeah, we can see it.

<!-- image -->

**Reddy, Resha** 0:06
OK, alright, so.
So like I said, I'm going to start very generic high level. These are different variations of things that we've put together. So I'm just going to pull from each of them. So from a high level perspective, when Verizon determines that there is some sort of migration work that needs to be done.
Whether it's a consolidation or a migration, changing to new design or changing to new equipment, whatever it is, there are certain gates or certain steps that we go through first what they normally do. And you'll see some of this is specific for routes, which some of it is specific for firewall, but it's.
Some of the steps are basically the same. What they do is they normally do a review of what's existing in their legacy system. As for those who were on the call yesterday, that was the same thing. I asked Scott for a list of all of the nodes and sites that are in scope, so we understand.
What the expectation is. So once they do their review, then they'll do the LLD. That's where normally LLDS are created by Verizon. There are instances where we have had to update LLDS.
Or work with them to create LLDs, but they are normally created by Verizon, especially when there are major design changes. That is something that is usually handled by Scott if there are small design changes like we've had with IP SEC recently.
Those we can handle because they're just small updates, not major design changes.
So once they get through their whole design process, and sometimes that can take months, they usually start that way before we even sign a scope with them. When we get the LLD, they do the same thing that that we do normally where they have a gate.
And they do a LLD review and that's a CFT that's with a much larger group. It's to make sure that everyone is on the same page. They understand what the design is from all the different perspectives of the areas of business that need to be involved.
People have a chance to ask questions, poke holes, and then depending on what happens in that, there's either an updated LLD sent out or we just get approval on that call that that LLD is good to go once that LLD is signed off on.
We can then take that LLD and we can start our next step. So that's where we start our ours.
Path starts right here. First item that we normally do and this is all part of our lab cert is the TREQ. That is the test requirement creation and that's normally created in a very specific way. We we have a template that we use.
For test requirements, once we create those test requirements and we usually have been doing an internal review to make sure we've captured everything, we then do a review with Verizon. Normally we do it with the IPCME team and that is John Venuto.
Travis, Scott, Liana, those are the four that we really are concerned about. We'll do the review with them along with a larger group if you know if needed, but normally those are the four that we require on that call.
They will then let us know on that call whether we have the approval to move ahead with testing based on this TREC or if we need to go back because there are certain considerations that we have not brought in. So they either approve the TREC on that call or we send an amendment.
TREC out and they confirm they're good with it. Once we get that approval on the test requirements, then we move over to start all of our standardized work to be able to actually prep for the lab cert and that includes.
The MOP creation, some sort of basic MOP, just a drafted basic MOP, generic for that design to start out with, and then the actual configuration that we'll be putting onto the SIT environment devices.
To move ahead, that also includes things like creating the JIRA for the cable updates and creating the cable matrix that feeds into that. So those are the three. And then James, keep me honest here, those are the three that we really focus on. The cable matrix has many times taken months to get done.
Because we need a lot of input from different application areas, that cable matrix, once completed, gets put in the Jira. Jira is created and sent over to Denver and team.
And then they start working on the cabling and updates in the lab environment. While they're doing that, we work on the actual config and the MOP. Now the only thing out of all of those three that gets reviewed with Verizon is the config, because we want to make sure the config makes sense.
For what we are testing and what we want to implement for the design before we actually start testing in the lab.
So we review the config, get the approval on the config, and that's really our next step to be able to move ahead with the actual lab certification. So I'm gonna stop there for a second to see if that makes sense.

<!-- image -->

**Kanumuru, Mohan** 5:31
So I'm I'm just this is for a a project like PIP 2.5 or a PIP 2.7.

<!-- image -->

**Reddy, Resha** 5:40
Yes, yeah, the DPC. Mm-hmm.

<!-- image -->

**Kanumuru, Mohan** 5:44
Yeah so this is but if there are five sites under work under that 2.7 some example. So this is this is done for the for the entire we take it. Yeah that's what yeah.

<!-- image -->

**Reddy, Resha** 5:52
Mhm.
Design for the entire design, yes.

<!-- image -->

**Kanumuru, Mohan** 6:00
And the rest of the yeah, so when we go into real site migrations, so these steps will not apply there. This is only for the OK, got you.

<!-- image -->

**Reddy, Resha** 6:03
Mhm.
No, because all of this is done before that. So all everything until here, everything in green is all generic for a specific design or set of designs. Then you move into site specific.

<!-- image -->

**Kanumuru, Mohan** 6:18
Got you.
Got ya.

<!-- image -->

**Reddy, Resha** 6:24
Right. But that's a good question. So let me.

<!-- image -->

**Kanumuru, Mohan** 6:27
Yeah.

<!-- image -->

**Reddy, Resha** 6:29
Go to the CCR sheet for a minute. So I don't know how many of you have seen this, but we review this with the install team, the VVE team, and this is basically the site install where they are with their site install. This is NFIDCCR is that you'll hear us reviewing on a weekly.
Basis on our weekly calls with Verizon. So if you'll note in here we have the services. So for example SPIP 7/8 this is SPIP 7/8 SIDA. When I go to Gen. 25 we have like NSRS PIP.
So what we normally do when we get a scope is we go through and get the list of all of the sites and the services on those sites and then we determine the amount of lab certification that are needed based on that.
Right. So for Gen. 2-7 we have SPIP 7-8, we have SPIP 7-8 SIDA and then we have I skip. So we've created, I think it was two or three lab certs based on these combinations. It doesn't. Each lab cert does not have to correspond to each one.
I think in that that's part like a second part of your question. The lab certs are more general. They can encompass 5 sites or one site. It really depends on what design it is.

<!-- image -->

**Erickson, James** 7:52
OK.
But there are are we still doing a separate certification for each unique combination in production?

<!-- image -->

**Reddy, Resha** 8:01
Depending on what the combination is, right? So for example, we've we're doing I skip as.
PIP one and Titan and I can't remember which one we want, but then we also sorry, I was saying the one that we're working on now is SPIP one through 5, ISCIP and Titan, right? So that encompasses these two, but it also takes care of part of DSSN one. Now we did do a lab cert for SPIP 7-8 and SIDA, so.

<!-- image -->

**Erickson, James** 8:17
You cut out for a minute there.

<!-- image -->

**Reddy, Resha** 8:35
That part of it is covered here, so it'll kind of it works for some. It's part parts of the lab cert that work for different sites, if that makes sense.

<!-- image -->

**Erickson, James** 8:45
Yeah.

<!-- image -->

**Reddy, Resha** 8:46
We what we try to do when we get a list of sites and the services is we try to determine the most efficient way to test because each test lab certification as we all know takes months.
So the more lab certs we have, the more delayed those sites will then be.

<!-- image -->

**Erickson, James** 9:01
Yeah.
And even the ISIP in the lab that certification we it was very isolated that required three different cable matrixes.

<!-- image -->

**Reddy, Resha** 9:11
Mhm.

<!-- image -->

**Donaldson, Michael** 9:14
Mm.

<!-- image -->

**Reddy, Resha** 9:18
SIT environments, Yeah, yeah.

<!-- image -->

**Erickson, James** 9:20
And just using the same firewall and despair if I remember right, right?

<!-- image -->

**Reddy, Resha** 9:28
Yeah, that that's this is probably the most complex lab cert with them.

<!-- image -->

**Erickson, James** 9:32
Yeah, yeah. So I mean, that's what's helped us be able to kind of abstract and and test only specific VSNS rather than specific unique combinations of them.

<!-- image -->

**Reddy, Resha** 9:46
Yeah.

<!-- image -->

**Erickson, James** 9:48
But it does make the trade off as it gets a lot more complicated.

<!-- image -->

**Reddy, Resha** 9:52
It does, yeah. So you'll see, for example, between Gen. 25 and Gen. 27, we've had six lab certs.
But four of them were for Gen. 25.
Gen. 25.
And these are the different combinations, right?
But so for example, we had only one that had Broadsoft NSRS PIP, but we have specific nodes that are only NSRS PIP, but because that was covered in this lab cert.
It ended up working out best that we handle it this way. Otherwise, instead of having six, we could have probably had to have eight or nine lab certs if we did it specific to each combination.

<!-- image -->

**Kanumuru, Mohan** 10:33
So do do we have a a in in somewhere in the in the preparation or during the testing process or ultimate outcome?
Is there is any just for broadsoft for example and NSRS? So if there is we if broadsoft alone is there and NSR NSRS is alone is there or combination is there? Is there any overlap between them or are they completely autonomous?

<!-- image -->

**Reddy, Resha** 10:51
Mhm.
Mhm.
Mhm.
From a lab testing perspective or from a migration?

<!-- image -->

**Kanumuru, Mohan** 11:11
Yeah, but from the are in the service aspect, from the service, from the service point of view, are there any interdependence inter inter? If I have only one, will the configuration be one way and if I have both will the configuration will be other way?

<!-- image -->

**Reddy, Resha** 11:30
That's a good.

<!-- image -->

**Kanumuru, Mohan** 11:30
What changes?

<!-- image -->

**Erickson, James** 11:30
Like you're talking about with ice, ice, skip and say S pip 7:00 and 8:00.

<!-- image -->

**Kanumuru, Mohan** 11:37
Yeah, yes in the in the in this combination I think that's I think it coming from your point only if there are if there are only SPIP one only case and SPIP one and SPIP 7 case so.

<!-- image -->

**Reddy, Resha** 11:42
Yeah.

<!-- image -->

**Kanumuru, Mohan** 11:52
If I did test for SPIP one only and SPIP 7 only separately, and if we have happen to have a site where both of them are there, what would just to have a clear idea what will be the? Yeah, just thought of.

<!-- image -->

**Reddy, Resha** 12:01
I see what you're saying.
Can you pick and choose is basically what you're saying. Is it like an ad hoc? You add two things together and it doesn't matter how it's tested, it should work the same. That's your question.

<!-- image -->

**Kanumuru, Mohan** 12:09
Yeah.
At least, at least.
Yeah, at least, yeah. And at least in the analysis we have an idea. Are there any interdependencies? If will if both of them exist, do I need to tweak certain parameters differently?

<!-- image -->

**Reddy, Resha** 12:24
Mhm.

<!-- image -->

**Kanumuru, Mohan** 12:31
Is just a thought, yeah.

<!-- image -->

**Erickson, James** 12:33
Well, so in the lab that you know, we we generally have each sit environment usually matches a combination of of.

<!-- image -->

**Donaldson, Michael** 12:36
Um.

<!-- image -->

**Reddy, Resha** 12:47
Services, yeah.

<!-- image -->

**Erickson, James** 12:48
VSN services that exist in bulk out in production. What you don't see in production is like S PIP one and S PIP 7-8 specifically together on the same or I skip and S skip or D skip on the same.

<!-- image -->

**Reddy, Resha** 13:03
Mhm.

<!-- image -->

**Erickson, James** 13:06
I believe.

<!-- image -->

**Reddy, Resha** 13:09
No, they would never be the same.

<!-- image -->

**Erickson, James** 13:09
But.
Yeah. And and so, yeah, there.
We we have none of the sits in the lab have just one service on them, but they do. There is I skip we've had because we don't have any equipment to service it. We've had to float it between just that VSN and the parameters that belong to it and the IPS.

<!-- image -->

**Reddy, Resha** 13:23
Exactly.

<!-- image -->

**Erickson, James** 13:36
That belong to that environment between different sets for different labs or.

<!-- image -->

**Reddy, Resha** 13:44
But I think to answer your question, Mohan, no, I don't believe there are interdependencies between different services that would be a concern as we move forward. So for example, if on this list we have OCAS, which is lab cert 3.

<!-- image -->

**Erickson, James** 13:52
Mhm.
Yeah.

<!-- image -->

**Reddy, Resha** 14:02
And NSRS, but we've tested them separately on two different lab certs. And if we have OCAS and NSRS, for example, on one node, are there interdependencies that we would not have caught during lab cert? That's your question.

<!-- image -->

**Kanumuru, Mohan** 14:16
Right, right. And do we need to be concerned about it? Yep, that's exactly.

<!-- image -->

**Reddy, Resha** 14:19
No, I I don't believe so, no.

<!-- image -->

**Kanumuru, Mohan** 14:21
OK.

<!-- image -->

**Reddy, Resha** 14:28
And that's a lot of the consideration that's taken into what combination we put in each lab cert. So we actually determined that before the cell was even signed.
Determine how many lab certs and the only way we can determine the amount of lab certs is knowing what services, what combination. Are there any issues with different combinations? What SIT environment we would be using because some SIT environments don't have the right combinations and then.

<!-- image -->

**Kanumuru, Mohan** 14:37
OK.

<!-- image -->

**Reddy, Resha** 14:52
We come to that number of lab starts and that is a discussion between from like Mike and my side and from the technical side. It's not just determined by Mike and I or or sales.

<!-- image -->

**Kanumuru, Mohan** 15:05
Thank you. Thank you.

<!-- image -->

**Reddy, Resha** 15:07
Yep.
Any other questions on this part of it?
And just a quick note, there's the difference between ISIP and DSIP. ISIP is international, that's what the I is. DSIP is domestic, that's what the D is. The same service, just domestic and international.
Right.
OK, so once we get the, once we do the configuration review with Verizon, we get the approval to move ahead. At that point we have all the pieces that we need normally to move ahead with the lab cert, the pieces being an approved TREC.
An approved configuration and confirmation from Denver, whoever in the lab is handling it, that all the cabling and the equipment and everything is ready to go. Those are really the three pieces that we need to be able to move ahead.
Normally the lab setup takes the longest.
Right. And a lot of that is because sometimes cables are underneath the floor, sometimes they just don't have cables and we they need to order more and they're back ordered. Sometimes we find we need different equipment and we have to start looking to see if there's anything on site or do we need to buy equipment.
A lot of that is what comes into that whole lab prep, and that's why it takes so long.
I am going to has has everyone seen a cable matrix before?

<!-- image -->

**Kanumuru, Mohan** 16:46
No, Abidi didn't see it.

<!-- image -->

**Reddy, Resha** 16:47
OK, so I'm going to James, do you know where that would be held? The cable matrix?

<!-- image -->

**Erickson, James** 16:56
Well, for the labs, I don't think we've ever really archived them like that.

<!-- image -->

**Reddy, Resha** 17:01
Loaded it on here. OK, Yeah. No, that's what I was wondering. I don't think they're on here. You're right, I think.

<!-- image -->

**Erickson, James** 17:07
Not on the Google, they'd be on the teams OneDrive share for our.
Um.

<!-- image -->

**Reddy, Resha** 17:18
Actually, I don't think that's true. I think they are in here because I remember we had to the port assignment right here. So we used to what we work with Verizon on is the port mapping and the port assignment from the port assignment. We then take that and turn that into a cable matrix.

<!-- image -->

**Erickson, James** 17:18
There might be one under there.

<!-- image -->

**Reddy, Resha** 17:38
That sound about right?

<!-- image -->

**Erickson, James** 17:40
Yeah, I mean, and then we have to identify from the old routers all the servers and devices that are connected to it and add those in.

<!-- image -->

**Reddy, Resha** 17:49
Mhm.
Yeah.

<!-- image -->

**Erickson, James** 17:55
So that's that should be the.
The same doc right that you're talking about when the port assignments.

<!-- image -->

**Reddy, Resha** 18:03
This is, yeah, this is the port mapping. This should have the from and to Yep. So since this is a source device for example.

<!-- image -->

**Erickson, James** 18:08
Yeah, OK. Yeah, yeah, yeah.

<!-- image -->

**Reddy, Resha** 18:12
The rack.

<!-- image -->

**Erickson, James** 18:15
Yeah, and this.

<!-- image -->

**Reddy, Resha** 18:15
All the interface details and then this is all the destination.
So if you'll notice this description, that's what we rely on a lot to figure out what certain connections are for, what they're used for.
And sometimes it's so generic we have absolutely no idea what they're talking about.

<!-- image -->

**Erickson, James** 18:37
Yeah. And if we don't update these in the lab at the same time we're doing the migration and certification, we've lost an opportunity. We need to do it and we'll get called out by Travis if if we don't.

<!-- image -->

**Reddy, Resha** 18:49
Mhm.
Yep, absolutely. But you can see like this is a Sonus. This is the GeoProbe. I saw Brix in here somewhere, right there Brix. So they're for the most part they have the information that we need, but there's always at least a few that.

<!-- image -->

**Erickson, James** 18:53
4.

<!-- image -->

**Reddy, Resha** 19:12
We're not really sure what they're used for and we have to go back to Verizon.
That's what that's what ends up taking time along with the actual cabling in the lab. So like for this one, there's, yeah, we we this was actually over 200 originally.

<!-- image -->

**Erickson, James** 19:34
Yeah, and and at times this takes like actually working and and part of Denver's team was all contractors either going from between this site or one of the other sites, but sometimes trying to coordinate with them.

<!-- image -->

**Reddy, Resha** 19:43
Mhm.

<!-- image -->

**Erickson, James** 19:51
To get those cables run and or rerun or adjusted, just try to be as complete on this as you can with.

<!-- image -->

**Reddy, Resha** 19:56
Yeah.

<!-- image -->

**Donaldson, Michael** 20:02
Mm.

<!-- image -->

**Reddy, Resha** 20:02
Exactly.

<!-- image -->

**Erickson, James** 20:05
So we don't have to come back and revisit it.

<!-- image -->

**Reddy, Resha** 20:09
Yeah, the more we have to ask Verizon for details, the longer it'll take. There have been a couple of times in the past where we've actually had to go down the road of just unplugging it and see who complains.

<!-- image -->

**Erickson, James** 20:15
Mhm.
Yeah.

<!-- image -->

**Reddy, Resha** 20:24
Because no one, no one could answer the question as to what it was used for, but that's only happened a couple of times I think. So normally this is what we use to start off with. The cable matrix is created off of this. That's what's loaded, what's loaded into JIRA.

<!-- image -->

**Erickson, James** 20:29
Mhm.
Mhm.

<!-- image -->

**Reddy, Resha** 20:44
All right. So then let's say we start the lab cert. So we work through the lab cert. Lab cert is normally a layer one and a baseline. So layer one meaning all the cabling, making sure we can actually, you know, all the cables can move back and forth, everything comes up properly and then the baseline.
We try to use ITP. That's a system they use for baseline, but not everything has a test case in ITP. So we normally check there first to check with the ME team to see if there are cases or tests that we just don't have access to. And then I, for example for Titan, there are no tests in ITP.
Then we use a laptop and then we just test to make sure everything looks good from the laptop standpoint because there's no other way to test it. So it's a very manual process.
And then once we've gotten through those two, then we start the actual testing per the test requirements and let me see if I can bring one of those up.
So like I say, that usually follows a specific template, so we usually take previous templates and just change it up. Gives us a good reference point of what tests were previously done as well. So different different sections. So there's mock testing layer 2.
Layer 3 design specific VSN security.
TACACS fit and then failover SNMP. So there there's a lot that we test. We want to be as thorough as possible without overdoing it, right? And that's why we refer to previous test requirements to see what would apply and what would not.
And we go down and confirm exactly what we're testing, whether it's past any specific details once we do the actual testing. So this is what we normally go through and what you'll see and you'll work on as you're doing a test or a lab certification.
Because you want to make sure you're giving them specific details as to what you've seen when you're testing.
And if there is a failure for any reason, if something doesn't work, then we come back internally and say, OK, this didn't work, why didn't it work? Is there something that we're missing? Is there a a config change that needs to be made or such?
And then once we have this, many times what we do, dependent on how intricate it is or what issues we've had, we review it internally just to make sure that there aren't any specific questions we think Verizon will ask because we want to catch those and test for them before we go through this with Verizon.
So that's all part of this lab certification. So to get out of lab certification, we then go and once that test requirement list is complete, we do what's called the TER Test Exit Report and that is basically review of that whole test plan with all the pass fails and the details.
As well as a MOP review, because as you're doing the testing in the lab for the certification, you are also updating the MOP to ensure that, OK, I've tested all of this. This is how I know we should be able to go forward because it's been tested.
Does that make sense? Yeah.

<!-- image -->

**Donaldson, Michael** 24:13
There is, yeah, I sent you a file. It's not gonna have I think exactly what you want, but if you open that and go to slide five, it has the true what what Verizon used to call their true gates, gate zero through 4. It might help just to see it because it has what the deliverables are in each one of those gates.

<!-- image -->

**Reddy, Resha** 24:21
An e-mail.
OK, OK.
Please.
Yes.
Yes. Oh, where did you send it?

<!-- image -->

**Donaldson, Michael** 24:33
Basically.
It's in your it's in your teams. You're not getting it. Oh, helps if I do this.
Now you should have.

<!-- image -->

**Reddy, Resha** 24:44
Perfect. Thank you.
On.

<!-- image -->

**Donaldson, Michael** 24:58
And then go to slide five, I think might help.

<!-- image -->

**Reddy, Resha** 25:04
Yeah, I had. I had a version of this too, so this is perfect. Yep. So LLD test requirements, proof of concept. That's not really.

<!-- image -->

**Donaldson, Michael** 25:08
OK.

<!-- image -->

**Reddy, Resha** 25:15
I don't think we do do that at all anymore and a security design review, but that's all done.

<!-- image -->

**Donaldson, Michael** 25:19
No, I think they do a lot of that as part of their LLD development, yeah.

<!-- image -->

**Reddy, Resha** 25:21
Exactly. So this is what we were talking about the test plan, which is a test requirements, a TREC, the TER delivery. So that's really the actual this in this kind of go hand in hand the lab certification and the TER delivery is the review of that the results of that lab.
Lab certification. The MOP development is what we review. So these two are reviewed to these two are reviewed together, the TR and the MOP, because what we want is their approval that the generic MOP for that design looks good and if it does look good.
Then we know we can use it to create the site specific MOPs.
Right. And then the golden config comes from the config that we use that we've reviewed with them before we started the lab cert, and we tweak that as we go along if there are any issues.
Alright, any questions on the lab cert? There is one thing I am going to go to if I can remember where it is.
No, it's in open items.

<!-- image -->

**Czirjak, Gery** 26:31
He didn't mention the Nessus thing. I don't know if that's wrong.

<!-- image -->

**Reddy, Resha** 26:34
Oh, that's right. The Nessus security scan. Yeah, that's that's also part of that finishing up the lab, certain part of the actual test requirements.

<!-- image -->

**Donaldson, Michael** 26:37
Hmm, yeah.
Yeah, that's a must as part of the.

<!-- image -->

**Reddy, Resha** 26:47
Oh.

<!-- image -->

**Donaldson, Michael** 26:48
Do we do we list that as a check off in our TER like an item check off to me just so that we don't close the TER and forget it?

<!-- image -->

**Reddy, Resha** 26:56
I don't think so.

<!-- image -->

**Donaldson, Michael** 26:58
I'm wondering if we should, you know what I mean, just as a final, so at least it's in there.

<!-- image -->

**Reddy, Resha** 27:01
Mhm.

<!-- image -->

**Donaldson, Michael** 27:05
As a reminder.

<!-- image -->

**Reddy, Resha** 27:05
No, no, I don't look. Doesn't look like we have it in here.

<!-- image -->

**Czirjak, Gery** 27:09
No, I don't think it is.

<!-- image -->

**Reddy, Resha** 27:11
Mhm.
We haven't talked about it in a while, so that's probably a good question to bring up with the with Nick and Derek.

<!-- image -->

**Donaldson, Michael** 27:21
Whether we did them in the last few lab search me, Travis usually runs out.

<!-- image -->

**Reddy, Resha** 27:24
Mm-hmm. Yep.
Yes.

<!-- image -->

**Donaldson, Michael** 27:29
Don't know if he still is or not, but he's usually the one that runs those scans.

<!-- image -->

**Reddy, Resha** 27:35
All right, I have a note to check. OK, going back here. So what we've done is this matrix that we have, we have this for route switch and DPC. So this is the one for a route switch that we've done. You'll notice that there are different designs here on the left.
And then we had some regression testing that we had to do for Junos, but the LLD, so IPCME like we talked about when they have actually completed it and done their review. So this is more on them than on us. You'll see Scott Hiller's name in here a few times.
The TREC, so that is us creating it and reviewing it with IPCME and these are the dates and whether we've got an approval creation of the mop that goes in line with the TER. Now once for the TER because it is a combination of the lab certification, we have to do a review with IPCME which is that small.
Team Liana, John, Travis and Scott. But then we also have to do a CFT TER with a much larger team, so anyone who would support it in any way possible. So usually OPS, app OPS, you know, T6, those teams once we have that review done.
Then we can move ahead with actually the actual migrations, the site-specific migrations. Those are really that's the gate to complete lab certification is this right here.
Now there are additional documents that we also create. So we've talked about a device configuration. Well, we call it a MOP, but it's really just a config the router switch migration MOP. So that's our site, our generic for the site specific. We also have a decommissioning mop, so we have that that we don't really update as much.
We might tweak it. It's really these two that may be updated, the behavioral differences and the provisioning guidelines.
So that is really dependent on what changes are being made and where they're being made, and that's usually outlined in this out whether we need to update these or not.

<!-- image -->

**Kanumuru, Mohan** 29:39
Could you elaborate on the behavioral difference part and provisioning guidelines? Is that with the comes back to MOP and the config generation?

<!-- image -->

**Reddy, Resha** 29:44
Yeah.
No. So behavioral differences is device specific.
And Mike, you might have to go into a little bit more detail here. I believe this is device specific and I can find them so I can show you where they are.

<!-- image -->

**Donaldson, Michael** 30:02
What is the question? Sorry, I missed it.

<!-- image -->

**Reddy, Resha** 30:04
Behavioral differences. What is it used for versus provisioning guidelines?

<!-- image -->

**Donaldson, Michael** 30:09
Behavioral differences is really like between releases, if there's anything that is significant for them to know in OPS like command, you know level changes or operational level changes in the product itself. So they basically want to know like like we had to do one from a Cisco to to one of our switches which.

<!-- image -->

**Reddy, Resha** 30:09
Yes.

<!-- image -->

**Donaldson, Michael** 30:28
Which is significant, but you're basically giving him the.
The I don't know if it's CLI level, but basically CLI level differences in how our commands operate versus a Cisco switch. You know that's an example or like from the MX960s release 14 that was their latest one that was out there all the way to where we're where we are now. What are the behavioural differences?
In the code, basically the command operation.

<!-- image -->

**Kanumuru, Mohan** 30:55
OK. I think that. Thank you. That's helpful. I think what I can compare to is the port mirroring. I think, yeah, James clarified to me that in Cisco they do both ingress and egress. It looks like we can only do ingress.

<!-- image -->

**Donaldson, Michael** 31:06
Right. That's a good example. Yeah.

<!-- image -->

**Kanumuru, Mohan** 31:12
Um.
Or I think one we can only do ingress for VLANS. So such such behavioral difference and if so, OK, got you. Thank you.

<!-- image -->

**Reddy, Resha** 31:16
S.

<!-- image -->

**Erickson, James** 31:20
Yeah.

<!-- image -->

**Donaldson, Michael** 31:20
Right.

<!-- image -->

**Erickson, James** 31:24
Well.

<!-- image -->

**Donaldson, Michael** 31:24
Mhm.

<!-- image -->

**Erickson, James** 31:25
Yeah.

<!-- image -->

**Kanumuru, Mohan** 31:26
And also maybe from the if we are jumping, if we are changing the Junos versions, I think then maybe some of those comes what what changed from before to now. OK, that makes sense.

<!-- image -->

**Reddy, Resha** 31:34
Mhm.
I don't think we've ever done one for Junos version change.

<!-- image -->

**Donaldson, Michael** 31:43
I think we did for the MX 960, right? Because they're they had such old code out there. I'm pretty sure Nick created one for those, yeah.

<!-- image -->

**Reddy, Resha** 31:49
Oh, I see. Yes. Yeah, I see. I see what you're saying. Yep.
Yeah, but there I I put the link in the chat if you wanna if anyone wants to go check it out. Both the provisioning guidelines, the different versions and the behavioral differences are in here.

<!-- image -->

**Donaldson, Michael** 32:04
Um.

<!-- image -->

**Reddy, Resha** 32:08
Alright, let me just check DPC because I feel like.

<!-- image -->

**Kanumuru, Mohan** 32:10
All this comes from the lab lab exercise, right? All this everything comes out of the our.

<!-- image -->

**Reddy, Resha** 32:16
It should, yeah. For the most part, it's really the configuration and the migration, the generic migration MOP that really comes out of that. But you'll see for DPC, there's also like a VSN build MOP. There was a line card replacement MOP. There was a routing engine replacement MOP. And don't laugh, Gary.
Um, there were certain.

<!-- image -->

**Donaldson, Michael** 32:34
Those aren't really, those aren't really TER related exit criteria. They're documentation deliverables where we had to create a MOP and test it, but it's not really part of a true lab cert, if that makes sense.

<!-- image -->

**Reddy, Resha** 32:39
Parents.
Yeah.
Exactly.

<!-- image -->

**Donaldson, Michael** 32:48
Those are operational mops that we create. They're MOPs that we create for operations for future maintenance kind of thing.

<!-- image -->

**Reddy, Resha** 32:53
And the reason we tie it to a lab cert is only because from a SA perspective it's tied to that milestone and it's generic, it is not site specific. So usually when we're seeing things from a technical perspective that are generic, it's lab cert related.
That's why we kind of club it in that way, if that makes sense.

<!-- image -->

**Donaldson, Michael** 33:13
Right.

<!-- image -->

**Reddy, Resha** 33:18
Does that help?

<!-- image -->

**Kanumuru, Mohan** 33:19
Yes, thank you.

<!-- image -->

**Reddy, Resha** 33:21
OK, oh and this. These are all the notes I had from when I went over this with TJ.
All right. So that takes care of all the lab cert. That's what we keep track of in here for the most part. And you can see we're not very good at updating this. Eventually we'll do it in December, probably later. So once we get through that, then we go through as that's going on, actually as that's going.

<!-- image -->

**Donaldson, Michael** 33:37
Mhm.

<!-- image -->

**Reddy, Resha** 33:47
Going on in tandem the VVE team, which is voice and video equipment, I believe voice and video engineering. I mean that team who reports into Shervin that team and.
Scott Stroud and Rob Lebou report into Matt Trostel. Scott Stroud creates the CCRs or the NFIDs, and that's what we keep track of in this sheet. It is basically their plan of record of here's what the design says needs to be done. Here's how it needs to be.
Applied to this specific node, here are the specific connections, the PO that you get the equipment from all of that. Now go off and do it.
Right. That's really the start of that process. There are a lot of steps in that process. So I'm gonna go back here because I did note this out for TJ. So the request is created. So we we tell Scott, hey, can you start the CCR for these five sites for example?
So Scott will normally get together with James and Gary or whoever else needs to be involved that's been involved in the lab cert and they start going through the details specific to that node and how things translate from the generic to the site specific. He then creates a CCR or an NFID that's that's the same thing.
Once that's created, then the VVE team gets that and they then run with it. Then when they say they run with it, they're basically project managing that process until install, right? They assign what's called a center engineer and a design engineer. A center engineer is who.
Who Mike and I talked to. That's like the Araceli, the Chuck.
The Ronald, who's not here anymore, those are the people that we normally talk to. They're like the PM of that process. The design engineer is a person who is like the Fred or the Lindsey who works in much more detail, technical detail to get through the specifics and they'll put the requests in for the different parts.
So they work on different things. So they'll put normally the process is, and I'm just going to walk through this really quickly. They get assigned, they put a request in to check the power and the HVAC.
And to check the telemetry, it's two separate requests and reason that they do that first is they want to make sure from a capacity, power, cooling, all of that, that they actually have the space and the capacity to.
Add these devices in because right off the bat, if that's not a possibility, we get delayed, right? Once we get the confirmation, yeah, everything came back, it looks good. They do, you know, a site survey to get all that information, then we do.
They they do a site survey, a separate site survey to get into the specific details from a cabling standpoint. It's kind of the Verizon version of our cable matrix, how we do it for the lab. That's their version of it for production for the site.
So they create or they gather all the details of what's currently in place on site and then they hand that off to the VVE team. The VVE team then turns around and the design engineer takes that information and turns it into an I spec.
And the I spec is what we've seen before. You guys have been on those review calls and you had that call earlier this week. That I spec is what we then base our cut sheet off of, but it gives us the specifics not only of all the cable runs but of how many.
SFPs are coming in. What you know, how many devices are they ordering from what PO? Because we've found a few times that we do have to validate that information. What we've also found is that if we review the I spec with the design engineer before they even start the install.
There's usually things that we catch before install is done that makes next steps much easier. So that's why we've implemented that. We we never used to do that. I think we started that last year and our layer one used to take a long time.
But I think it's helped a lot doing the I spec review before they start the install because there are many things that we catch. I don't think there's been a single I spec review that has been, yeah, this is great, no issue whatsoever.

<!-- image -->

**Erickson, James** 38:20
Yeah. So yesterday, when we were talking about the CCR, the the PRF, and the the I spec, I didn't go into any great detail on the VVE teams.

<!-- image -->

**Reddy, Resha** 38:36
Um.

<!-- image -->

**Erickson, James** 38:37
Role in it. So yeah, thank you for for presenting that and this that is a key part to that all our part, you know I highlighted our parts in that once we handed off in the CCR.

<!-- image -->

**Reddy, Resha** 38:39
OK.
Yeah.

<!-- image -->

**Erickson, James** 38:52
And the center engineer is assigned and um.

<!-- image -->

**Reddy, Resha** 38:57
Mhm.

<!-- image -->

**Erickson, James** 38:59
That VVE team gets involved. They they have their own engineering resources. They have master I specs that they base off of. They should be in a lot of ways.

<!-- image -->

**Reddy, Resha** 39:07
Yes.

<!-- image -->

**Erickson, James** 39:18
The the detail, you know, you know that's their domain, right? The the all the little little nitpicky details, the the actual engineering that goes on there, you know?

<!-- image -->

**Reddy, Resha** 39:25
Yep, absolutely.

<!-- image -->

**Erickson, James** 39:33
Um is.

<!-- image -->

**Reddy, Resha** 39:33
Mhm.

<!-- image -->

**Erickson, James** 39:37
Is it's like a black box for us a little bit, you know, we don't see what.

<!-- image -->

**Reddy, Resha** 39:39
A little bit, yeah. And that's why I wanted to. That's one of the reasons I wanted to have this conversation because.

<!-- image -->

**Donaldson, Michael** 39:43
Yes.
You just you you just maybe. Sorry, go ahead. I didn't mean to interrupt.

<!-- image -->

**Erickson, James** 39:45
Yeah.

<!-- image -->

**Reddy, Resha** 39:49
No, I was just saying that's one of the reasons why I wanted to have this conversation because it is kind of a black box for them.

<!-- image -->

**Erickson, James** 40:05
Mhm.

<!-- image -->

**Reddy, Resha** 40:10
Oh yeah.

<!-- image -->

**Donaldson, Michael** 40:10
Goes through document our product and and where the cards are placed and how the labeling is logical versus, you know, physical, those kind of import assignments, all that. Do you remember, do you guys remember what that's called?

<!-- image -->

**Reddy, Resha** 40:10
Oh yeah.

<!-- image -->

**Erickson, James** 40:15
Mhm.
Yeah.

<!-- image -->

**Reddy, Resha** 40:21
Mhm.

<!-- image -->

**Donaldson, Michael** 40:28
Master product document or something like that.
It's they develop it so that those their teams can do the I specs, right? And I'm wondering, do they need them for the MPC sevens? I know the MX 960 already has a document, but I'm wondering if it needs to be updated because these new MPC7 cards are coming out.

<!-- image -->

**Reddy, Resha** 40:33
So.
Yeah, I I forgot what that's called.
Oh.

<!-- image -->

**Donaldson, Michael** 40:48
That's what made me think about it, but we can talk about that later offline.

<!-- image -->

**Czirjak, Gery** 40:49
It was done.
It was done, Mike.

<!-- image -->

**Donaldson, Michael** 40:55
Say that at the beginning, Gary? Oh, okay. Well then, very good. I don't need to worry about it.

<!-- image -->

**Czirjak, Gery** 40:57
I said it was done.

<!-- image -->

**Donaldson, Michael** 41:03
I'll go back to sleep. Go back to work.

<!-- image -->

**Reddy, Resha** 41:04
OK.
All right, so if I'm glad I have this because you'll see everything in here in blue is what I'm talking about right now.

<!-- image -->

**Erickson, James** 41:08
This.

<!-- image -->

**Reddy, Resha** 41:14
So the CCR creation, the PEC is the site survey. I can't remember what PEC stands for exactly, but that's the site survey. So, but there's steps in here that are even more intricate than this. So we have to request the CCR, then Scott Strat submits the CCR.
Then once they assign people, then they request the Peck. Then the Peck is done. Then they wait for the results of the Peck to be sent to them. Then they can use that for the I spec creations. Then they create the I spec. They review it internally.
Then they review it with us and then they order the materials. So they put the request in for their materials. The materials are then shipped out. Then they have to put a request in to receive the materials.
Which includes making sure that what they requested is what was actually sent. Then they can put a request in to say, OK, now whoever's going to do the install, whether it's Blue Ally or OPS, please schedule the install to be done.
And sometimes by the time they get to that point. So for example, I think it was NORSN one we found out today that they are not going to start the install until the 12th.
Because they just put the request in and they just heard back that from a scheduling standpoint, they don't have anyone available to do it until the 12th, right? So I've asked before if some of this work can be done concurrently and that it can't, it has to be done serially.
So they can't, for example, say, hey, ship everything to site and I'm going to put a request in to install at the same time because they can't. What if for some reason the material sent is not all the material that's needed? Then it causes an issue. So they have to do everything step by step.
And then once the install starts, the one thing that we have noticed is.
Depending on who's doing the install, if it's OPS, Verizon OPS doing the install, it will take at least a month for that install to be complete. If Blue Ally is doing the install because they're contracted, it will take maybe 2 weeks.
From start to finish, so it really depends. And OPS also gets pulled off of installs for other priority items. That's one of the reasons that you'll notice that all the installs, if you've heard on our DPC calls, are being done by Blue Alloy. They're not being done by OPS anymore.
Because it was taking too long. So a lot of pressure that Mike and I used to get earlier in the year was how can we compress this process? How can we get ice specs sooner? How can we start install sooner? And there's no way to do it.
There really isn't. It has to be done step by step. It's all based on how many resources you have and what other priorities they have going on, so.
And we'll talk about this later, but there are things we found out on the CCR call that have some major impacts to our schedule next year.
So coming back to this process, once the site install is complete and once we get confirmation from the center engineer that the site install is complete, they actually then have one additional validation step that's done by Rob Lebu.
He just validates that everything is set up the way it needs to be from a access standpoint. And then once he does a validation, he's the one that actually sends the confirmation to us to say, OK, this site is ready now for layer one.
And then we can move ahead with our layer 1 validation. And a lot of times that will be, you know, we've had times where that's taken one week, everything looks good, no problem. And then we've had times where that's taken three months.
Because, you know, a cable wasn't plugged in properly and or something's wrong with the cable and we have to replace it or there could be many reasons.

<!-- image -->

**Erickson, James** 45:13
Yeah.

<!-- image -->

**Reddy, Resha** 45:15
But at minimum, yeah, but at minimum, we assume that a layer one will take two weeks.

<!-- image -->

**Erickson, James** 45:15
There's lots of those.

<!-- image -->

**Reddy, Resha** 45:23
Now as part of the layer one, and Gary's gonna go over this at another time, we used to do IT assurance separately, but we're now kind of clubbing it in along with, hey, layer one's mostly complete, I can move ahead with, you know, certain.
Layer IT assurance items. So we just do it right away because there's no need to wait for some of those items.
All right, I'm gonna stop here. So this is this whole blue process is the VVE process.
Any questions on that?

<!-- image -->

**Kanumuru, Mohan** 45:58
The IT students is TACAC, syslog, SNMP, et cetera.

<!-- image -->

**Reddy, Resha** 46:03
Yes, smarts SNMP needs the I skip all of that. Mm-hmm.

<!-- image -->

**Kanumuru, Mohan** 46:07
DNS OK.

<!-- image -->

**Reddy, Resha** 46:13
Yeah. So once we finish up our layer one, I'm gonna go back here, see if it's in here. I'll have to check. We then start depending on when, obviously, depending on when the migration is, there's certain things we can't do and certain things we can't do.
Right. IT assurance is something we can always move ahead with. Once layer one is complete, we can always move ahead with a mop.
Um, a cut sheet.
But we can't do config conversion because you want to do that as close to migration as possible so that you don't have to do too much of a delta afterwards.
Right. So there's that's all like the pre-migration verification and readiness. That's all that stuff that we talk about from a site, that site checklist or the planning list is is the mop done, is the the cut sheet done?
We have to review the mop with Verizon for every single site specific mop and get their approval before we can move ahead. That was a new thing that was introduced.
I feel like saying end of 23. Is it end of 23? Yeah, I think it was end of 23. Every mop now has to be approved. So we usually record it, confirm approvals, all of that and that's usually in our.

<!-- image -->

**Donaldson, Michael** 47:25
Probably.

<!-- image -->

**Reddy, Resha** 47:39
Where our schedule is this first tab, we keep track of all the mops and all the different approvals depending on what it's for.
So once we get the approval, then we have a go, no go call. That's usually the afternoon right before the migration. We also the week before send out health checks for geoprobe, utility and bricks. I have those set up automated. Depending on what kind of site it is, they'll come back.
And say you know we don't have a utility server and I keep track of that because we do send out post checks after every single migration window. So once I get a success e-mail I then prompt tool that I use to send out post checks to the same people.
So utility goes to James Rader, Geoprobe goes to Paul Holm and Venkat, and Bricks goes to Teresa.
So and we don't usually we need confirmation that everything looks good or if there's an issue, how we're going to resolve it before we move ahead with the next maintenance window. And we do that after every single maintenance window. So if we have 5 maintenance windows, I send five different sets of post checks out after each one.
And then once that's done, do I have it in here? Then after once we finish migration, then we have our post post checks like I talked about and then a soak period. So normally during the soak period we do if there's needed, if there's PIP, we do the IT database.
Update requests which I send out to the IT team and then a week later once we confirm that all the IT database changes have been made, we then release the freeze and do a hand off for that site to operations to say look our soak is over.
We are no longer like every all of our work on this note is complete. We're gonna hand off to you because now anything that comes up is from an operation standpoint to be handled.
Alright, I'm gonna stop there. Mike, is there anything else you want to add in?

<!-- image -->

**Donaldson, Michael** 49:57
Can you go back to that timeline just for a second? You might have mentioned this, but I had to step away for a second. The third one, yeah.

<!-- image -->

**Reddy, Resha** 50:02
This one or this one?
Yeah.

<!-- image -->

**Donaldson, Michael** 50:05
So you probably addressed this, but anywhere where it says mass stars.

<!-- image -->

**Reddy, Resha** 50:08
Mm.
Yeah, this one's old.
Sh.

<!-- image -->

**Donaldson, Michael** 50:16
That's where you would, you know, start the whole process for scheduling Kirks, et cetera. Then we do it a little bit different now. This was this timeline was created when we first started having to develop processes with Verizon on how Juniper needs to work with them from a PS perspective and follow all their gates, et cetera.

<!-- image -->

**Reddy, Resha** 50:33
Mhm.

<!-- image -->

**Donaldson, Michael** 50:34
That's why you see some of the older naming conventions in there.

<!-- image -->

**Reddy, Resha** 50:36
Yeah. So, so that's a good point. I didn't talk about Kirk, so we try to get our Kirks in.
At least a month or two before all of these Kirks, any migration related activity, the Kirk is seen as a service affecting Kirk and service affecting Kirks have an SLA of 12 days, which means we have to enter the Kirk 12 days before the actual migration date.
Like I said, we normally try to do it a month or two in advance, just because it's a lot of work when you're talking about DPC specifically because of the amount of windows, and for each window we have to create two separate plans it can take.
Four to five hours at least to create all of the Kirks. So we create them a month or two in advance, but we try not to get too far ahead because as we all know, there is constant change to the schedule.

<!-- image -->

**Donaldson, Michael** 51:32
Huh.
That never happens.

<!-- image -->

**Reddy, Resha** 51:35
Never happens. So for example, TJ and I were talking about TJ's working on creating TSSN one for now. Once that's done, we probably will only go up to HSJSN one until we hit January and then we'll stop. We will only create these two in December and then we'll wait until January starts.
And then we'll move ahead with the next month or the next two months worth. We're only doing them a month or two in advance right now. I used to do them all like each quarters 1/4 before, but then there the issue is if we change, I have to go to every single request to change the date.
And that changes for every. So it'll take hours to do all of that, and it's unnecessary. We know things are going to change at this point, so we only do a few at a time. But when we create the Kirks, all of the Kirks go into a pending approval status.
And then we have to go back in to check if they were approved. If they're not approved, depending on whether it's a firewall Kirk or a network Kirk, we have to go to that team to just remind them that there's something out there for them to approve and if they don't approve it, we can't migrate.
Once we get the approvals, you guys, of course you start the Kirks, you complete the Kirks. But we keep track of everything. All of our Kirks are kept track of and we this goes back years now. We keep track of all of our Kirks. We keep track of all the completed Kirks. You'll see this goes back to 2022, every single one.
We've kept track of just to make sure that we know what and we've actually come back to this and gone back to close Kirks from 2-3 years ago to to check on something that's come up.
So we keep track of everything. This is what I take screenshots of and put into each of the invites. You'll notice we actually have specific address details in here. This was requested because of a question that had come up a few times from the firewall team because of overlapping maintenance work.
And they weren't sure exactly what location we were doing the work in. So that's why we've added that in.
But there's a lot of effort and prep that goes into creating these Kirks as TJ is now having fun with.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 53:48
But you said a few hours has taken me just a few days, so.

<!-- image -->

**Reddy, Resha** 53:51
I know when you when you're doing it normally, it still takes you at least half a day.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 53:57
Yeah, for me it's a little bit longer right now, but getting there.

<!-- image -->

**Reddy, Resha** 53:59
Yeah, Yep.
All right, I think. What was that?

<!-- image -->

**Czirjak, Gery** 54:04
Do you not like TJ Rish? Do you not like TJ or something?

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 54:04
Hey, Rachel.

<!-- image -->

**Reddy, Resha** 54:12
Child by fire, man.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 54:12
I'm in the fire. Hey, Rachel, I just got a quick question too. Like on that one sheet where you had the completed Kirks and you said you had to go back, you know, a couple of years and look at what is there like a?

<!-- image -->

**Reddy, Resha** 54:17
Yeah.
Oh.
Mhm.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 54:28
Is there a sign off when a Kirk is completed or is it just a system sign off, meaning once it's complete, that's the assumption that Verizon signed off that it was completed as you know, per specs?

<!-- image -->

**Reddy, Resha** 54:29
Yes.
Oh, that's a good question. So and I'm I'm sure Gary or James can probably step into this, but basically what happens is once all the Kirks are approved, our our job from a PM standpoint ends right when Gary or James or whoever else is handling A maintenance window starts their maintenance window.
They do all of their pre-checks and when it hits midnight they actually go into Kirk and they'll they'll it'll have a button to say start Kirk because it's at that point where they can now start the Kirk. They're in that window, they start the Kirk and once they're done with everything they have to do.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 55:07
Yeah.

<!-- image -->

**Reddy, Resha** 55:11
I think it's close or is it end something like that?
They close out each of the Kirk. Yeah, so they close out each of the Kirks.

<!-- image -->

**Czirjak, Gery** 55:16
close complete.

<!-- image -->

**Donaldson, Michael** 55:16
Completed.
Right. And that's for each individual request. So like you can see some of those examples that Ratia is showing has multiple Kirk request numbers, right. So they have to start each request in for that maintenance window and they have to close them before the maintenance window ends. There's reports that go to the.

<!-- image -->

**Reddy, Resha** 55:22
Yes.

<!-- image -->

**Donaldson, Michael** 55:38
The managers that own that equipment. So in that approval process for Kirk, there are certain managers that are pro that you know the the approval flow flows to and if we don't complete or you know something is incomplete or it's not marked as complete, they the managers get a flag and so then they'll e-mail us and say what happened.

<!-- image -->

**Reddy, Resha** 55:49
Oh.

<!-- image -->

**Donaldson, Michael** 55:58
Happened, right? So. So we definitely need to be cognitive of that. It's not a it's not something we can skip. So we just have to remember to do that at the close of every maintenance window.

<!-- image -->

**Reddy, Resha** 56:09
Well, and here's my question. I don't think I've ever asked this. Does it auto close at the end of the maintenance window or do you have to close it like if you go past 6:00 AM local time?

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 56:09
OK.

<!-- image -->

**Donaldson, Michael** 56:20
No, I don't think it auto loaded.

<!-- image -->

**Reddy, Resha** 56:21
Does it auto close?

<!-- image -->

**Czirjak, Gery** 56:23
Yeah, I'm pretty sure it does. Auto close cause Scott told me. Scott Mills once told me that it does and I've had it accidentally do it to me when I had the wrong date the other day, remember for Sydney. But that doesn't change the the comment that Mike made that we do close it when we're done.

<!-- image -->

**Reddy, Resha** 56:24
System.
That's what I thought.
Yeah, Yep.

<!-- image -->

**Donaldson, Michael** 56:34
Hmm. OK.

<!-- image -->

**Reddy, Resha** 56:41
Yeah, yeah, yeah.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 56:41
Yeah.

<!-- image -->

**Reddy, Resha** 56:42
Maybe what you're talking about, Mike, is they'll get a notification if something was auto closed versus manually closed. Yeah.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 56:45
And.

<!-- image -->

**Donaldson, Michael** 56:46
That must be. It must have changed because I know I haven't hit that issue in quite some time, right? But because it reached out to me a couple times on it, but that was the last time was probably almost three years ago.

<!-- image -->

**Reddy, Resha** 56:52
Mm.
Yeah.
Yeah.

<!-- image -->

**Czirjak, Gery** 57:01
We used to forget to do it sometimes.

<!-- image -->

**Reddy, Resha** 57:03
You're you're admitting that on the recording, Gary. Too late.

<!-- image -->

**Czirjak, Gery** 57:11
Oops, I meant we thought we might have.

<!-- image -->

**Kanumuru, Mohan** 57:16
I'm curious if if we, I mean if it auto closes then if we in fact.
The maintenance prolonged. What happens then?

<!-- image -->

**Reddy, Resha** 57:29
You have so that that I was gonna go there next. So yeah, if for some reason you think you're going to go past the maintenance window end time, that's a huge red flag. We I think that's maybe only happened once or twice in the last few years that I've been with Verizon. But we if we think we're going to go over, we have to contact.
Oh my God, what's the team?

<!-- image -->

**Donaldson, Michael** 57:54
It's the the the you have to call knock first, right? And then they'll escalate up. But you don't ever want to do that because that's gets us a huge escalation like that's the whole reason for you. I don't know how much you guys have been stressed this the the newer members of the team, but.

<!-- image -->

**Reddy, Resha** 57:56
Yes, thank you.

<!-- image -->

**Donaldson, Michael** 58:10
You know you you've probably heard Greg say this right is we you know when we do these strategy reviews of how we're going to migrate and what the maintenance window is going to look like when we do those reviews with Verizon to kind of estimate what we think a maintenance window is going to be. You'll hear Greg stress a lot of times that OK, well, so what's your time cut off for deciding whether to roll back or not.

<!-- image -->

**Reddy, Resha** 58:28
Mhm.

<!-- image -->

**Donaldson, Michael** 58:29
Right. So we always have to be aware of where we are in the maintenance window because we don't have enough time to back out and then we're putting ourselves in jeopardy of going over and that's a big red flag on Juniper that goes all the way up to executive level. They don't, they do not approve any ever approve going over the 6:00 PM cut off 6:00 AM.

<!-- image -->

**Reddy, Resha** 58:44
Right.

<!-- image -->

**Donaldson, Michael** 58:49
Cut off.

<!-- image -->

**Kanumuru, Mohan** 58:52
OK, makes sense.

<!-- image -->

**Reddy, Resha** 58:52
Yeah. So usually we we determine around 4:00 AM local time, do we have enough time to finish up? And most of the time we do. It's very rare that we have so many issues that we're saying, you know what, we have to roll back. And I think there's been one site in the past where even a roll back has had issues.

<!-- image -->

**Erickson, James** 59:07
Yes.

<!-- image -->

**Reddy, Resha** 59:11
Um.

<!-- image -->

**Erickson, James** 59:12
Yeah, yeah. And I mean, most on here have heard me.
Manage a call where we where we take into consideration these the the cut off time making that decision. I think we've if if we know it's gonna go long we have cancelled one before like we.

<!-- image -->

**Reddy, Resha** 59:24
Mhm.
Yes, rolled back in cancelled or put it. We've sometimes we've gotten approval from Verizon to leave it in a hybrid state.

<!-- image -->

**Erickson, James** 59:43
Mhm.

<!-- image -->

**Reddy, Resha** 59:43
And come back to it in the next window.

<!-- image -->

**Erickson, James** 59:46
And it and it really just depends on what you have scheduled to do in in the amount of time. Um, the uh

<!-- image -->

**Reddy, Resha** 59:51
Mhm.

<!-- image -->

**Erickson, James** 59:56
The DPC, the the four or five day long maintenance windows. If it's just a matter of cabling, the rollback is simply just rollback. Just the you know.

<!-- image -->

**Reddy, Resha** 1:00:01
Yeah.

<!-- image -->

**Erickson, James** 1:00:11
A couple advices before you you know that kind of thing.

<!-- image -->

**Reddy, Resha** 1:00:14
Yeah, whatever you did in that maintenance window, right?

<!-- image -->

**Erickson, James** 1:00:17
Yeah.

<!-- image -->

**Reddy, Resha** 1:00:19
Yeah.

<!-- image -->

**Erickson, James** 1:00:19
Um.

<!-- image -->

**Reddy, Resha** 1:00:21
But I think Mohan you had part of your question I didn't answer is the approval to or it was it TJ someone asked that question the approval to close the Kirk. So part of the end of the migration window is post checks that are done a lot of it by.
Some of it by us, but a lot of it by like the Tier 2 app OPS teams, whether it's, you know, Abid or T6 or whoever it is. And they check all the applications to make sure everything looks good and that's really their approval to say, OK, looks like everything's fine, you can close this out.
So it's it's a joint. We don't make that determination, we rely on them, but they also rely on us for from our device standpoint to make sure everything's good.

<!-- image -->

**Kanumuru, Mohan** 1:01:08
OK.

<!-- image -->

**Donaldson, Michael** 1:01:09
I was trying to get off mute. So and along those same lines, right is so we used to have at least with the firewall team handover meetings, right. So once we completed a project and did the post checks etcetera and we determined everything was good and it's been settled for a couple of days where.

<!-- image -->

**Reddy, Resha** 1:01:20
Mm-hmm.

<!-- image -->

**Donaldson, Michael** 1:01:28
We usually wait like a week period to make sure nobody in OPS, you know, comes back to us and said something's wrong. Then we'll release it to back to operations teams in production. And the firewall team was adamant about us doing that because they would take their teams would actually go in and do firewall checks as well.

<!-- image -->

**Reddy, Resha** 1:01:34
Yes.

<!-- image -->

**Donaldson, Michael** 1:01:46
More advanced than these post checks that we're doing on the devices as a as a parallel acceptance. There's no real acceptance. That meeting was just used to see if there was any, you know, objections to us handing it over. The route switch team is a little bit different, the IPT 3 team, so they just.

<!-- image -->

**Reddy, Resha** 1:01:50
Right.

<!-- image -->

**Donaldson, Michael** 1:02:06
We just do those in emails and then respond back to us and we're good, right? So there's not really an approval approval process that we quote have completed the maintenance.

<!-- image -->

**Reddy, Resha** 1:02:15
They don't even respond back, Mike. They stop responding, but they they get the emails and they get notified. That's that's enough. That's all they expect.

<!-- image -->

**Donaldson, Michael** 1:02:16
Right, but no.
One time they respond back to when we have an outage.

<!-- image -->

**Reddy, Resha** 1:02:27
Yeah.
Sure.

<!-- image -->

**Donaldson, Michael** 1:02:33
But we still have to go through that formal process so that they know it's been handed back to them.

<!-- image -->

**Reddy, Resha** 1:02:35
Mhm.
Exactly.
Yeah. So there's there's a planning sheet that we work off of just to do make sure that we handle all of that, that all the health checks pre-imposed, the handoffs, whatever notifications we have to do for freezes, things like that outside of the IT assurance.

<!-- image -->

**Donaldson, Michael** 1:02:44
Mhm.

<!-- image -->

**Reddy, Resha** 1:02:57
So one of the things that I didn't mention was part of our prep when we create the Kirk, when we get like 2 weeks out, we send a request out for the on-site tech and that goes to Shelly Thompson and.
We send out a request for support and that's done manually because it changes for each site and each service. So that's both are sent out about two weeks beforehand. So we can make sure that we have from a support standpoint physical and app related that we have all of that covered.
All right, any go ahead.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:03:36
It.
Oh, Rachel, real quick. Like I said, I I stopped listening to recording, just went right to that instructional sheet. So as I was going through the Kirk and I actually indicated that it was not approved, but I did catch that. Is it a week before?

<!-- image -->

**Donaldson, Michael** 1:03:44
Mm.

<!-- image -->

**Reddy, Resha** 1:03:45
Mhm.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:03:54
The Kirk is actually due where you go back in to see if it has been approved and then change the status in Kirk. OK, but.

<!-- image -->

**Reddy, Resha** 1:04:00
Yes. So I check, I go back in and I do a check of all of the Kirks for. So if I have them like TSSN one for example, if that one's set for January 20th, I'll go in like the Wednesday or Thursday before the migration to check, recheck all of the Kirks just to make sure everything's approved and then I'll send an e-mail out.
To whatever group that has not approved it and keep following up to make sure that they've approved it before we even get to the go no go call.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:04:29
OK. So just put a reminder a week before. OK. Yep. Got it. Thank you.

<!-- image -->

**Reddy, Resha** 1:04:31
Mhm.
Yeah, I've I've actually missed that in the past where I thought something was approved and it wasn't and we get to the migration and James is like, Risha, this Kirk isn't approved. Yeah, that was fun.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:04:44
Wow. Wow.

<!-- image -->

**Erickson, James** 1:04:45
Mhm.

<!-- image -->

**Donaldson, Michael** 1:04:48
I.

<!-- image -->

**Reddy, Resha** 1:04:50
So now I put a reminder on my calendar. What was that?

<!-- image -->

**Donaldson, Michael** 1:04:51
She really makes a mistake though.
I said you rarely make mistakes though.

<!-- image -->

**Erickson, James** 1:04:57
Yeah, and.

<!-- image -->

**Reddy, Resha** 1:04:58
It happens.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:05:00
You can just blame it on me right now, Rachel. Blame it on the new guy.

<!-- image -->

**Reddy, Resha** 1:05:02
Half of my calendar though, I'll tell you half of my calendar is just filled of reminders to hey, send the post check out. Hey, send the pre-check out.

<!-- image -->

**Donaldson, Michael** 1:05:11
Underview.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:05:12
Yeah.

<!-- image -->

**Reddy, Resha** 1:05:14
Because you there's too many moving pieces and you forget. If you're just trying to keep track of it on your own, you'll forget.

<!-- image -->

**Kulpa, TJ (Project Manager, Consulting &amp; NaaS)** 1:05:15
Absolutely.
Yeah, absolutely.

<!-- image -->

**Reddy, Resha** stopped transcription

<!-- wikiagent:alias-remap
{
  "schemaVersion": 1,
  "substitutions": [
    {
      "appliedAt": "2026-06-19T13:41:44.404765+00:00",
      "canonicalTerm": "TREC",
      "reviewCardId": 39,
      "term": "T rec"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.446059+00:00",
      "canonicalTerm": "TREC",
      "reviewCardId": 40,
      "term": "Test requirement creation"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.480065+00:00",
      "canonicalTerm": "TER",
      "reviewCardId": 41,
      "term": "Test exit report"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.509133+00:00",
      "canonicalTerm": "CCR",
      "reviewCardId": 42,
      "term": "NFID"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.543111+00:00",
      "canonicalTerm": "Nessus security scan",
      "reviewCardId": 43,
      "term": "Nesta security scan"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.627890+00:00",
      "canonicalTerm": "TREC",
      "reviewCardId": 51,
      "term": "test requirement creation"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.628066+00:00",
      "canonicalTerm": "TREC",
      "reviewCardId": 51,
      "term": "test requirements"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.656465+00:00",
      "canonicalTerm": "TER",
      "reviewCardId": 52,
      "term": "test exit report"
    },
    {
      "appliedAt": "2026-06-19T13:41:44.656658+00:00",
      "canonicalTerm": "TER",
      "reviewCardId": 52,
      "term": "TER delivery"
    }
  ]
}
-->
