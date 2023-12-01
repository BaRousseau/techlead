# CSS Web Component

## Hide Web Component until it's defined in JavaScript

The CSS `:defined` pseudo-class applies to an element when it’s been defined in the browser.

For Web Components, that doesn’t happen until the `customElements.define()` method has been run on your custom element, which is JavaScript !

```css
/* Hide the <count-up> element until it's defined */
count-up:not(:defined) {
  display: none;
}
```

No need to handle it in JavaScript.
