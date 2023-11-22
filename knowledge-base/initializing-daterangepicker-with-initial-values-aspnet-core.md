---
title: Initializing DateRangePicker with Initial Values
description: This article provides instructions on how to set initial values for the DateRangePicker in ASP.NET Core.
type: how-to
page_title: Initializing DateRangePicker with Initial Values | ASP.NET Core DateRangePicker
slug: initializing-daterangepicker-with-initial-values-aspnet-core
tags: 
  - daterangepicker
  - aspnet-core
  - initializer
  - initial values
res_type: kb
---

## Environment
| Product | Version |
|---------|---------|
| DateRangePicker for ASP.NET Core | 2020.1 406 |

## Description
I want to set initial values for the DateRangePicker in ASP.NET Core, but when I provide a value on startup, it is not represented. Edited!

## Solution
To set the initial values for the DateRangePicker, you can use the `Range.Start` and `Range.End` properties. 

Here's an example code snippet:

```csharp
@(Html.Kendo().DateRangePicker()
    .Name("daterangepicker")
    .Range(r => r.Start(Model.StartDate).End(Model.EndDate))
    .Events(e => e.Change("onDateRangeChange"))
)
```

Make sure to update the control definition in your code with the modified snippet.

After making this change, the DateRangePicker should display the initial values correctly.

## Notes
- Ensure that the `model` is returned to the View.
- For more information and examples, you can refer to the [official Telerik demo](https://demos.telerik.com/aspnet-core/daterangepicker/date-range).
