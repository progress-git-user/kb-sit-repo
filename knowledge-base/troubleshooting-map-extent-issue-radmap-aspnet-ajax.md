---
title: Troubleshooting Map Extent Issue
description: This article provides troubleshooting steps for resolving an issue with the Map Extent function not working properly in RadMap for ASP.NET AJAX.
type: troubleshooting
page_title: Troubleshooting Map Extent Issue | RadMap for ASP.NET AJAX
slug: troubleshooting-map-extent-issue-radmap-aspnet-ajax
tags: troubleshooting, map extent, RadMap, ASP.NET AJAX
res_type: kb
---
# Environment
| Property | Value |
|----------|-------|
| Product  | RadMap for ASP.NET AJAX |
| Version  | 2019.2 814 |

# Description
I am experiencing an issue with the Map Extent function in RadMap for ASP.NET AJAX. When trying to show the map so it fills the entire screen and displays the whole world, the Map element does not zoom properly. The map is zoomed out too far, causing an "empty" section to appear on the right side. This issue occurs when using various positions with the Extent function on different resolutions.

I am using the map without a tile layer and with only shape layers. The use of shape layers, which do not wrap around, exacerbates the issue. I have a shape layer displaying the Day-Night boundary, and when the map zooms incorrectly, the layer is cut vertically at longitude 180, creating a distinct edge where the map ends.

I have tried using different locations for the Extent function, but it seems that at a certain "area," the function stops zooming on the given region and zooms out too far. Using the Zoom setting alone does not work since it only accepts integers.

Is there a way to resolve this issue? Additionally, is there a workaround for the shape layer wrap around issue, other than adding a second map next to the first to simulate wrapping?

# Solution
Currently, there isn't enough information to provide a specific solution for this issue. However, we recommend the following steps to troubleshoot the problem:

1. Verify that you are using the latest version of RadMap for ASP.NET AJAX. You can check for any available updates on the Telerik website or through the Telerik Control Panel.
2. Double-check your code to ensure there are no syntax errors or incorrect usage of the Extent function.
3. Review the documentation and examples provided by Telerik for working with the Extent function in RadMap.
4. If possible, create a runnable sample that reproduces the issue and share it with Telerik support. This will help them to debug the issue locally and identify the cause.

Please note that without a specific code sample or more detailed information about your configuration, it is challenging to provide a precise solution. However, following the steps mentioned above should help in troubleshooting the issue.

# Notes
- Ensure that you have a valid license for RadMap for ASP.NET AJAX.
- Consider reaching out to Telerik support for further assistance with this issue.

# See Also
- [RadMap for ASP.NET AJAX Documentation](https://docs.telerik.com/devtools/aspnet-ajax/controls/map/overview)

Please let me know if you need any further assistance.
