---
title: Categories
icon: fas fa-folder-open
order: 6
---

Browse posts by category.

{% assign sorted_categories = site.categories | sort %}
{% if sorted_categories.size > 0 %}
{% for category in sorted_categories %}
{% assign name = category[0] %}
{% assign posts = category[1] %}
- [{{ name }}]({{ '/categories/' | append: name | slugify | append: '/' | relative_url }}) ({{ posts | size }})
{% endfor %}
{% else %}
No categories yet.
{% endif %}
