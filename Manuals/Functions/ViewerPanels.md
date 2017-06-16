---
layout: default
title: ViewerPanels 
category: FunctionDocs 
function: 
  chapter: Seg3DViewer
  subchapter: 
---

# {{ page.title }} 

## Category

**{{ page.function.chapter }}**

## Description

<figure>
  <img src="../Manuals/Seg3DBasicFunctionality_figures/layout_blank.pdf" id="blank">
  <figcaption>Figure 3.1 Seg3D interface.</figcaption>
</figure>

As seen in [Figure 3.1](#blank), there are a number of viewer panels in Seg3D, though the exact number can be set (see [Section 3.4](#ViewingOptions.md)). Each of these viewer windows can be changed in size and in type. The type options are: volume, axial, sagittal, and coronal. The names of the 2D planes can be changed by the user in preferences ([Sec. 5.4](Preferences.md)). You can change the view of each pane by clicking on the view name and choosing the view to change it too. This is a drop down menu, so you can scroll over the name and the view will also change. There are also shortcuts to change views (V–Volume, X–Sagittal, Y–Coronal, and Z–Axial). There are several icons in each view panel, as well as mouse and keyboard shortcuts. The controls for each of the 2D viewers will be described below, as will the controls for the 3D volume viewer.

{% comment %}from https://gist.github.com/pepelsbey/9334494{% endcomment %}
{% capture toolpages %}
  {% for page in site.pages %}
    {% if page.function.subchapter == "ViewerPanels" %}${{ page.title }}#{{ page.url | prepend: site.github.url }}
    {% endif %}
  {% endfor%}
{% endcapture %}

{% assign pageitems = toolpages | strip | strip_newlines | split: '$' %}
{% if pageitems[0] %}
  {% for item in pageitems %}
    {%if forloop.first %} {% continue %} {% endif %}
    {% assign linkitem = item | split: '#' %}
**[{{ linkitem[0] }}]({{ linkitem[1] }})**
  {% endfor %}
{% endif %}

{% capture url %}{% include functionurl.md%}{% endcapture %}
{{ url }}

