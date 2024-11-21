---
title: Enabling Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
description: Learn how to enable postback on ActiveRowChanged in RadGrid for ASP.NET AJAX.
type: how-to
page_title: Enable Postback on ActiveRowChanged in RadGrid for ASP.NET AJAX
slug: enable-postback-activerowchanged-radgrid-aspnet-ajax
tags: radgrid, asp.net ajax, postback, activerowchanged
res_type: kb
---

## Environment

| Product  | RadGrid for ASP.NET AJAX |
|----------|--------------------------|
| Version  | 2011.3 1115              |

## Description

To enable postback on ActiveRowChanged in RadGrid for ASP.NET AJAX, follow these steps:

1. Set the `AllowKeyboardNavigation` property of the `RadGrid` to `true` in the `<ClientSettings>` section:

```
<ClientSettings EnablePostbackOnRowClick="true" AllowKeyboardNavigation="true" >
```

2. Enable row selection by setting the `AllowRowSelect` property to `true` in the `<Selecting>` section:

```
<Selecting AllowRowSelect="True" />
```

By default, when you click on a row using the mouse, the postback occurs and you can perform the necessary operations. However, when you use the keyboard up/down keys to change the row selection, the grid visually changes the selected row but does not trigger a postback.

If you want to enable postback while navigating using the arrow keys, you can achieve this by implementing the following JavaScript solution.

## Solution

1. Attach the `OnRowSelected` client event to the `RadGrid` and pass the grid ID to the `_doPostBack` function in JavaScript. This will trigger a postback when a row is selected.

```javascript
function OnRowSelected(sender, eventArgs) {
    var gridId = sender.get_id();
    _doPostBack(gridId);
}
```

2. In the code-behind, handle the postback event and perform the necessary data binding and logic.

```csharp
protected void RadGrid1_ItemCommand(object sender, GridCommandEventArgs e)
{
    if (e.CommandName == RadGrid.SelectCommandName)
    {
        // Perform data binding and other logic here
    }
}
```

With this solution, a postback will occur when you navigate using the arrow keys, allowing you to perform the required operations in the code-behind.

## Notes

- Make sure to replace `RadGrid1` with the ID of your `RadGrid` control in the code-behind example.
- This solution requires both client-side and server-side code modifications.
- Keep in mind that it is recommended to keep related questions in one support thread or forum post to help us provide better and faster support.
