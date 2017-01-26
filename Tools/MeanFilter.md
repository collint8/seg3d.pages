---
layout: default
title: Mean
category: ToolDocs 
tool: DataFilters 
---

# {{ page.title }} 

## Category

**{{ page.tool }}**

## Description

### Summary

This filter performs smoothing on the data layer using a step function.

### Detailed Description

The Mean filter performs a smoothing on the data layer using a discrete step function kernel. For every pixel (except the edges), this filter performs an averaging of the neighboring pixels. This filter will reduce noise by averaging it out, but will also reduce edges. The neighborhood size is controlled by the distance parameter, the greater the distance, the more smoothing.

![alt text]({{ site.github.url }}/images/{{ page.title }}GUI.png)

{% capture url %}{% include url.md%}{% endcapture %}
{{ url }}

