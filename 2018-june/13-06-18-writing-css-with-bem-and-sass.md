## Writing CSS with BEM and SASS

I came across a problem today in which css works.

I had this class in my HTML markup:

```html
<div class="message__logo--bottom">
  // content here
</div>
```

and this was my SCSS:

```scss
.message {
  &__logo {
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;

    &--bottom {
      order: 1;
    }
  }
}
```

When I was previewing this in the browser, the CSS didn't render **message\_\_logo** and only rendered **message\_\_logo--bottom**. Turns out, if you want to render **message\_\_logo**, you need to provide your class name in HTML markup like this:

```html
<div class="message__logo message__logo--bottom">
  // content here
</div>
```
