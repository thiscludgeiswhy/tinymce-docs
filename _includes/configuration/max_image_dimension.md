### `max_image_dimension`

This option constrains the width and height of uploaded images. When specified, any images with a greater width or height than the specified amount would be proportionally resized down to the specified maximum dimension.

Type
: `Number`

#### Example: Using `max_image_dimension` with the tinydrive.browse API

```js

tinymce.init({
  selector: 'textarea',
  plugins: 'tinydrive image',
  toolbar: 'custombrowse',
  tinydrive_token_provider: 'URL_TO_YOUR_TOKEN_PROVIDER',
  setup: function (editor) {
    editor.ui.registry.addButton('custombrowse', {
      text: 'Custom browse',
      onAction: function () {
        editor.plugins.tinydrive.browse({
          max_image_dimension: 1024
        }).then(function () {
          console.log('Tiny Drive dialog closed.');
        });
      }
    });
  }
});
```