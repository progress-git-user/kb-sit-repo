---
title: Map Extent not working properly on different resolutions
description: This article provides troubleshooting steps for resolving the issue with Map Extent not working properly on different resolutions in RadMap for ASP.NET AJAX.
type: troubleshooting
page_title: Troubleshooting Map Extent Issue on Different Resolutions | RadMap for ASP.NET AJAX
slug: map-extent-issue-different-resolutions-radmap-ajax
tags: radmap, map extent, resolutions, troubleshooting
res_type: kb

---

## Description

I'm experiencing an issue with the Map Extent not working properly on different resolutions in RadMap for ASP.NET AJAX. 

When trying to show the map so it fills the entire screen viewing the whole world, the Map element fills the entire viewport. I'm using the Extent function with various positions to make the map properly zoom in. However, the map element doesn't zoom properly and is zoomed out too far, causing the map to contain an "empty" section to its right.

I'm using only shape layers without a tile layer, and the shape layers do not wrap around. This makes the issue look even worse, as one shape layer is used to display the Day-Night boundary, and if the map zooms incorrectly, that layer is being cut vertically at longitude 180, resulting in a distinct "edge" where the map ends.

## Steps to Reproduce

1. Set up a RadMap with shape layers and without a tile layer.
2. Use the Extent function with various positions to zoom in the map.
3. Observe that the map is zoomed out too far and contains an "empty" section to its right.

## Cause

The issue occurs when using the Extent function with different positions to zoom the map. The Extent function stops doing zooming on the given region and zooms out too far.

## Solution

To resolve the issue with Map Extent not working properly on different resolutions, follow these steps:

1. Use the Zoom setting instead of the Extent function to zoom the map. The Zoom setting accepts integers and can be adjusted to achieve the desired zoom level.
2. Adjust the Zoom setting based on the resolution of the screen to ensure proper zooming.

## Suggested Workaround

If the above solution does not resolve the issue, you can try the following workaround:

- Add a second map next to the first map to fake the wrap-around effect of the shape layers.

## Notes

- Ensure that the Zoom setting is adjusted based on the resolution of the screen to achieve the desired zoom level.

## See Also

- [RadMap Documentation](https://docs.telerik.com/devtools/aspnet-ajax/controls/map/overview)
