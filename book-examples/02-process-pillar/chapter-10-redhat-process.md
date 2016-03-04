## Schema Driven Design

```json
{
 "type": "object",
 "properties": {
   "headline": {
     "type": "string",
     "format": "text"
   },
   "body": {
     "type": "object",
     "oneOf": [
       {
         "title": "Two Up",
         "required": ["logos", "layout"],
         "properties": {
           "layout": {
             "type": "string",
             "enum": ["2up"],
             "options": {
               "hidden": true
             }
           },
           "logos": {
             "type": "array",
             "format": "tabs",
             "minItems": 2,
             "maxItems": 2,
             "items": {
               "$ref": "#/definitions/logo"
             }
           }
         }
       },
       {
         "title": "Three Up",
         "properties": {
           "layout": {
             "type": "string",
             "enum": ["3up"],
             "options": {
               "hidden": true
             }
           },
           "logos": {
             "format": "tabs",
             "type": "array",
             "minItems": 3,
             "maxItems": 3,
             "items": {
               "$ref": "#/definitions/logo"
             }
           }
         },
         "required": ["logos", "layout"]
       }
     ]
   }
 },
 "required": ["body"],
 "definitions": {
   "logo": {
     "title": "Logo",
     "type": "object",
     "oneOf": [
       {
         "title": "Upload File",
         "properties": {
           "file": {
             "title": "Logo File",
             "description": "Upload your logo",
             "type": "string",
             "format": "file"
           }
         },
         "required": ["file"]
       },
       {
         "title": "Paste URL",
         "properties": {
           "url": {
             "title": "Logo URL",
             "description": "Paste a URL to your logo",
             "type": "string",
             "format": "url"
           }
         },
         "required": ["url"]
       }
     ]
   }
 }
}
```

## Moving to the Twig File

```json
{
 "headline": "This is my headline",
 "body": {
   "layout": "2up",
   "logos": [
     {
       "url": "http://www.fea.pub/my-logo.png"
     },
     {
       "file": "path/to/my-other-logo.png"
     }
   ]
 }
}
```

```html
<div class="logo-wall">
  {% if headline %}
    <h1 class="logo-wall-headline">{{headline}}</h1>
  {% endif %}
  <div class="logo-wall-logos" data-layout="{{body.layout}}">
    {% for logo in body.logos %}
      <img class="logo-wall-logo"
       src="{{ logo.file ?: logo.url }}" />
    {% endfor %}
  </div>
</div>
```

## [View this is JSON Schema Editor](http://bit.ly/1FKio8h)
