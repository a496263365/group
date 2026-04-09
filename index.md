---
layout: single
title: "软件复用研究组"
author_profile: false
---

{% include base_path %}

## 欢迎来到软件复用研究组

软件复用研究组（Software Reuse Research Group）隶属于北京大学，是一支专注于软件工程、人工智能和知识图谱领域前沿研究的高水平科研团队。

---

## 研究方向

### 软件工程

软件复用是软件工程领域的重要研究方向，旨在通过复用已有的软件构件来提高软件开发效率和质量。

**研究课题：**
- 软件构件技术
- 软件产品线工程
- 面向服务的架构（SOA）
- 云原生软件工程

### 人工智能

人工智能是当前科技发展的热点，我们关注如何将AI技术应用于软件工程，以及如何开发智能软件系统。

**研究课题：**
- 机器学习与深度学习
- 自然语言处理
- 计算机视觉
- 智能推荐系统

### 知识图谱

知识图谱是一种大规模语义网络，用于描述现实世界中的实体及其关系。

**研究课题：**
- 知识表示与推理
- 知识图谱构建
- 知识增强的AI系统
- 知识图谱应用

---

## 团队组成

| 角色 | 人数 |
|:---:|:---:|
| 负责人（教授/研究员） | 2名 |
| 博士研究生 | 约10名 |
| 硕士研究生 | 约6名 |
| 本科生 | 若干名 |

### 负责人

| 姓名 | 职称 | 研究方向 |
|:---:|:---:|:---:|
| [谢冰](/people/xie-bing/) | 教授 | 软件复用、软件工程 |
| [邹艳珍](/people/zou-yanzhen/) | 研究员 | 知识图谱、人工智能 |

---

## 招生信息

软件复用研究组常年招收博士研究生、硕士研究生和本科生。

### 博士/硕士研究生

欢迎计算机相关专业背景的学生报考，有软件工程、人工智能或知识图谱研究兴趣者优先。

### 本科生

欢迎对软件工程研究感兴趣的同学加入实验室参与科研项目。

---

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

---

## 联系我们

- 邮箱：swreuse@pku.edu.cn
- 地址：北京大学

欢迎关注我们的研究工作，如有任何问题或合作意向，请随时与我们联系。

<style>
section {
  margin-bottom: 40px;
}
h3 {
  color: #333;
  padding-bottom: 10px;
}
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