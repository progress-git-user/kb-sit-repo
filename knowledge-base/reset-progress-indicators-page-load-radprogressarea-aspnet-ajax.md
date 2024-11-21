---
title: Resetting Progress Indicators after PageLoad
description: Learn how to reset progress indicators in RadProgressArea after a page load.
type: how-to
page_title: How to Reset Progress Indicators after PageLoad in RadProgressArea for ASP.NET AJAX
slug: reset-progress-indicators-page-load-radprogressarea-aspnet-ajax
tags: radprogressarea, asp.net ajax, page load, progress indicators
res_type: kb
---

## Environment

| Property | Value |
| --- | --- |
| Product | RadProgressArea for ASP.NET AJAX |
| Version | 2020.1 219 |

## Description

I want to reset progress indicators in RadProgressArea after a page load. I have different indicators for different button clicks and I need to reset them.

## Solution

To reset progress indicators in RadProgressArea after a page load, follow these steps:

1. Add the following code to the Page_Load event in your code-behind file:

```
RadProgressArea1.ProgressIndicators = ProgressIndicators.None;
```

2. Replace `RadProgressArea1` with the ID of your RadProgressArea control.

By setting `ProgressIndicators` to `None`, you are resetting all the progress indicators in RadProgressArea.

That's it! Your progress indicators will be reset after a page load.

## Notes

- Make sure to replace `RadProgressArea1` with the ID of your RadProgressArea control.
- This solution assumes you are using the RadProgressArea control in ASP.NET AJAX.
- If you have multiple RadProgressArea controls on your page, make sure to reset the progress indicators for each control separately.
