---
layout: default
title: 'Post'
tags: [github]
comments : true
---

<div class="post">
  ... 생략 ...
</div>

{% if page.comments %}
<div id="post-disqus" class="container">
{% include disqus.html %}
</div>
{% endif %}
