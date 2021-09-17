### `insertdatetime_element`

When this option is enabled HTML5 time elements gets generated when you insert dates/times.

**Type:** `Boolean`

**Possible Values:** `true`, `false`

#### Example: Using `insertdatetime_element`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'insertdatetime',
  menubar: 'insert',
  toolbar: 'insertdatetime',
  insertdatetime_element: true
});
```
