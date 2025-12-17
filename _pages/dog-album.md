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

{% assign dog_photos = site.static_files
  | where_exp: "file", "file.path contains '/assets/dogs/'"
  | where_exp: "file", "file.extname != '.md'"
  | sort: "path" %}

{% if dog_photos.size > 0 %}
> 目前共有 **{{ dog_photos.size }}** 張照片，拉到下方細細欣賞吧！

<style>
  .dog-album-grid {
    display: grid;
    grid-template-columns: repeat(3, minmax(0, 1fr));
    gap: 1.25rem;
    align-items: start;
  }

  @media (max-width: 900px) {
    .dog-album-grid {
      grid-template-columns: repeat(2, minmax(0, 1fr));
    }
  }

  @media (max-width: 600px) {
    .dog-album-grid {
      grid-template-columns: 1fr;
    }
  }

  .dog-album-grid figure {
    margin: 0;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 0.4rem;
  }

  .dog-album-grid img {
    width: 240px;
    height: 240px;
    border-radius: 0.5rem;
    display: block;
    object-fit: cover;
    object-position: center;
  }

  .dog-album-grid figcaption {
    text-align: center;
    font-weight: 600;
  }
</style>

<div class="dog-album-grid">
  {% for photo in dog_photos %}
    {% assign photo_label = photo.name | remove: photo.extname %}
    <figure>
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
