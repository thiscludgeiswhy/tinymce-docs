### `imagetools_credentials_hosts`

This option can be used together with the `imagetools_cors_hosts` option to allow credentials to be sent to the CORS host. This is not enabled by default since the server needs to have proper CORS headers to support this.

**Type:** `String[]`

#### Example: Using `imagetools_credentials_hosts`

```js
tinymce.init({
  selector: 'textarea',  // change this value according to your HTML
  toolbar: 'image',
  plugins: 'image imagetools',
  imagetools_cors_hosts: ['mydomain.com', 'otherdomain.com'],
  imagetools_credentials_hosts: ['mydomain.com', 'otherdomain.com']
});
```
