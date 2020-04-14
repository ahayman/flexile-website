---
layout: post
title: Crash Reporting
category: [news]
---

So, funny thing happened.... bugs.  This last build included an integrated "crash reporting" service, Crashlytics, that compiles and emails me whenever Flexile crashes.  While I do a lot of testing, and my beta testers fill in the "gaps"... there's only so much a dozen people can actually cover in an app as large and as complex as Flexile.  Knowing when a crash occurred would help me a lot.  So this past update (v 1.0.6) was the first update to include this reporting service in a public release of Flexile.  Now, I had been testing/using this service with my beta testers for the last couple of months and I found it incredibly useful.  However, I didn't really know what to expect when it was released into the public.  On the one hand, I kind of hoped that not much would happen, as it would mean Flexile was pretty much bug free.... not that I really expected this.  On the other hand, getting thousands of crash reports would mean I should really reconsider my chosen profession.

​Luckily, I didn't get thousands of crash reports.  I did, however, get a few.  Enough of them that I decided to squash them quickly and put out another update.  It's very important that Flexile is stable, which is why I'm using the Crash Reporting service in the first place.  I especially found a very "pernicious" bug in the new Sidebar that occurred if you added, deleted or moved a Table Section.  It's kind an obvious bug, except that me and (I suspect) all my beta testers have already 'fleshed' out our databases so we don't actually mess with that part of the app very much.... <sigh>... a bad oversight.  I've already implemented the fix and submitted the update.  Assuming no more 'major' bugs come in, the update should be approved by early next week (possibly sooner if Apple is feeling efficient).   

If you want more information about the bugs that were fixed, please take a look at the Release Notes for version 1.0.7.

​Privacy: ​I want to assure you that even though Flexile now reports to me when it crashes, no personal information is transmitted.  ​Essentially, I receive a report that tells me when the crash occurred, some device information (iPad, iPhone, etc) and where in my code the crash occurred.  Your data isn't transmitted.  

​