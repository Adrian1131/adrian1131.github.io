---
title: Updates
icon: fas fa-newspaper
order: 4
---

Posts and progress updates from what I am building and learning.

{% assign updates = site.posts %}

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
No updates yet. Add a post in `_posts/` with front matter like:

```yaml
---
title: "Your Post Title"
date: 2026-04-08 12:00:00 -0400
---
```
{% endif %}
