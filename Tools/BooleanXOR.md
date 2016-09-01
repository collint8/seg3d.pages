---
title: BooleanXOR
category: ToolDocs 
tool: MaskFilters 
---

# {{ page.title }} 

## Category

**{{ page.tool }}**

## Description

### Summary

This filter produces the unique regions of two masks.

### Detailed Description

The boolean XOR filter will input two mask layers and output the unique union regions of the two masks, i.e., the pixels that are masked by exactly one of the two input masks. This filter is the same as removing the result of the boolean AND filter from the result of the boolean OR filter.

{% capture url %}{% include url.md%}{% endcapture %}
{{ url }}

