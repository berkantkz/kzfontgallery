---
title: Font Gallery
permalink: /
---

{% assign fontsAvailable = "" | split: ',' %}{% for font in site.static_files %}{% if font.path contains 'fonts' %}{% if font.name contains 'hwt' %}{% assign fontsAvailable = fontsAvailable | push: font %}{% endif %}{% endif %}{% endfor %}

## Currently available fonts
{% for font in fontsAvailable %}
{% assign name = font.basename | replace: '_', ' ' |split: '-' %}
* {{name[0]}}
{% endfor %}