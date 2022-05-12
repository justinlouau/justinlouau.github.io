---
layout: default
permalink: /articles/
title: "Articles"
---

<div class="container">
  <div id="archives">
    {% for category in site.categories %}
      <div class="archive-group">
        {% capture category_name %}{{ category | first }}{% endcapture %}
        <h2 class="category-title">{{ category_name }}</h2>
        <a name="{{ category_name | slugize }}"></a>

        {% for post in site.categories[category_name] %}
          <article class="post-item">
            <span class="post-meta date-label">{{ category_name }}</span>
            <div class="article-title">
              <a class="post-link" href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
            </div>
          </article>
        {% endfor %}
      </div>
      <br><br>
    {% endfor %}
  </div>
</div>
