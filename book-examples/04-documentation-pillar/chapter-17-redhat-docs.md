## A Static Style Guide

```md
  <!-- cta.docs.md -->

  ---
  hologram: true
  title: CTA Component
  category: Component - CTA
  ---

  - A "Call-to-Action" component contains one or more CTA buttons.

  ## Primary Button

  \```html_example
   {% include "cta.twig" with {'type': 'primary'} %}
  \```

  ## Secondary Button

  \```html_example
   {% include "cta.twig" with {'type': 'secondary} %}
  \```
```

```html
<!-- cta.twig -->
<div class="rh-cta" >
   <a class="rh-cta-link" data-rh-cta-type="{{type}}" href="#">
    CTA Button
  </a>
</div>
```

### Resulting File After Twig

```html
  <!-- cta.docs.md -->

  ---
  hologram: true
  title: CTA Component
  category: Component - CTA
  ---

  - A "Call-to-Action" component contains one or more CTA buttons.

  ## Primary Button

  \```html_example
  <div class="rh-cta" >
     <a class="rh-cta-link" data-rh-cta-type="primary" href="#">
      CTA Button
    </a>
  </div>
  \```

  ## Secondary Button
  \```html_example
  <div class="rh-cta" >
     <a class="rh-cta-link" data-rh-cta-type="secondary" href="#">
      CTA Button
    </a>
  </div>
  \```
  
```
## We Just Reinvented Pattern Lab

```html
{% set template = 'cta.twig' %}

{% include template  %}
```

```md
<!-- card.docs.md -->

---
hologram: true
title: Card Layout
category: Layout - Card
---

{%
 set data = {
   "theme": "dark",
   "components": [
     {
       "template": "image_embed.twig",
       "src": "my-image.jpg"
     },
     {
       "template": "cta.twig",
       "type": "primary"
     }
   ]
 }
%}

{% include card.twig with data %}

<!-- end card.docs.md -->
```

```html
<!-- card.twig -->

<div class="rh-card data-rh-theme="{{theme}}">
 {% for component in components %}
   {% include component.template with component only %}
 {% endfor %}
</div>

<!-- end card.twig -->
```

### JSON Schemas

```json
{
   "template": "band.twig",
   "theme": "dark",
   "components": [
     {
       "template": "cta.twig",
       "type": "tertiary"
     }
   ]
 }
 ```
