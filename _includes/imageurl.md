{% capture imageurl %}../images/{%endcapture%}
{{ imageurl | append: page.title | append: "GUI.png"}}
![alt text]({{imageurl}})
