## Style Links Depending on Destination

Today I learned that you can actually target a specific link to style it in css such as:

```
a[href^="http://"] {
  - styling goes here -
}

a[href^="mailto:"] {
  - styling goes hee -
}
```

Further information can be found [here](https://css-tricks.com/snippets/css/style-links-depending-on-destination/).
