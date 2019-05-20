---
layout: default
title: tinymce.html.Styles
---

|  |  |
| --- | --- |
| Namespace | tinymce.html |
| Class | Styles |

This class is used to parse CSS styles it also compresses styles to reduce the output size.<span>Version:</span>3.4      

**Example**  

## Public Methods

| Method | Defined By |
| --- | --- |
| [parse](#parse)(css:String):Object : Parses the specified style value into an object collection. | Styles |
| [serialize](#serialize)(styles:Object, element_name:String):String : Serializes the specified style object into a string. | Styles |
| [toHex](#tohex)(color:String):String : Parses the specified RGB color value and returns a hex version of that color. | Styles |

## Method details

### parse 

***public function parse(css:String):Object***  
Parses the specified style value into an object collection. This parser will also merge and remove any redundant items that browsers might have added. It will also convert non hex colors to hex values. Urls inside the styles will also be converted to absolute/relative based on settings.      

**Parameters**  

| Param | Detail |
| --- | --- |
| css:String | Style value to parse for example: border:1px solid red;. |

**Returns**  
Object - Object representation of that style like {border : '1px solid red'}

### serialize 

***public function serialize(styles:Object, element_name:String):String***  
Serializes the specified style object into a string.      

**Parameters**  

| Param | Detail |
| --- | --- |
| styles:Object | Object to serialize as string for example: {border : '1px solid red'} |
| element_name:String | Optional element name, if specified only the styles that matches the schema will be serialized. |

**Returns**  
String - String representation of the style object for example: border: 1px solid red.

### toHex 

***public function toHex(color:String):String***  
Parses the specified RGB color value and returns a hex version of that color.      

**Parameters**  

| Param | Detail |
| --- | --- |
| color:String | RGB string value like rgb(1,2,3) |

**Returns**  
String - Hex version of that RGB value like #FF00FF.