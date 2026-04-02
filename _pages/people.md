---
layout: archive
title: "课题组成员"
author_profile: false
permalink: /people/
---

{% include base_path %}

## 负责人

<ul>
  {% for person in site.people %}
    {% if person.title == "谢冰" or person.title == "邹艳珍" %}
    <li><a href="{{ base_path }}{{ person.url }}">{{ person.title }}</a></li>
    {% endif %}
  {% endfor %}
</ul>



<style>
ul {
  list-style-type: none;
  padding-left: 0;
}
li {
  margin: 10px 0;
  padding: 8px 0;
  border-bottom: 1px solid #eee;
}
li:last-child {
  border-bottom: none;
}
a {
  font-weight: 500;
}
section {
  margin-bottom: 40px;
}
</style>
