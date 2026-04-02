---
layout: single
title: "软件复用研究组"
author_profile: false
---

{% include base_path %}

## 欢迎来到软件复用研究组

软件复用研究组隶属于北京大学，是一支专注于软件工程、人工智能和知识图谱领域的研究团队。

## 研究方向

- **软件工程**：软件复用、软件构件、软件产品线
- **人工智能**：机器学习、深度学习、智能软件系统
- **知识图谱**：知识表示、知识推理、知识工程

## 负责人

| 姓名 | 职称 | 研究方向 |
|:---:|:---:|:---:|
| [谢冰](/people/2024-01-01-xie-bing/) | 教授 | 软件复用、软件工程 |
| [邹艳珍](/people/2024-01-02-zou-yanzhen/) | 研究员 | 知识图谱、人工智能 |

## 组内成员

- **博士后**：若干名
- **博士研究生**：10名
- **硕士研究生**：6名
- **本科生**：若干名

## 最新动态

{% assign posts = site.posts | sort: "date" | reverse | limit: 5 %}
{% if posts.size > 0 %}
<ul>
  {% for post in posts %}
    <li><span>{{ post.date | date: "%Y-%m-%d" }}</span> — <a href="{{ base_path }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
{% else %}
<p>暂无最新动态。请关注我们的 [Publications](/publications/) 页面。</p>
{% endif %}

## 联系我们

- 邮箱：swreuse@pku.edu.cn
- 地址：北京大学

<style>
table {
  width: 100%;
  border-collapse: collapse;
  margin: 20px 0;
}
th, td {
  border: 1px solid #ddd;
  padding: 12px;
  text-align: center;
}
th {
  background-color: #f5f5f5;
}
ul {
  list-style-type: none;
  padding-left: 0;
}
li {
  margin: 10px 0;
}
</style>