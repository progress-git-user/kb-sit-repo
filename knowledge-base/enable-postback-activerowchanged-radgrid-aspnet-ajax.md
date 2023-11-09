---
title: Enabling Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
description: Learn how to enable postback on ActiveRowChanged event in RadGrid for ASP.NET AJAX.
type: how-to
page_title: How to Enable Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
slug: enable-postback-activerowchanged-radgrid-aspnet-ajax
tags: radgrid, asp.net ajax, postback, activerowchanged
res_type: kb
---

## Environment
| Product | RadGrid for ASP.NET AJAX |
|---|---|
| Version | 2011.3 1115 |

## Description
I want to enable postback on the ActiveRowChanged event in RadGrid for ASP.NET AJAX. Currently, the postback only occurs when I click on a row using the mouse, but not when I change the row selection using the keyboard arrow keys. I need to perform certain operations in the code-behind when navigating rows using the arrow keys.

## Solution
To enable postback on the ActiveRowChanged event when navigating rows using the keyboard arrow keys, follow these steps:

1. Add the following code to the RadGrid markup to enable keyboard navigation and row selection:
```
<ClientSettings EnablePostbackOnRowClick="true" AllowKeyboardNavigation="true">
    <Selecting AllowRowSelect="True" />
</ClientSettings>
```

2. In the code-behind, handle the ActiveRowChanged event and perform your desired operations. The postback will occur automatically when the active row changes.

```csharp
protected void RadGrid1_ActiveRowChanged(object sender, EventArgs e)
{
    // Perform your desired operations here
}
```

By following these steps, you will enable postback on the ActiveRowChanged event in RadGrid for ASP.NET AJAX when navigating rows using the keyboard arrow keys.

## Notes
- Make sure that the RadGrid is configured with the EnablePostBackOnRowClick and AllowKeyboardNavigation properties set to true, and AllowRowSelect set to True for row selection.
- Handle the ActiveRowChanged event in the code-behind to perform your desired operations when the active row changes.
- Keep in mind that it is recommended to keep related questions in one support thread or forum post for better support and faster response times.

## See Also
- [Forum Thread: Enable Postback on ActiveRowChanged](https://www.telerik.com/forums/enable-postback-on-activerowchanged)
