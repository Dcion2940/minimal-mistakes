---
permalink: /dogs/album/
title: "狗狗相簿"
layout: single
author_profile: false
---

想看看所有狗狗的可愛瞬間嗎？這裡會自動收集 `assets/dogs` 資料夾裡的所有照片，只要在 GitHub 上新增或刪除圖片，下一次部落格建置時相簿就會同步更新。

{% assign dog_photos = site.static_files
  | where_exp: "file", "file.path contains '/assets/dogs/'"
  | where_exp: "file", "file.extname != '.md'"
  | sort: "name" %}
{% assign photo_count = dog_photos | size %}

目前相簿共有 **{{ photo_count }} 張照片**。

<div class="gallery third">
  {% for photo in dog_photos %}
    <figure class="gallery-item">
      <a href="{{ photo.path | relative_url }}">
        <img src="{{ photo.path | relative_url }}" alt="{{ photo.basename | escape }}" loading="lazy" />
      </a>
      <figcaption>{{ photo.basename }}</figcaption>
    </figure>
  {% endfor %}
</div>
