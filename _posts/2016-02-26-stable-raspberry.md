---
layout: post
title:  "Make the Raspberry running stable"
date:   2016-02-26 22:57:13 +0100
categories: raspberry stable
---

I always loved the raspberry and wanted to them permanently for different purposes,
but no matter what, they seemed to bug out after so time.

Good, high quality power supplies didn't help in my case.

Even with a high quality PSU only `4.8 Volts` where on the test points of the
raspberry.

##My Solution

1. Use a Buck-Converter that outputs about `5.2 Volts`
    (The Buck-Converter is the `kis3r33s` available from china)
    The advantage of this Buck-Converter is, that is can actually supply enough
    amperage for the raspberry. The converter does not get warm.
2. I used the shortest USB-Cable I could find (about 15cm), so that the voltage
  drop of the cable would be minimal.

##Effectiveness

Now the Raspberry runs at `5.1-5.2 Volts` which is at the upper end of what the
raspberry can handle.

It seems like **overvoltage is better than undervoltage** when it comes to
stability and the raspberry pi.
