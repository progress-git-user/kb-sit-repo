---
title: Resetting Progress Indicators after Page Load
description: Learn how to reset progress indicators in RadProgressArea for ASP.NET AJAX after a page load.
type: how-to
page_title: How to Reset Progress Indicators after Page Load in RadProgressArea for ASP.NET AJAX
slug: reset-progress-indicators-after-page-load-radprogressarea-aspnet-ajax
tags: radprogressarea, aspnet-ajax, indicators, reset, page load
res_type: kb
---

## Environment

| Property | Value              |
|----------|--------------------|
| Product  | RadProgressArea    |
| Version  | 2020.1 219         |

## Description

I want to reset progress indicators in RadProgressArea for ASP.NET AJAX after a page load. Currently, the indicators are not being reset automatically.

## Solution

To reset the progress indicators after a page load, you can use the following approach:

1. Add the following JavaScript code to your page:

```javascript
function resetProgressIndicators() {
    var progressArea = $find("<%= RadProgressArea1.ClientID %>");
    progressArea.set_progressIndicators(ProgressIndicators.None);
}
```

2. Call the `resetProgressIndicators` function after the page load event:

```javascript
Sys.Application.add_load(resetProgressIndicators);
```

By doing this, the progress indicators will be reset to their default values after the page load event.

That's it! Now the progress indicators in RadProgressArea will be reset automatically after a page load.

## Notes

- Make sure to replace `<%= RadProgressArea1.ClientID %>` with the actual ClientID of your RadProgressArea control.

## See Also

- [RadProgressArea Documentation](https://docs.telerik.com/devtools/aspnet-ajax/controls/progressarea/overview)
