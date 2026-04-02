---
layout: archive
title: "最新动态"
author_profile: false
permalink: /news/
---

{% include base_path %}

<ul>
  {% assign posts = site.posts | sort: "date" | reverse %}
  {% for post in posts %}
    <li>
      <span>{{ post.date | date: "%Y-%m-%d" }}</span>
      — <a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

{% if posts.size == 0 %}
<p>暂无最新动态。</p>
{% endif %}

<style>
ul {
  list-style-type: none;
  padding-left: 0;
}
li {
  margin: 15px 0;
  padding: 10px;
  border-left: 3px solid #4a90d9;
  padding-left: 15px;
}
li:hover {
  background-color: #f9f9f9;
}
span {
  color: #666;
  font-size: 0.9em;
}
</style>