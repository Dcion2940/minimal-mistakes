---
permalink: /dog-gallery/
title: "狗狗相簿"
layout: single
author_profile: false
classes: wide
gallery_images:
  - file: 博美犬1.png
    caption: "博美犬 1"
    alt: "博美犬的照片"
  - file: 博美犬2.png
    caption: "博美犬 2"
    alt: "博美犬的照片"
  - file: 博美犬3.png
    caption: "博美犬 3"
    alt: "博美犬的照片"
  - file: 哈士奇1.png
    caption: "哈士奇 1"
    alt: "哈士奇的照片"
  - file: 哈士奇2.png
    caption: "哈士奇 2"
    alt: "哈士奇的照片"
  - file: 哈士奇3.png
    caption: "哈士奇 3"
    alt: "哈士奇的照片"
  - file: 德國牧羊犬1.png
    caption: "德國牧羊犬 1"
    alt: "德國牧羊犬的照片"
  - file: 德國牧羊犬2.png
    caption: "德國牧羊犬 2"
    alt: "德國牧羊犬的照片"
  - file: 德國牧羊犬3.png
    caption: "德國牧羊犬 3"
    alt: "德國牧羊犬的照片"
  - file: 拉布拉多1.png
    caption: "拉布拉多 1"
    alt: "拉布拉多的照片"
  - file: 拉布拉多2.png
    caption: "拉布拉多 2"
    alt: "拉布拉多的照片"
  - file: 拉布拉多3.png
    caption: "拉布拉多 3"
    alt: "拉布拉多的照片"
  - file: 柴犬1.png
    caption: "柴犬 1"
    alt: "柴犬的照片"
  - file: 柴犬2.png
    caption: "柴犬 2"
    alt: "柴犬的照片"
  - file: 柴犬3.png
    caption: "柴犬 3"
    alt: "柴犬的照片"
  - file: 法國鬥牛犬1.png
    caption: "法國鬥牛犬 1"
    alt: "法國鬥牛犬的照片"
  - file: 法國鬥牛犬2.png
    caption: "法國鬥牛犬 2"
    alt: "法國鬥牛犬的照片"
  - file: 法國鬥牛犬3.png
    caption: "法國鬥牛犬 3"
    alt: "法國鬥牛犬的照片"
  - file: 米格魯1.png
    caption: "米格魯 1"
    alt: "米格魯的照片"
  - file: 米格魯2.png
    caption: "米格魯 2"
    alt: "米格魯的照片"
  - file: 米格魯3.png
    caption: "米格魯 3"
    alt: "米格魯的照片"
  - file: 貴賓犬1.png
    caption: "貴賓犬 1"
    alt: "貴賓犬的照片"
  - file: 貴賓犬2.png
    caption: "貴賓犬 2"
    alt: "貴賓犬的照片"
  - file: 貴賓犬3.png
    caption: "貴賓犬 3"
    alt: "貴賓犬的照片"
  - file: 邊境牧羊犬1.png
    caption: "邊境牧羊犬 1"
    alt: "邊境牧羊犬的照片"
---

用輕鬆的速度欣賞每一張毛孩的模樣，感受牠們在日常中的可愛瞬間。

<div class="dog-gallery-grid">
  {% for photo in page.gallery_images %}
  <figure class="dog-gallery-item">
    <img src="/assets/dogs/{{ photo.file }}" alt="{{ photo.alt }}">
    <figcaption>{{ photo.caption }}</figcaption>
  </figure>
  {% endfor %}
</div>

<style>
.dog-gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 1rem;
}

.dog-gallery-item {
  margin: 0;
  padding: 0.5rem;
  border-radius: 12px;
  background: #f8e9f1;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.06);
}

.dog-gallery-item img {
  width: 100%;
  height: 210px;
  object-fit: cover;
  border-radius: 8px;
  display: block;
}

.dog-gallery-item figcaption {
  margin-top: 0.5rem;
  text-align: center;
  color: #7b4b67;
  font-weight: 600;
}
</style>
