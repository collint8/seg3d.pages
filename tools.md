---
title: Seg3d Tool Documentation
category: info 
---

# Seg3d Tools

{% comment %}from https://gist.github.com/pepelsbey/9334494{% endcomment %}
{% capture tmp %}
{% for page in site.pages %}{% if page.category == "ToolDocs" %} {{ page.tool}} {% endif %}{% endfor %}
{% endcapture %}

{% assign categories = tmp | split: ' ' %}
{% assign tmp = categories[0] %}

{% for cat in categories %}
  {% unless tmp contains cat %}
    {% capture tmp %}{{ tmp }} {{ cat }}{% endcapture %}
  {% endunless %}
{% endfor %}

{% assign toolcategories = tmp | split: ' ' %}

{% capture toolpages %}
  {% for cat in toolcategories %}?{{ cat }}
    {% for page in site.pages %}
      {% if page.tool == cat %}${{ page.title }}#{{ page.url | prepend: site.github.url }}
      {% endif %}
    {% endfor%}
  {% endfor %}
{% endcapture %}

{% assign sortedpages = toolpages | strip | strip_newlines | split: '?' | sort %}

{% for pagestring in sortedpages %}
  {% assign pageitems = pagestring | split: '$' %}
  {% if pageitems[0] %}
## {{ pageitems[0] }}
    {% for item in pageitems %}
      {% comment %}skip category list item (index 0){% endcomment %}
      {% if forloop.first %} {% continue %} {% endif%}
      {% assign linkitem = item | split: '#' %}
**[{{ linkitem[0] }}]({{ linkitem[1] }}){:target="_blank"}**
    {% endfor %}
  {% endif %}
{% endfor %}
