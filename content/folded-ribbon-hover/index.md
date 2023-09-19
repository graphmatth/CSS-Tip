---
layout: layouts/post.njk
title: Folded Ribbon Shape with hover effect
description: a fancy ribbon shape with a nice hover effect
date: 2023-09-19
tags: posts
---

Turn your title into a fancy Ribbon Shape 🎀
* One element (no complex HTML)
* Optimized with CSS variables
* Cool animation on hover


{% image "./image.png", "A folded ribbon shape" %}

```css
@property --d {
  syntax: "<length>";
  initial-value: 0px;
  inherits: true;
}

h1 {
  --r: 20px; /* control the cutout of the ribbon */
  --s: 20px; /* size of the folded part */
  --c: #d81a14;
  
  --d: 0px; /* This will control the animation part */
  line-height: 1.6; /* control the height */
  padding-inline: 1.2lh calc(var(--r) + .2lh);
  background: linear-gradient(#0000 40%,#0002) var(--c);
  clip-path: polygon(calc(1lh + var(--d)) 0,100% 0,calc(100% - var(--r)) 50%,100% 100%,100% 999px, var(--d) 999px,var(--d) 100%);
  position: relative;
  transition: --d .3s linear;
}
h1:before {
  content:"";
  position: absolute;
  top: 100%;
  left: var(--d);
  width: 1lh;
  height: calc(var(--s) + var(--r) + var(--d));
  background: linear-gradient(#0005,#0000 20%) var(--c);
  clip-path: polygon(0 0,100% 0,100% calc(100% - var(--r)),50% 100%,0 calc(100% - var(--r)));
}
h1:hover {
  --d: .2lh; /* don't use a big value to not cut the text */
}
```

<p class="codepen" data-height="450" data-default-tab="result" data-slug-hash="KKbyPbM" data-preview="true" data-user="t_afif" style="height: 450px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/t_afif/pen/KKbyPbM">
  CSS-only Ribbon with a nice hover effect</a> by Temani Afif (<a href="https://codepen.io/t_afif">@t_afif</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
