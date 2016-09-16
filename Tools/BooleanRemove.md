---
layout: default
title: BooleanRemove
category: ToolDocs 
tool: MaskFilters
---

# {{ page.title }} 

## Category

**{{ page.tool }}**

## Description

### Summary

The boolean REMOVE filter removes the intersecting region of two masks from the first.

### Detailed Description

The boolean REMOVE filter will input two mask layers and use the second input to remove the intersecting regions from the first. The result of this can be thought of as the first region minus the second region.

![alt text]({{ site.github.url }}/images/{{ page.title }}GUI.png)

{% capture url %}{% include url.md%}{% endcapture %}
{{ url }}

