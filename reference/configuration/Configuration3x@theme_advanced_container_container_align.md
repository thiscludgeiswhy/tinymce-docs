---
layout: default
title: theme_advanced_container_container_align
---

This option is used to set the alignment of a specific container. The <container> part of this option should be replaced with a name within the theme_advanced_containers list. This option can only be used when theme is set to advanced and when the theme_advanced_layout_manager option is set to the value of "RowLayout".

## Example of `usage of the theme_advanced_container_<container>_align` option:

```js
tinyMCE.init({
	...
	theme_advanced_container_somecontainer1_align : "left"
	theme_advanced_container_somecontainer2_align : "right"
});
```