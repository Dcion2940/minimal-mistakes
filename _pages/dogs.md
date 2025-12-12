---
permalink: /dogs/
layout: single
title: "狗狗圖鑑"
author_profile: false
---

用粉紅與蕾絲點綴的鄉村風小鎮，準備好陪妳一起逛逛 10 種狗狗的故事。從小巧的博美到聰明的邊境牧羊犬，每篇都整理了適合族群、飼養重點與新手建議。

{% assign dog_posts = site.posts | where_exp: "post", "post.categories contains '狗狗圖鑑'" %}
<div class="dog-grid">
  {% for post in dog_posts %}
  <article class="dog-card">
    <h2 class="dog-card__title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p class="dog-card__meta">更新時間：{{ post.date | date: "%Y-%m-%d" }}</p>
    <p class="dog-card__excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
    <a class="btn btn--rose" href="{{ post.url | relative_url }}">閱讀故事</a>
  </article>
  {% endfor %}
</div>
