---
permalink: /album/
title: "狗狗相簿"
layout: single
author_profile: false
header:
  overlay_color: "#f7e4ee"
  overlay_filter: "0.24"
  caption: "每一次按下快門的甜蜜"
---

這本相簿會自動收集 `assets/dogs` 目錄下的所有照片，新增或刪除檔案後只要重新部署網站，相簿就會同步更新，永遠和你的最新收藏保持一致。

{% assign dog_photos = site.static_files
  | where_exp: "file", "file.path contains '/assets/dogs/'"
  | where_exp: "file", "file.extname != '.md'"
  | sort: "path" %}

{% if dog_photos.size > 0 %}
> 目前共有 **{{ dog_photos.size }}** 張照片，拉到下方細細欣賞吧！

<div class="gallery">
  {% for photo in dog_photos %}
    {% assign photo_label = photo.name | remove: photo.extname %}
    <figure class="third">
      <a href="{{ photo.path | relative_url }}">
        <img src="{{ photo.path | relative_url }}" alt="{{ photo_label }} 的照片">
      </a>
      <figcaption>{{ photo_label }}</figcaption>
    </figure>
  {% endfor %}
</div>
{% else %}
> 目前還沒有上傳任何照片，快把毛孩的可愛身影放進 `assets/dogs` 吧！
{% endif %}
