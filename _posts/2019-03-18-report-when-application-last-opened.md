---
layout: post
title: "Report When Application Last Opened"
description: ""
tags: [jamf]
---

While Jamf Pro is capable of collecting Application Usage data, sometimes we just want to know when an application was last opened. This information is especially helpful when reclaiming unused licenses or retiring unused software.

Create an Extension Attribute in Jamf Pro using the **Date** data type. Then select **Script** for the input and paste in the following snippet. Though _Self Service_ is used here, any application path can be substituted.

{% highlight bash %}
#!/bin/bash

APPLICATION_PATH=/Applications/Self\ Service.app

if [ ! -e "$APPLICATION_PATH" ]; then
    result="Not Present"
fi

if [ -e "$APPLICATION_PATH" ]; then
    result=`/usr/bin/mdls "$APPLICATION_PATH" | /usr/bin/grep -w "kMDItemLastUsedDate" | /usr/bin/awk '{ print $3 }'`
fi

if [ "$result" == "" ]; then
    result="2001-01-01 01:01:01"
fi

/bin/echo "<result>$result</result>"
{% endhighlight %}

Now that we are collecting this information it can be used when creating Smart Computer Groups or Advanced Computer Searches.

There is also a [Feature Request](https://www.jamf.com/jamf-nation/feature-requests/10453/report-date-application-last-opened) for this on the Jamf Nation website.