---
title: Making RadScheduler Events Trigger Immediately in IE7 and IE8
description: This article explains how to address the issue of RadScheduler events not triggering immediately in IE7 and IE8, unlike in IE6.
type: how-to
page_title: Ensuring Immediate Event Triggering for RadScheduler in IE7 and IE8
slug: immediate-event-triggering-radscheduler
tags: radscheduler, radajaxpanel, asp.net ajax, event triggering, internet explorer
res_type: kb
category: knowledge-base
ticketid: 1576925
---

## Environment

| Product | Version      |
|---------|--------------|
| RadScheduler for ASP.NET AJAX | 2022.2.622 |

## Description

I am working with the RadScheduler in an ASP.NET AJAX application. The application uses a RadAjaxPanel control. When I access the application in Internet Explorer 6 (IE6), events trigger immediately as expected. However, this immediate triggering does not occur in Internet Explorer 7 (IE7) and Internet Explorer 8 (IE8). I'm using RadControls for ASP.NET AJAX Q2 2009 SP1. I need a solution to make the events trigger immediately in IE7 and IE8, just as they do in IE6.

This KB article also answers the following questions:
- How can I make RadScheduler events trigger immediately in IE7 and IE8?
- What is the workaround for immediate event triggering in RadScheduler across different IE versions?
- Is there a way to ensure consistent event triggering behavior in RadScheduler for various versions of Internet Explorer?

## Solution

To address the issue of RadScheduler events not triggering immediately in IE7 and IE8, unlike in IE6, you may need to adjust the configuration or implementation of the RadAjaxPanel and RadScheduler. Since the specific feature of immediate event triggering as experienced in IE6 is not directly supported in later versions of Internet Explorer through the RadControls used, consider the following general tips and checks:

1. **Update RadControls:** Ensure you are using the latest version of RadControls for ASP.NET AJAX. Older versions may not have optimal support or fixes for issues related to newer browsers or later versions of Internet Explorer.

2. **Use RadAjaxManager:** Consider replacing RadAjaxPanel with RadAjaxManager for more fine-grained control over AJAX settings and to manage AJAX requests more explicitly. RadAjaxManager offers greater flexibility in configuring AJAXified controls.

3. **Check Compatibility Settings:** Internet Explorer 7 and 8 have compatibility view settings that can affect how web applications behave. Ensure that your application is not being forced into a compatibility mode that emulates an older version of IE, which might impact JavaScript execution and event handling.

4. **JavaScript Optimization:** Review and optimize any JavaScript code associated with event handling. Ensure that JavaScript is not causing delays in event triggering. Utilize JavaScript profiling tools to identify and optimize slow-running scripts.

5. **Server-Side Event Handling:** Evaluate if some of the event logic can be moved to server-side processing to minimize client-side delays. In some cases, handling events server-side can improve responsiveness.

6. **Browser Testing Tools:** Utilize browser developer tools in IE7 and IE8 to monitor and debug event triggering and handling. These tools can help identify any errors or performance issues that might be affecting event responsiveness.

Since the direct feature requested is not supported, these general guidelines can help improve the responsiveness of event triggering in RadScheduler across different versions of Internet Explorer. For more specific solutions, consider reaching out to Telerik Support with details about the events and functionalities affected.

## Notes

- The behavior of web applications, including event triggering, can vary significantly across different browser versions. Testing across multiple environments is crucial for identifying and addressing compatibility issues.

- Always ensure that your application is tested on the target browsers and versions to confirm that the desired behavior is achieved.

## See Also

- [RadScheduler Overview](https://docs.telerik.com/devtools/aspnet-ajax/controls/scheduler/overview)
- [RadAjaxManager](https://docs.telerik.com/devtools/aspnet-ajax/controls/ajaxmanager/overview)
- [Browser Compatibility in RadControls for ASP.NET AJAX](https://docs.telerik.com/devtools/aspnet-ajax/general-information/browser-support)
