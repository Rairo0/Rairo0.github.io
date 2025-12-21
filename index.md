---
layout: home
# Index page
---
{% for post in site.posts %}
<article class="post-item">
  <a href="{{ post.url | relative_url }}">
    {% if post.image %}
    <img src="{{ post.image | relative_url }}" alt="{{ post.title }}" style="max-width:200px;">
    {% endif %}
    <h2>{{ post.title }}</h2>
  </a>
  <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
  <p class="post-meta">{{ post.date | date: "%Y-%m-%d" }} — {{ post.categories | array_to_sentence_string }}</p>
</article>
{% endfor %}
