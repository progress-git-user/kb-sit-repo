---
title: Enabling Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
description: Learn how to enable postback on ActiveRowChanged event in RadGrid for ASP.NET AJAX.
type: how-to
page_title: Enable Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
slug: enable-postback-activerowchanged-radgrid-aspnet-ajax
tags: radgrid, asp.net ajax, postback, activerowchanged
res_type: kb
---

## Environment

| Property | Value |
| --- | --- |
| Product | RadGrid for ASP.NET AJAX |
| Version | 2011.3 1115 |

## Description

I want to enable postback on the ActiveRowChanged event in a RadGrid for ASP.NET AJAX. Currently, when I use the keyboard up/down keys to change the row selection, the grid updates the selected row visually, but it does not trigger a postback. I need the postback to occur so that I can perform data binding and other logic from the code-behind.

## Solution

To enable postback on the ActiveRowChanged event, you can follow these steps:

1. Set the `EnablePostBackOnRowClick` property of the RadGrid's `ClientSettings` to `true`.
2. Set the `AllowKeyboardNavigation` property of the RadGrid's `ClientSettings` to `true`.
3. Set the `AllowRowSelect` property of the RadGrid's `Selecting` attribute to `true`.

Here is an example of how to enable postback on ActiveRowChanged:

```markup
<telerik:RadGrid ID="RadGrid1" runat="server">
    <ClientSettings EnablePostBackOnRowClick="true" AllowKeyboardNavigation="true">
        <Selecting AllowRowSelect="true" />
    </ClientSettings>
    <!-- ... -->
</telerik:RadGrid>
```

With these settings, when you navigate through the rows using the keyboard up/down keys, the RadGrid will trigger a postback on the ActiveRowChanged event, allowing you to perform the necessary operations in the code-behind.

## Notes

- Make sure to replace `"RadGrid1"` with the ID of your RadGrid control.
- Enabling postback on ActiveRowChanged will cause a postback every time a row is selected or changed using the keyboard navigation.
- Keeping related questions in one support thread or forum post is recommended to help us track your support history and provide better answers in a shorter time.

## See Also

- [Forum thread discussing enabling postback on ActiveRowChanged](https://www.telerik.com/forums/enable-postback-on-rowselected-or-activerowchanged)
