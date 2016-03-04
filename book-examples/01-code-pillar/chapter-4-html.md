## Procedural Markup: 100% Automation, 0% Control

```html
<div id="header" class="clearfix">
  <div id="header-screen" class="clearfix">
    <div id="header-inner" class="container-12 clearfix">
      <div id="nav-header" role="navigation">
        <div class="region region-navigation">
          <div class="block block-system block-menu">
            <div class="block-inner">
              <div class="content">
                <ul class="menu">
                  <li class="first leaf">
                    <a href="/start">Get Started</a>
```

## Static Markup: 0% Automation, 100% Control

```html
<header>
  <section>
    <nav>
      <div>
        <ul>
          <li>
            <a href="/products">Products</a>
            <ul>
              <li>
                <a href="/socks">Socks</a>
```

```css
header > section > nav > div > ul > li > a {
  color: white;
}
header > section > nav > div > ul > li > ul > li > a  {
  color: blue;
}
```


## Modular Markup: 100% Automation, 100% Control

```html
<nav class="nav">
  <ul class="nav__container">
    <li class="nav__item">
      <a href="/products" class="nav__link">
        <ul class="nav__container--secondary">
          <li class="nav__item--secondary">
            <a href="/socks" class="nav__link--secondary">
```

## OOCSS Approach

```html
<div class="toggle simple">
  <div class="toggle-control open">
    <h1 class="toggle-title">Title 1</h1>
  </div>
  <div class="toggle-details open"> ... </div>
  ...
</div>
```

## SMACSS Approach

```html
<div class="toggle toggle-simple">
  <div class="toggle-control is-active">
    <h2 class="toggle-title">Title 1</h2>
  </div>

  <div class="toggle-details is-active">
    ...
  </div>
  ...
</dl>

```


## BEM Approach

```html
<div class="toggle toggle--simple">
  <div class="toggle__control toggle__control--active">
    <h2 class="toggle__title">Title 1</h2>
  </div>

  <div class="toggle__details toggle__details--active">
    ...
  </div>
  ...
</dl>
```
