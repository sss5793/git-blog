---
layout: post
title: 댓글 등록하기
parent: 블로그 작성하기
nav_order: 3
---

```html
{% if page.comments %}
<div id="post-disqus" class="container">
{% include disqus.html %}
</div>
{% endif %}
```

#### 댓글
