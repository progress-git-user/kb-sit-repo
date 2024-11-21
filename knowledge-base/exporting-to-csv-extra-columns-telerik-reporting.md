---
title: Exporting to CSV with Extra Columns
description: This article provides a solution for the issue where exporting to CSV produces extra columns containing headers for each data column in Telerik Reporting.
type: troubleshooting
page_title: How to Fix Exporting to CSV with Extra Columns in Telerik Reporting
slug: exporting-to-csv-extra-columns-telerik-reporting
tags: telerik-reporting, export, csv, extra columns
res_type: kb
---

## Environment
| Product   | Progress Telerik Reporting |
|-----------|---------------------------|
| Version   | 14.0.20.219              |

## Description
When exporting to CSV in Telerik Reporting, you may encounter an issue where extra columns containing headers for each data column are added.

## Cause
The issue occurs due to a specific implementation in the code.

## Solution
To resolve this issue, follow these steps:

1. In the `Process` method of the Handler, modify the code as shown below:

```csharp
protected override IAsyncUploadResult Process(UploadedFile file, HttpContext context, IAsyncUploadConfiguration configuration, string tempFileName)
{
    var queryStringParam1 = context.Request.QueryString["saveToFolder"];
    string targetFolder = context.Server.MapPath(configuration.TargetFolder);
    string fileName = file.GetName();      

    CustomAsyncUploadResult result = CreateDefaultUploadResult<CustomAsyncUploadResult>(file);
    //file.SaveAs(targetFolder + "/" + fileName);
     
    if (true)
    {
        //Success
        result.ErrorMessage = String.Empty;
    }
    else
    {
        // Error. Set error message      
        result.ErrorMessage = "File failed to upload in DB";
    }   
    
    return result;
}
```

2. In the client-side code, add the following function to handle the `OnClientFileUploaded` event:

```javascript
function OnClientFileUploaded(sender, args) {
    var msg = args.get_fileInfo().ErrorMessage;

    if (msg) {
        //Display error message
        $('#msg').text(msg);
        //Remove selected file
        $('.ruButton.ruRemove').click();
    }
}
```

## Notes
- Make sure to replace `CustomAsyncUploadResult` with the appropriate class name in your code.
- Adjust the code as needed to fit your specific requirements.

## See Also
- [Telerik Reporting Documentation](https://docs.telerik.com/reporting/overview)
