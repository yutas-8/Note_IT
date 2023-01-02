---
title: Thymeleafについて
date: 
description: 
tags: ['MT']
category: HTML
---

## Thymeleafについて

### th:if

```html
<div th:if = "${条件}">
    <!-- 条件がtrueの場合にこのタブと内部にあるタブを表示する -->
</div>
```

### th:unless

```html
<div th:unless = "${条件}">
    <!-- 条件がfalseの場合にこのタブと内部にあるタブを表示する -->
</div>
```

- `th:if`と組み合わせることにより、`if else if`をHTML上で作り出すことができる。
