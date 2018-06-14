## CSS

I seem to always forget how the class is applied when it's like this:

```css
.first .second {
  border: 1px solid red;
}
```

This means, apply the following styles in `.second` class, which is nested inside `.first` class.

```html
<div class="first">
  <div class="second">

  </div>
</div>
```

If the css classes don't have space between them, e.g.:

```css
.first.second {
  border: 1px solid red;
}
```

This would mean:

```html
<div class="first second">

</div>
```
