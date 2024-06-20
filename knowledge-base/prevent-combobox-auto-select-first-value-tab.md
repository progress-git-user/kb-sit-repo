---
title: Resolving Object Reference Error with Telerik.Reporting.Drawing.FontExtensions.ToEngineFont in .NET Core on Alpine Docker 
description: Resolving Object Reference Error with Telerik.Reporting.Drawing.FontExtensions.ToEngineFont in .NET Core on Alpine Docker
type: how-to
page_title: Resolving Object Reference Error with Telerik.Reporting.Drawing.FontExtensions.ToEngineFont in .NET Core on Alpine Docker
slug: prevent-combobox-auto-select-first-value-tab
tags: kendo-ui, combobox, aspnet-mvc, auto-select, tab
res_type: kb
ticketid: 1453919
---

## Environment

| Product | Kendo UI ComboBox for ASP.NET MVC |
| --- | --- |
| Version | 2019.3.1023 |

## Description

When upgrading the `Kendo.Mvc.dll` from version `2016.2.714.340` to `2019.3.1023.340`, the `Html.Kendo().ComboBox` started auto-selecting the first value from the available options when navigating through the options using the tab key.

This KB article also answers the following questions:
- How to prevent Kendo UI ComboBox from auto-selecting the first value?
- How to handle tab navigation in Kendo UI ComboBox for ASP.NET MVC?
- How to maintain previous behavior of Kendo UI ComboBox after DLL upgrade?

## Solution

To prevent the `Kendo UI ComboBox` from auto-selecting the first value when navigating through the options using the tab key, you can utilize the `select` event to override the default behavior.

1. Add the `select` event handler to the ComboBox configuration.
2. In the event handler, check if the selection is due to tab navigation.
3. Prevent the default selection behavior if the tab key is used.

Here's how to implement this:

```csharp
@(Html.Kendo().ComboBox()
    .Name("comboBox")
    .DataTextField("Text")
    .DataValueField("Value")
    .Events(events => events.Select("onSelect"))
)

<script type="text/javascript">
    function onSelect(e) {
        // Check if the event was triggered by pressing the tab key
        if (e.sender.input.is(":focus")) {
            e.preventDefault();
        }
    }
</script>
```

This script ensures that the first value is not auto-selected when navigating through the ComboBox options using the tab key.

## See Also

- [ComboBox Documentation](https://docs.telerik.com/kendo-ui/api/javascript/ui/combobox)
- [ComboBox Events](https://docs.telerik.com/kendo-ui/api/javascript/ui/combobox#events-select)
