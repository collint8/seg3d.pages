{% capture tmp %}{{page.function.subchapter}}{% endcapture %}
{% if tmp == null %}
[Back]({{ site.github.url }}/functionality.md)
{% else %}
  {% for page in site.pages %}
    {% if page.title == tmp %}
[Back]({{ page.url | prepend site.github.url }})
    {% endif %}
  {% endfor %}
{% endif %}
