### `a11ychecker_allow_decorative_images`

This option sets whether the Accessibility Checker should allow decorative images. When this option is set to `true`, a decorative image must have **both**:

- An empty alternative text attribute.
- The `role="presentation"` attribute.

For example:

```html
<img src="my-image.png" role="presentation" alt="" />
```

If `a11ychecker_allow_decorative_images` is set to `true`, the Accessibility Checker will present an error when:

- An image does not have the alternative text attribute (`alt`).
- An image has an empty alternative text attribute, but is missing the `role="presentation"` attribute.
- An image has alternative text and a conflicting `role="presentation"` attribute.

If `a11ychecker_allow_decorative_images` is set to `false`, the Accessibility Checker will present an error when:

- An image does not have the alternative text attribute (`alt`).
- An image has an empty alternative text attribute.
- An image has the `role="presentation"` attribute.

> **Note**: If [`a11y_advanced_options`](#a11y_advanced_options) is set to `true`, `a11ychecker_allow_decorative_images` will default to `true`.

**Type:** `Boolean`

**Default value:** `false`

**Possible Values:** `true`, `false`

#### Example: Using `a11ychecker_allow_decorative_images`

```js
tinymce.init({
  selector: 'textarea',
  plugins: 'a11ychecker',
  toolbar: 'a11ycheck',
  a11ychecker_allow_decorative_images: true
});
```
