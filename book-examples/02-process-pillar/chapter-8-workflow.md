## Development

```css
.cta {
  background: blue;
  color: white;
  padding: 8px;
}
```

```css
.cta-large {
  background: blue;
  color: white;
  padding: 16px;
}
```

```css
@mixin button($size) {
  background: blue;
  color: white;
  padding: $size;

}

.cta {
 @include button(8px);
}

.cta-large {
 @include button(8px);
}
```

```css
.cta-large {
  padding: 16px;
}

/* Example HTML would be <a class="cta cta-large"> */
```

```css
.cta[data-size="large"] {
 padding: 16px;
}

/* Example HTML would be <a class="cta" data-size="large"> */
```
