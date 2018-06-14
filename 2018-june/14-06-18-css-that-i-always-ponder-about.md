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

`.first` class is the parent selector and `.second` is the child selector.

In SCSS, you can apply the styles like so:

```SCSS
.first {
  border: 1px solid blue;
  .second {
    border: 1px solid red;
  }
}
```

which then compiles to:

```CSS
.first {
  border: 1px solid blue;
}

.first .second {
  border: 1px solid red;
}
```

I asked myself, why would you want `.first` if you're only targeting `.second`?

But if you only want to target the `.second` class within the `.first` then you would use this css. Otherwise if you only target `.second`, it will target all your elements with `.second` class regardless of whether it's nested within `.first` class or not.

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
