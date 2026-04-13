---
layout: archive
title: "专利与软件著作权"
author_profile: false
permalink: /patents/
---

{% include base_path %}

## 专利

{% assign patents = site.patents | where: "category", "patents" | sort: "year" | reverse %}
{% for post in patents %}
  {% include archive-single-patent.html %}
{% endfor %}

## 软件著作权

{% assign software = site.patents | where: "category", "software" | sort: "year" | reverse %}
{% for post in software %}
  {% include archive-single-patent.html %}
{% endfor %}
