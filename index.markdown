---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
---
{% assign postsByYearMonth = site.posts | group_by_exp:"post", "post.date | date: '%Y %b'"  %}
{% for yearMonth in postsByYearMonth %}
<h3>{{ yearMonth.name }}</h3>
<ul>
  {% for post in yearMonth.items %}
  <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.date | date: '%B %d, %Y' }} {{ post.title }}</a></li>
  {% endfor %}
</ul>
{% endfor %}
