## Pattern Lab in Action

```html
<!-- 00-homepage.mustache -->

{{> templates-homepage }}
```

```json
<!-- 00-homepage.json -->

{
 "title" : "Home Page",
 "bodyClass": "home",
 "hero" : [
   {
     "img": {
       "landscape-16x9": {
         "src": "../../images/sample/16x9-mountains.jpg",
         "alt": "Mountains"
       }
     },
     "headline" : {
       "medium" : "Top 10 mountain ranges for hiking"
     }
   }
 ],
 "touts" : [
   ...
 ],
 "latest-posts" : [
  ...
 ]
}
```

```html
<!-- 00-homepage.mustache -->

<div class="page" id="page">
 {{> organisms-header }}
 <div role="main">
   {{# hero }}
     {{> molecules-block-hero }}
   {{/ hero}}
   <div class="g g-3up">
     {{# touts}}
       <div class="gi">
         {{> molecules-inset-block }}
       </div>
     {{/ touts}}
   </div><!--end 3up-->
   <hr />
   <div class="l-two-col">
     <div class="l-main">
       <section class="section latest-posts">
         <h2 class="section-title">Latest Posts</h2>
         <ul class="post-list">
           {{# latest-posts }}
             <li>{{> molecules-media-block }}</li>
           {{/ latest-posts }}
         </ul>
         <a href="#" class="text-btn">View more posts</a>
       </section>
     </div><!--end .l-main-->
     <div class="l-sidebar">
       {{> organisms-recent-tweets }}
     </div><!--end .l-sidebar-->
   </div><!--end .l-two-col-->
 </div><!--End role=main-->
 {{> organisms-footer }}
</div>
```

## Homepage Template

```html
{{# hero }}
     {{> molecules-block-hero }}
{{/ hero}}
```

```json
{
  "img": {
   "landscape-16x9": {
     "src": "../../images/sample/landscape-16x9-mountains.jpg",
     "alt": "Mountains"
   }
  },
  "headline" : {
   "medium" : "Top 10 mountain ranges for hiking"
  }
}
```

```html
<div class="block block-hero">
 <a href="{{ url }}" class="inner">
   <div class="b-thumb">
     {{> atoms-landscape-16x9 }}
   </div>
   <div class="b-text">
     <h2 class="headline">{{ headline.medium }}</h2>
   </div>
 </a>
</div>
```


## Our First Variables

```json
{
   "url": "http://www.google.com",
   "img": {
       "landscape-16x9": {
           "src": "../../images/sample/16x9-mountains.jpg",
           "alt": "Mountains"
       }
   },
   "headline" : {
       "medium" : "Top 10 mountain ranges for hiking"
   }
}
```


## Going Atomic

```html
<!-- 02-landscape-16x9.mustache -->
<img src="{{ img.16x9.src }}" alt="{{ img.16x9.alt }}" />
```
