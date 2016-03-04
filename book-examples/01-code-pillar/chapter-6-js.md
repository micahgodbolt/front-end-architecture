## Create Reusable Functions

### Not Reusable

```js
$('.red-alert')
   .css('background-color', "red")
   .on('click', function() {
    console.log($(this).html());
});

$('.yellow-alert')
   .css('background-color', "yellow")
   .on('click', function() {
    console.log($(this).html());
});
```

### More Reusable

```js
$.fn.log_text_on_click = function() {
  this.on('click', function() {
    console.log($(this).html());
  });
  return this;
};

$.fn.add_background = function(color) {
  this.css('background-color', color);
  return this;
}

$('.red-alert').add_background("red").log_text_on_click();
$('.yellow-alert').add_background("yellow").log_text_on_click();
```
