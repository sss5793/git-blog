---
layout: default
title: 구글 검색엔진 등록하기
parent: 블로그 작성하기
nav_order: 3
comments : true
---

```html
{% if page.comments %}
<div id="post-disqus" class="container">
{% include disqus.html %}
</div>
{% endif %}
```

#### 댓글

{% if page.comments %}
<div id="post-disqus" class="container">
{% include disqus.html %}
</div>
{% endif %}
