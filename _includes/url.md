{% assign relative-baseurl = "" %}
{% assign cannon = page.url | append: "page.html" | split: "/" %}
{% for item in cannon offset:2 %}
  {% assign relative-baseurl = relative-baseurl | append:"../" %}
{% endfor%} 
[Seg3D Tools]({{ relative-baseurl }}tools.md)
