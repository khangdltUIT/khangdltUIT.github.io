---
layout: page
tittle: IELTS
permalink: /ielts/
---

<div class="posts">
  {% for post in site.categories.ielts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      
      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
      
      <div class="date">
        {{ page.date | date: "%B %e, %Y" }}
      </div>

    </article>
  {% endfor %}
</div>