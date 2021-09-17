### `save_onsavecallback`

This option allows you to specify the function that will be executed when the save button/command is invoked.

**Type:** `String`

#### Example: Using `save_onsavecallback`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  plugins: 'save',
  toolbar: 'save',
  save_onsavecallback: function () { console.log('Saved'); }
});
```
