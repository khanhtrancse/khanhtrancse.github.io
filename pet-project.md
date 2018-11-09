---
layout: default
---
<div class="col-12 col-lg-9 mx-auto px-0 py-3">
    {% for post in site.posts %}
        {% for cate in post.categories %}
            {% if cate== "pet-project" %}
                {% include post-card.html title=post.title url=post.url summary=post.summary
          date=post.dateString image=post.thumbnail-image categories=post.categories  %}
                {% break %}
            {% endif %}
        {% endfor %}
    {% endfor %}
</div>