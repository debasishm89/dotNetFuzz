# dotNetFuzz

A quick and dirty .NET "Deserialize_*" fuzzer based on James Forshaw's (@tiraniddo) DotNetToJScript.

# The Background

Lately I've got a chance to take a look at James Forshaw's **DotNetToJScript**.( https://github.com/tyranid/DotNetToJScript ). DotNetToJScript is a tool to generate a JScript which bootstraps an arbitrary .NET Assembly and class. Since DotNetToJScript deals **serialization / de-serialzination** of .NET objects a lot, I decided to write this fuzzer. This fuzzer targets a very tiny component of .NET Framework. Hence the name of this fuzzer may sound bit inappropriate :P , however I couldn't think of any better. After running this fuzzer for few days, it recorded several OOB issues. Some of the interesting OOB reads were reported to MSRC ( **~July'18** ), however Microsoft decided not to fix any of them :( **POC's are being made public after receiving confirmation from MSRC**. Responses from MSRC are listed below:

**MSRC Case 46714 CRM:0461057158**

> We will resolve this issue as "won't fix". This OOB read is fixed in recent versions of >NET and an exception is generated that the public key is invalid. The issue reproduces only on **.NET 2.0, which is no longer supported.** 

**MSRC Case 47293 CRM:0461061041, MSRC Case 46897 CRM:0461058267, MSRC Case 47306 CRM:0461061145**

> Microsoft has decided that it will not be fixing this **vulnerability** in the current version and we are closing this case.  At this time, you are able to blog about/discuss this case and/or present your findings publicly about the current version. We'd love to hear if you plan post anything. We can request feedback from our engineering teams about the technical accuracy of the post, and prepare for any possible customer questions. Thank you and we look forward to more submissions from you in the future.

# How to Reproduce ? 

Grab **poc.js** file(s) from **crashes/** folder and execute **c:\\>wscript.exe poc.js**.
(In some cases you may have to enable pageHeap as well)

# LICENCE

"THE BEER-WARE LICENSE" (Revision 42): 
Debasish Mandal wrote this file. As long as you retain this notice you can do whatever you want with this stuff. If we meet some day, and you think this stuff is worth it, you can buy me a beer in return Debasish Mandal.


Cheers,
Debasish
https://twitter.com/debasishm89
