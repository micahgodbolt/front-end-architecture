#Hologram

## Hologram Configuration

```yaml
destination: ./docs
documentation_assets: ./doc_assets
code_example_templates: ./code_example_templates
dependencies: ./build
source: ./sass
```

### code_example_templates

```html
<div class="codeExample">
 <div class="exampleOutput">
   <%= rendered_example %>
 </div>
 <div class="codeBlock">
   <div class="highlight">
     <pre><%= code_example %></pre>
   </div>
 </div>
</div>
```



## Hologram Documentation Block

```css

/*doc
---
title: Primary Button
category: Base CSS
---

This is our button

\```html_example
<a class="btn" href="#">Click</a>
\```
*/


.btn {
 color: white;
 background: blue;
 padding: 10px;
 border: none;
 text-decoration: none;
}

```

#SassDoc

## Installing SassDoc

```
$ npm install sassdoc --global
```

## Exploring SassDoc

```
/// A number between 0 and 360 used to find __foreground color__
/// @type Number
/// @access private
$foreground-adjust: 180 !global;

```

## Digging Deep into SassDoc

```
/// Our global button padding
/// @access private
$button-padding: 1em !global;

/// Our global button font-size
/// @access private
$button-font-size: 1.2em !global;

/// A number between 0 and 360
/// @type number
/// @access private
$foreground-adjust: 180 !global;

/// Function to return a foreground color based
 on a background color
/// @access private
/// @param {color} $color - The background color
/// @return {color}
/// @example
///   @function get_foreground(blue);
///   // yellow
@function get_foreground($color) {
 @return adjust_hue($color, $foreground-adjust);
}

/// Our core button styles
/// @access private
%btn-core {
 padding: $button-padding;
 text-decoration: none;
 font-size: $button-font-size;
}

/// Our basic button mixin
/// @access public
/// @param {Color} $bg_color [red] - Background Color
@mixin button($bg_color:"red") {
 background: $bg_color;
 color: get_foreground($bg_color);
 @extend %btn-core;
}
```
