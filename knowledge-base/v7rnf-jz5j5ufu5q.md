---
title: Binding the Kendo UI for jQuery Grid Control
description: Learn how to bind the Kendo UI for jQuery Grid control to a data source.
type: how-to
page_title: How to Bind the Kendo UI for jQuery Grid Control
slug: bind-kendo-ui-jquery-grid-control
tags: grid, kendo ui, jquery, bind, data source
res_type: kb
---

## Environment

| Property | Value |
| --- | --- |
| Product | Kendo UI for jQuery |
| Version | 2022.2.802 |

## Description

To bind the Kendo UI for jQuery Grid control to a data source, you can use the `dataSource` property.

## Solution

Follow these steps to bind the Grid control:

1. Create a data source object with the desired data.

```javascript
var dataSource = new kendo.data.DataSource({
  data: [
    { id: 1, name: "John" },
    { id: 2, name: "Jane" },
    { id: 3, name: "Bob" }
  ]
});
```

2. Initialize the Grid and configure the `dataSource` property to use the created data source.

```javascript
$("#grid").kendoGrid({
  dataSource: dataSource,
  columns: [
    { field: "id", title: "ID" },
    { field: "name", title: "Name" }
  ]
});
```

Make sure to replace `"#grid"` with the appropriate selector for your Grid element.

That's it! The Grid control is now bound to the specified data source.

## See Also

- [Kendo UI for jQuery Grid Documentation](https://docs.telerik.com/kendo-ui/controls/data-management/grid)
