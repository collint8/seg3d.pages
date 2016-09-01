---
title: ConnectedComponentSize
category: ToolDocs 
tool: MaskFilters 
---

# {{ page.title }} 

## Category

**{{ page.tool }}**

## Description

### Summary

Similar to the connected component filter, this filter will return a image data layer but the data value will correspond to its size (logarithmic or linear scale).

### Detailed Description

The connected component size filter is similar to the connected component filter, but will return a image data layer labeling each connected region with a data value corresponding to its size (logarithmic or linear scale). This allows the user to manipulate the connected regions in the volume based on size. For example, thresholding real data can yield several regions of interest that are correct maskings of the data, but may also capture small regions of noise in other areas of the scan. These small regions of noise can be eliminated using the connected component filter by using the threshold tool on the result.

![alt text]({{ site.github.url }}/images/{{ page.title }}GUI.png)

{% capture url %}{% include url.md%}{% endcapture %}
{{ url }}

