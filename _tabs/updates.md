---
title: Updates
icon: fas fa-newspaper
order: 4
---

Posts and progress updates from what I am building and learning.

{% assign updates = site.posts | where_exp: "post", "post.categories contains 'Updates' or post.categories contains 'updates'" %}

{% if updates.size > 0 %}
{% for post in updates %}
## [{{ post.title }}]({{ post.url | relative_url }})
**{{ post.date | date: "%B %-d, %Y" }}**

{% if post.excerpt %}
{{ post.excerpt | strip_html | truncate: 180 }}
{% endif %}

---
{% endfor %}
{% else %}
No updates yet. Add a post in `_posts/` with:

```yaml
categories: [Updates]
```
{% endif %}
