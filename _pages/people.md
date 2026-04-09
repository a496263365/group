---
layout: archive
title: "课题组成员"
author_profile: false
permalink: /people/
---

{% include base_path %}

<style>
.people-section {
  margin-bottom: 50px;
}

.people-section h2 {
  font-size: 1.5rem;
  color: #333;
  padding-bottom: 10px;
  margin-bottom: 25px;
}

.people-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
  gap: 25px;
  padding: 0;
  list-style: none;
}

.person-card {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #fff;
  border-radius: 12px;
  padding: 20px 15px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
  transition: transform 0.2s, box-shadow 0.2s;
  text-align: center;
  text-decoration: none;
  color: inherit;
}

.person-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 6px 20px rgba(0,0,0,0.12);
}

.person-avatar {
  width: 110px;
  height: 110px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 15px;
  border: 3px solid #e8e8e8;
  background-color: #f0f0f0;
}

.person-avatar-placeholder {
  width: 110px;
  height: 110px;
  border-radius: 50%;
  margin-bottom: 15px;
  border: 3px solid #e8e8e8;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 2rem;
  font-weight: bold;
}

.person-name {
  font-size: 1.1rem;
  font-weight: 600;
  color: #333;
  margin-bottom: 8px;
}

.person-info {
  font-size: 0.85rem;
  color: #666;
  line-height: 1.4;
}

.person-type {
  display: inline-block;
  padding: 2px 10px;
  background: #f0f7ff;
  color: #4a90d9;
  border-radius: 12px;
  font-size: 0.8rem;
  margin-top: 6px;
}

.section-divider {
  margin: 15px 0;
  border: 0;
  border-top: 1px dashed #e0e0e0;
}
</style>

{%- comment -%}
分组顺序定义
{%- endcomment -%}
{% assign groups_order = "负责人,博士研究生,硕士研究生,本科生,已毕业学生" | split: "," %}

{% for group_name in groups_order %}

  {%- comment -%} 收集当前分组的成员 {%- endcomment -%}
  {% assign group_keys = "" | split: "," %}
  {% assign group_orders = "" | split: "," %}

  {% for item in site.data.authors %}
    {% assign key = item[0] %}
    {% assign data = item[1] %}
    {% if data.group == group_name %}
      {% assign group_keys = group_keys | push: key %}
      {% assign group_orders = group_orders | push: data.order %}
    {% endif %}
  {% endfor %}

  {% if group_keys.size > 0 %}
    {%- comment -%} 按 order 排序 {%- endcomment -%}
    {% assign tuples = "" | split: "," %}
    {% for i in (0..group_keys.size) %}
      {% unless forloop.last %}
        {% assign key = group_keys[i] %}
        {% assign order = group_orders[i] %}
        {% assign tuple = order | append: "|" | append: key %}
        {% assign tuples = tuples | push: tuple %}
      {% endunless %}
    {% endfor %}
    {% assign sorted_tuples = tuples | sort %}

  <div class="people-section">
      <h2>{{ group_name }}</h2>
      <ul class="people-grid">
        {% for tuple in sorted_tuples %}
          {% assign parts = tuple | split: "|" %}
          {% assign key = parts[1] %}
          {% assign data = site.data.authors[key] %}
          {% assign person_file = data.key | replace: " ", "-" %}
          {% assign first_char = data.name | slice: 0 %}

          <a href="{{ base_path }}/people/{{ person_file }}/" class="person-card">
            {% if data.avatar and data.avatar != "profile.png" and data.avatar != "" %}
              <img src="{{ base_path }}/images/{{ data.avatar }}" alt="{{ data.name }}" class="person-avatar">
            {% else %}
              <div class="person-avatar-placeholder">{{ first_char }}</div>
            {% endif %}

            <div class="person-name">{{ data.name }}</div>

            {% if group_name == "已毕业学生" %}
              {% if data.year %}<div class="person-info">{{ data.year }}年</div>{% endif %}
              {% if data.degree %}<span class="person-type">{{ data.degree }}</span>{% endif %}
            {% else %}
              {% if data.grade and data.grade != "" %}
                <div class="person-info">{{ data.grade }}</div>
              {% endif %}
              {% if data.type and data.type != "" %}
                <span class="person-type">{{ data.type }}</span>
              {% endif %}
            {% endif %}
          </a>
        {% endfor %}
      </ul>
    </div>

    {% unless forloop.last %}
    {% endunless %}

  {% endif %}
{% endfor %}
