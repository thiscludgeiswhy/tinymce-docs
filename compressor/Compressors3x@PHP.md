---
layout: default
title: PHP
---

TinyMCE Compressor gzips all javascript files in TinyMCE to a single streamable file. This makes the overall download size 75% smaller and the number of requests will also be reduced. The overall initialization time for TinyMCE will be reduced dramaticly if you use this script.

## Requirements

1.  The PHP version must be version 4 or above
2.  The PHP gzip compressor cannot and will not work if zlib compression is already enabled on the server.

## Installation

Here are step-by-step instructions for installing the GZip compressor.

1.  Ensure that your server does not have zlib compression enabled in the file php.ini
2.  Copy the tiny_mce_gzip.js and tiny_mce_gzip.php to the tiny_mce directory. The same directory that contains the tiny_mce.js file. (You can download the necessary files from our [download page](http://archive.tinymce.com/download/download.php).)
3.  Remove the current script tag.
    <script type="text/javascript" src="tinymce/jscripts/tiny_mce/tiny_mce.js"></script>
4.  Add the new new GZip script
    <script type="text/javascript" src="tinymce/jscripts/tiny_mce/tiny_mce_gzip.js"></script>
5.  Add the new GZip initialization call that will tell the compressor what to include in the output. This should be all of the plugins, themes, and languages required by your TinyMCE implementation.

## Example of Initialization

The example below packs all of the plugins, themes, and languages into one file/stream. Remove the things you don't need or add your custom plugins to the settings below. Remember that the tinyMCE_GZ.init call must be placed in its own script tag. User defined plugins and themes should be identical in both "inits".

```html
<script type="text/javascript" src="tinymce/jscripts/tiny_mce/tiny_mce_gzip.js"></script>
<script type="text/javascript">
tinyMCE_GZ.init({
<!-- user-defined plugins and themes should be identical to those in "tinyMCE.init" below.-->
	plugins : 'style,layer,table,save,advhr,advimage,advlink,emotions,iespell,insertdatetime,preview,media,'+
        'searchreplace,print,contextmenu,paste,directionality,fullscreen,noneditable,visualchars,nonbreaking,xhtmlxtras',
	themes : 'simple,advanced',
	languages : 'en',
	disk_cache : true,
	debug : false
});
</script>
<!-- Needs to be seperate script tags! -->
<script type="text/javascript">
tinyMCE.init({
<!-- user-defined plugins and themes should be identical to those in "tinyMCE_GZ.init" above i.e.-->
        plugins : 'style,layer,table,save,advhr,advimage,advlink,emotions,iespell,insertdatetime,preview,media,'+
        'searchreplace,print,contextmenu,paste,directionality,fullscreen,noneditable,visualchars,nonbreaking,xhtmlxtras',
	themes : 'simple,advanced',

	.. now add your normal init, which will not be added to the tinyMCE_GZ.init above ..
});
</script>
```

## Direct method

As of 2.0.3 there is also a direct method for loading TinyMCE without the need of first loading the tiny_mce_gzip.js file.

```js
// Load the TinyMCE compressor class
require_once("../tiny_mce/tiny_mce_gzip.php");

// Renders script tag with compressed scripts
TinyMCE_Compressor::renderTag(array(
    "url" => "../tiny_mce/tiny_mce_gzip.php",
    "plugins" => "pagebreak,style",
    "themes" => "advanced",
    "languages" => "en"
));
```

### Direct method options:

| Option | Description |
| --- | --- |
| plugins | Comma separated list of plugins to include in the compressed script. For example: paste,table |
| themes | Comma separated list of themes to include in the compressed script. For example: advanced,simple |
| languages | Comma separated list of languages to include in the compressed script. For example: en,sv |
| disk_cache | True/false state if the gzip compressed data should be cached as a file on the server for extra performance. |
| expires | Relative expiration date for the clients cache. It should be a number with a suffix like "d" for days and "m" for months. |
| cache_dir | Location to where the cached files should be stored defaults to the same directory as the php file. |
| compress | True/false state if the contents should be gzipped or not. Defaults to true. |
| files | Comma separated list of custom files to include with the compression. |
| source | True/false if the minified scripts should be used or not defaults to false. |

## Troubleshooting

*   The GZip compressor can fail to load if the server has odd settings or is missing the required support for it to function. To see compilation errors or other problems we suggest that you use HTTP debugging tools like [Fiddler](http://www.fiddlertool.com/fiddler/) or [Firebug](http://www.getfirebug.com/) you can also point you browser directly to the GZip file.
*   Consult the changelog of this script and make sure that you use the latest version of TinyMCE. These two parts are pretty much tied together so there is no guarantee that it will work with older versions of TinyMCE.
*   Visit the [TinyMCE Community forum](https://community.tiny.cloud) for help with the TinyMCE Gzip Compressor.
*   To remove a plugin, remember to remove it both from tinyMCE_GZ.init and TinyMCE.init.
*   To add a plugin, remember to add it both to the tinyMCE_GZ.init and the tinyMCE.init calls.
*   If you are using prototype.js and scriptaculous.js framework include them below/after this two tags:

```html
<script type="text/javascript">tinyMCE_GZ.init({.....});</script>
<script type="text/javascript">tinyMCE.init({.....});</script>
```