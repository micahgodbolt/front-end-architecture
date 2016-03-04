## Specificity Wars and the Pains of Inheritance

```html
<body>
  <div id="main">
    <h2>I'm a Header</h2>
  </div>
  <div id="sidebar">
    <h2>I'm a Sidebar Header</h2>
    <div class="calendar">
      <h2>I'm a Calendar Header</h2>
    </div>
  </div>
</body>

<style>
h2 {
  font-size: 24px;
  color: red;
}

#sidebar h2 {
  font-size: 20px;
  background: red;
  color: white;
}

#sidebar .calendar h2 {
  background: none;
  color: red;
}
</style>
```


## A Modern, Modular Approach

```html
<body>
  <div class="main">
    <h2 class="content__title>"I'm a Header"</h2>
  </div>
  <div class="sidebar">
    <h2 class="content__title--reversed>
      "I'm a Sidebar Header"
    </h2>
    <div class="calendar">
      <h2 class="calendar__title>"I'm a Calendar Header"</h2>
    </div>
  </div>
</body>

<style>

/* Components folder */
.content__title {
  font-size: 24px;
  color: red;
}

.content__title--reversed {
  font-size: 20px;
  background: red;
  color: white;
}

.calendar__title {
  font-size: 20px;
  color: red;
}

/* Layout folder */
.main {
  float: left;
  ...
}
.sidebar {
  float: right;
  ...
}
</style>
```

## Single Responsibility Principle

```html
<div class="calendar">
  <h2 class="calendar-header">This Is a Calendar Header</h2>
</div>

<div class="blog">
  <h2 class="blog-header">This Is a Blog Header</h2>
</div>

<style>
.calendar-header {
  color: red;
  font-size: 2em;
}

.blog-header {
  color: red;
  font-size: 2.4em;
}
</style>
```



## Single Source of Truth

### Poor Approach

```html
<div class="blog">
  <h2 class="blog-header">This Is a Blog Header</h2>
  ...
  <div class="calendar">
    <h2 class="calendar-header">This Is a Calendar Header</h2>
  </div>
</div>
```

```css
/* calendar.css */
.calendar-header {
  color: red;
  font-size: 2em;
}

/* blog.css */
.blog-header {
  color: red;
  font-size: 2.4em;
}

.blog .calendar-header {
  font-size: 1.6em;
}
```

### A Better Approach

```html
<div class="blog">
  <h2 class="blog-header">This Is a Blog Header</h2>
  ...
  <div class="calendar">
    <h2 class="calendar-header">This Is a Calendar Header</h2>
  </div>
</div>
```

```css
/* calendar.css */
.calendar-header {
  color: red;
  font-size: 2em;
}

.blog .calendar-header {
  font-size: 1.6em;
}

/* blog.css */
.blog-header {
  color: red;
  font-size: 2.4em;
}

```

## Component Modifiers

```html
<div class="blog">
  <h2 class="blog-header">This Is a Blog Header</h2>
  ...
  <div class="calendar calendar--nested">
    <h2 class="calendar-header">This Is a Calendar Header</h2>
  </div>
</div>
```

```css
/* calendar.css */
.calendar-header {
  color: red;
  font-size: 2em;
}

.calendar--nested .calendar-header {
  font-size: 1.6em;
}

/* blog.css */
.blog-header {
  color: red;
  font-size: 2.4em;
}
```
