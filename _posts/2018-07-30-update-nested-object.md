---
layout: post
title:  Update nested object in Vue.js
mathjax: false
comments: false
share: false
mathjax: false
tags:
- javascript
---

Update nested object in Vue.js
<!--more-->
``` javascript
let aiVue = null;
let ai = something;

if (aiVue) {
    aiVue.$data.player = ai;
    // this would update the object and the nested object
} else {
    aiVue = new Vue({
        el: '#divAi',
        data: {
            player: ai
        }
    })
}
```

``` html
<span v-for="some in player.someCollection" v-html="some.toHtml()"></span>
<span>Hand: {% raw  %}{{ player.someCollection.length }}{% endraw %} </span>
```
