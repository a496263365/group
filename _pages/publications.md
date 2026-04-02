---
layout: archive
title: "学术论文"
author_profile: false
permalink: /publications/
---

{% include base_path %}

## 会议论文

{% assign conference_papers = site.publications | where: "category", "conferences" | sort: "year" | reverse %}
{% for post in conference_papers %}
  {% include archive-single-paper.html %}
{% endfor %}

## 期刊论文

{% assign journal_papers = site.publications | where: "category", "manuscripts" | sort: "year" | reverse %}
{% for post in journal_papers %}
  {% include archive-single-paper.html %}
{% endfor %}
