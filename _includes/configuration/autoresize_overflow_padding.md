### `autoresize_overflow_padding`

This option allows you to specify the size of the `padding` at the sides of the editor's `body` set on initialization.

**Type:** `Number`

#### Example: `autoresize_overflow_padding`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'autoresize',
  autoresize_overflow_padding: 50
});
```
