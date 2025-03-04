<head>
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<link rel="stylesheet" type="text/css" href="bc.css">
<script src="https://cdn.rawgit.com/google/code-prettify/master/loader/run_prettify.js" type="text/javascript"></script>
</head>

<!---

- roundtable feedback notes
  /a/doc/au/2020/doc $ diff boris_shafiro_revit_api_roundtable_notes_2.txt boris_shafiro_revit_api_roundtable_notes_3.txt

- notes
  edit
  https://docs.google.com/document/d/1jDVSyVU5ZB6OAcLpGnKnXxTGOFQNC-bb2q-TbEiJQnE/edit
  view
  https://docs.google.com/document/d/1jDVSyVU5ZB6OAcLpGnKnXxTGOFQNC-bb2q-TbEiJQnE/edit?usp=sharing
  https://docs.google.com/document/d/1jDVSyVU5ZB6OAcLpGnKnXxTGOFQNC-bb2q-TbEiJQnE/edit?usp=sharing
  https://nam03.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwiki.autodesk.com%2Fdisplay%2Faeceng%2F2020-11-19%2BAU%253A%2BRevit%2BAPI%2BFeedback%2BSession%2Band%2BRevit%2BAPI%2BExpert%2BRoundtable&data=04%7C01%7Cjeremy.tammik%40autodesk.com%7Cb8333da6f47b4191574908d88cb87ccf%7C67bff79e7f914433a8e5c9252d2ddc1d%7C0%7C0%7C637414071300653300%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=lPnvKYVE8Dksz9GrcuAqvfs%2FbIO%2FtHuViJjSlbvHs6g%3D&reserved=0

- roundtable feedback notes
  /a/doc/au/2020/doc $ diff boris_shafiro_revit_api_roundtable_notes_2.txt boris_shafiro_revit_api_roundtable_notes_3.txt

2020-11-19
autodesk_uni revit api roundtable boris
slack https://autodesk.slack.com/archives/C0SR6NAP8/p1605809338152500
downloaded https://wiki.autodesk.com/pages/viewpage.action?spaceKey=aeceng&title=2020-11-19+AU%3A+Revit+API+Feedback+Session+and+Revit+API+Expert+Roundtable
edited /a/doc/au/2020/doc/boris_shafiro_revit_api_roundtable_notes_2.txt
edited /a/doc/revit/tbc/git/a/1878_forge_bim360.md
http://jeremytammik.github.io/tbc/a/1878_au_roundtable_not.html

twitter:

Here are my notes from the virtual Revit API expert and feedback roundtable on Thursday last week as part of the Autodesk University Idea Exchange on #RevitAPI @AutodeskForge @AutodeskRevit #bim #DynamoBim #ForgeDevCon https://bit.ly/au2020roundtablenotes

 the #RevitAPI @AutodeskForge @AutodeskRevit #bim #DynamoBim #ForgeDevCon 

Boris Shafiro hosted the virtual Revit API expert and feedback roundtable on Thursday last week as part of the Autodesk University Idea Exchange.
I took the following notes...

&ndash; 
...

linkedin:

Here are my notes from the virtual Revit API expert and feedback roundtable as part of the Autodesk University Idea Exchange on #RevitAPI 

https://bit.ly/au2020roundtablenotes

#bim #DynamoBim #ForgeDevCon #Revit #API #IFC #SDK #AI #VisualStudio #Autodesk #AEC #adsk 

the [Revit API discussion forum](http://forums.autodesk.com/t5/revit-api-forum/bd-p/160) thread

<center>
<img src="img/" alt="" title="" width="600"/>
<p style="font-size: 80%; font-style:italic"></p>
<p style="font-size: 80%; font-style:italic">
<a href=""></a>
</p>
</center>

-->

### Revit API Roundtable Notes

Boris Shafiro hosted the virtual 
[Revit API expert and feedback roundtable](https://thebuildingcoder.typepad.com/blog/2020/11/join-the-revit-api-expert-roundtable-and-feedback.html)
on Thursday last week, 19 November 2020, as part of the Autodesk University Idea Exchange.

Over 20 participants attended from all around the world.

I took the following notes, and later published the [recording below](#3) as well.

The session was covered by a non-disclosure agreement
or [NDA](https://en.wikipedia.org/wiki/Non-disclosure_agreement) covering
forward-looking and confidential statements, so I had to remove a few items and get approval before being able to share it with you here today.

####<a name="2"></a> Revit API Expert Roundtable and Feedback Session

<p style="font-size: 80%; font-style:italic">Autodesk University 2020, November 19, 2020
<br/>Notes by Jeremy Tammik</p>

Panel members:

- Boris Shafiro &ndash; Revit Software Development Manager
- Sasha Crotty &ndash; Senior Product Manager, Revit Platform and Services
- Scott Conover &ndash; Revit Engineering Director
- Jeremy Tammik &ndash; Forge Principal Developer Consultant
- Mikako Harada &ndash; Forge Developer Tech Consultant Manager
- Arkady Gilman &ndash; Sr. SW Architect
- Diane Christoforo, Stone Shi, Phil Xia, Romeo Belciug &ndash; Developers and Revit API Guild Members

Notes:

Q Jorge Villaroel maintains a detailing add-in. Updating the solution for each new release of the Revit API requires some work, e.g., copy solution, update references to new DLLs, update deprecated calls, etc. Could this be simplified? Do you have a recommendation on how to handle this? How do you do it yourselves?

A This topic has been discussed repeatedly in the Revit API discussion forum and The Building Coder, e.g.,
the [Revit add-in `dotnet` template](https://thebuildingcoder.typepad.com/blog/2020/11/bim360-management-dotnet-template-and-prism-goodies.html#4) just last week.
Look into conditional compiles.
You can set up different VS configuration profiles for different Revit versions and then edit your `CSPROJ` file to selective load Revit DLLs based on values set in the respective config.

Q Olli Kattelus on the new unit API; we started migration work; large code base, significant work; optimization possible using enum instead of strings? Used for hash codes etc.; significant performance effect, even inside Revit?

A Scott: we are making this change for later extensibility and being less fixed in definitions of units and later parameters as well. Ability to extend and make changes more easily, less restrictions, more connectivity; hopefully straightforward one-time change; 2021.1 includes new units, which would have been impossible previously; changes also in native code as well as add-ins; no performance hit noticeable so far; please provide examples if you discover anything and we can see whether it can be improved. Sasha: please let us know!

Q Noam Ronen: How to implement QA testing for add-ins?

A The Building Coder provides a topic group
on [Unit Testing](https://thebuildingcoder.typepad.com/blog/about-the-author.html#5.16).
Internally, the Revit team uses journal files for testing.
Forge Design Automation for Revit might help make regular tests possible via automation of running the tests.

Q Kailas Dhage: An assembly cannot propagate changes to other instances. Are there any plans for this in near future? API-specific solution?

A Sasha: long-standing topic; assemblies are a post-processing documentation feature; hard to propagate; not on the roadmap; the Revit API reflects core functionality; replacing one assembly by another can be achieved. Concrete examples of what you are trying to achieve?

Q Kailas Dhage: Possibility to read / write formula in schedules? Can we expect this API in near future?

A Please submit all requests for new functionality to the Revit Idea Station and ensure it gets many votes.
Here is a wish list entry for this in the Revit Idea Station:
[API &ndash; create a calculated value field in schedule](https://forums.autodesk.com/t5/revit-ideas/api-create-a-calculated-value-field-in-schedule/idi-p/8065079).

Q Karol Jedruszek: Will it ever be possible to import/export Materials from .adsklib files via the Revit API? Or even create new .adsklib files with the API?

A We exposed full read-write access to material properties; the material components come from another team and are shared across products; we had plans to change this, they did not happen; maybe take another look now? Sorry for these decisions ging back and forth...

Q Ivo Lafeber: there are several workarounds for the selection changed event; will this event be added to the Revit API?

A Sasha: Revit produces many false positive calls; we were actually working on an event a while, but considered the output to be unacceptable. It may be time to review this again.

Q Question #2, Olli Kattelus: AFAIK a tap element cannot be re-connected to design duct etc. once disconnected. You must create a new instance to re-connect. True? Possible to improve? I tried, and I couldn't figure out a anyway... Workarounds?

A Unfortunately no MEP expert here… we would like to change this, if required.

Q Mustafa Salaheldin: I'm facing one challenge here and I hope I can find answer with you.
We need a way to export all data from Revit (like family parameters, design options, worksets, etc.) to make them ready for ETL process.
Till now I couldn't find any way faster than Revit Export to SQL via ODBC.
The drawback here it is not automated, so my questions are:
Is there any way to do the same database conversion from Revit db to any other format via ODBC without opening Revit?
If answer is no, can it be implemented? I.e., can we implement a tool that can parse native Revit file db and export it to ODBC even if Revit is not installed on the machine?
If also this is not applicable, can we drive this from Revit in a silent mode? I.e., can I run a command that can export from Revit to ODBC as add-in but without any interactive UI need?
Regarding Design Automation API: is there any intention to produce v4?
Is there still limitation on accessing external networks, so is there any mean to serialize the db from Revit.io to Azure SQL DB for example?
Or can I export from BIM360 for example to any cloud db server like Azure SQL DB in the same manner ODBC does?
One quick note: I managed to export from Revit to SQL on my local machine using the normal way, but what pulled my attention that I couldn't see a table for "warnings"; so, my question is, can we add warnings to the exported db via ODBC? Are there any other entities that might be not exported to external databases via ODBC?

A Use design automation and the standard Revit API. You cannot use the Revit API on the desktop without Revit installed; No network access in DA; you have to create an output file. Maybe we can open up access to cloud worksharing; might consider for certain clients access to certain databases etc. Some network connection can be established up-front; check out the docs on 'on-demand'. Re v4: there is no need for a new version for this; we are already considering support for Dynamo scripting and access to cloud models and BIM360 docs.

Q: Karol Jedruszek: A question about Design Automation API. It's an amazing tool, but we've noticed that sometimes the Workitems are stuck on 'pending' for quite some time. Could you explain why it's happening? Other requests sent later sometimes process faster. Could an improved status message be sent, not just ‘pending’, e.g., ‘sorry for slower processing right now’? We are sometimes unsure whether there is an error on our side… one thing takes seconds, another time the same thing takes several minutes.

A Maybe you are stuck in the queue. Maybe new machines are being spun up; that could take up to ten minutes; ask on StackOverflow. I’ll check whether we can improve the status message. We do not guarantee any time. A minute is pretty snappy. What time would you expect? Be aware that this is batch processing, and nobody should ever be sitting around waiting for it. We might be able to expose a current average queue time.

Q Matthew Hannon: I have a few questions. Geometric calculations on multiple threads?

A You can use multiple threads in your own code; the Revit API is single threaded. Certain touch points enforce the main thread, e.g., transactions; some utility classes might allow multithreading, but none of them are guaranteed to be thread safe; they may seem immutable and not really be so.

Q Check whether elements touch?

A We will follow up on this; please also check Revit Ideas.

Q Collection classes are often `IEnumerable`, not <code>IEnumerable&lt;T&gt;</code>?

A That has historical reasons. They were introduced earlier on. We are gradually migrating away from that. We’ll get to it.

Q Plans to support .NET 5?

A We discussed this internally just yesterday. We have to get there. This is more than just an API decision, it affects internals as well. More than just a version increment. Not in next release. Everything will have to move at once.

<!--
Removed because confidential, preview release:

Q Bettina: Will Export PDF be available in the next major release? I see export pdf in the preview API, in the October beta preview, but there is no Export PDF button as described in the help.

A It should be there in both API and UI. Ask in the preview forum.
-->

Q Mustafa: Is there any way through API to control which categories I want to export to external db? Also, why warnings are not coming to SQL when exporting from ODBC?

A The API does not expose anything ODBC related. Check out DBLink, but that has no API access.

Q Ivo: a shared parameter can be visible or invisible, in the Revit API it's read-only, the value can be changed with a workaround, but can we expect this parameter not to be read-only in the future?

A By definition, the `Invisible` shared parameter option makes the parameter not accessible/applicable in the project settings. Therefore, it would not make sense to make these parameters independently editable in the project.

<center>
<img src="img/stenography_eclectic_shorthand_by_cross.png" alt="Eclectic shorthand" title="Eclectic shorthand" width="533"/>
</center>

####<a name="3"></a> Addendum &ndash; Full Recording

The [complete one-hour recording](https://youtu.be/vDC_4Pwt6WM) is now available as well.

Note that it includes a sentence or two that was censored above for NDA reasons  :-)

<center>
<iframe width="480" height="270" src="https://www.youtube.com/embed/vDC_4Pwt6WM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>
