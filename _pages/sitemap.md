---
layout: archive
title: "Sitemap"
permalink: /sitemap/
author_profile: true
---

[About Me]({{ '/' | relative_url }})

{% for item in site.data.navigation.main %}
- [{{ item.title }}]({{ item.url | relative_url }})
{% endfor %}
