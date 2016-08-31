{% assign relative-baseurl = "" %}
{% assign cannon = page.url | append: "page.html" | split: "/" %}
{% for item in cannon offset:2 %}
  {% assign relative-baseurl = relative-baseurl | append:"../images/" | append page.title | append "GUI.png" %}
{% endfor%} 
[Seg3D image]({{ relative-baseurl }}tools.md

