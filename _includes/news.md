{% assign news_limit = 10 %}
<h2 id="news">News</h2>

<ul class="news-list">
{% for item in site.data.news limit: news_limit %}
  <li><strong>[{{ item.date }}]</strong> {{ item.text }}</li>
{% endfor %}
</ul>

{% if site.data.news.size > news_limit %}
<details class="news-more">
  <summary><span class="show-more">Show more</span><span class="show-less">Show less</span></summary>
  <ul class="news-list">
  {% for item in site.data.news offset: news_limit %}
    <li><strong>[{{ item.date }}]</strong> {{ item.text }}</li>
  {% endfor %}
  </ul>
</details>
{% endif %}
