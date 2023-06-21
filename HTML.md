# HTML

All HTML documents must start with a document type declaration: `<!DOCTYPE html>`. The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly.
It must only appear once, at the top of the page (before any HTML tags).

## The lang Attribute
You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers.
The following example specifies English as the language:
```
<!DOCTYPE html>
<html lang="en">
<body>
...
</body>
</html>
```

Country codes can also be added to the language code in the lang attribute. So, the first two characters define the language of the HTML page, and the last two characters define the country.
The following example specifies English as the language and United States as the country:
```
<!DOCTYPE html>
<html lang="en-US">
```


**Note:** Some HTML elements have no content (like the `<br>` element). These elements are called empty elements. Empty elements do not have an end tag!

HTML elements with no content are called empty elements.
The `<br>` tag defines a line break, and is an empty element without a closing tag:

### Example:
```
<p>This is a <br> paragraph with a line break.</p>
```



The HTML document itself begins with <html> and ends with </html>.
The visible part of the HTML document is between <body> and </body>.


## Head Tag
The head tag `<head>` contains all the elements describing the document.
## Title Tag
The title tag `<title>` specifies the HTML page title, which is shown in the browser's title bar.
## Body Tag
The body tag `<body>` is where you insert your web page's content.
##Paragraph Tag
A paragraph tag `<p>` is used to define a paragraph on a web page.
## Heading Tag
The HTML heading tag is used to define the heading of the HTML document. The `<h1>` tag defines the most important tag, and `<h6>` defines the least.
## Emphasis tag
The HTML `<em>` tag is used to emphasize the particular text in a paragraph.
## Bold Tag
The `<b>` tag is used to make the text bold.
## Italic Tag
The `<i>` tag is used to make the text italic.
## Underline Tag
The `<u>` tag is used to set the text underline.

## Link Tag
The `<a>` tag links one page to another page. The href attribute is used to define

## List Tag
The `<li>` tag is used if you want to enter the contents in the listed order. There are two types of lists.
- Ordered list `<ol>`
- Unordered list `<ul>`

## Image Tag
The `<img>` tag is used to embed an image in an HTML document. You need to specify the source of the image inside the tag.



## The href Attribute
The `<a>` tag defines a hyperlink. The href attribute specifies the URL of the page the link goes to:
### Example:
```
<a href="https://www.w3schools.com">Visit W3Schools</a>
```

## The src Attribute
The `<img>` tag is used to embed an image in an HTML page. The src attribute specifies the path to the image to be displayed:
### Example:
```
<img src="img_girl.jpg">
```

There are two ways to specify the URL in the src attribute:
1. Absolute URL - Links to an external image that is hosted on another website. Example: src="https://www.w3schools.com/images/img_girl.jpg".
Notes: External images might be under copyright. If you do not get permission to use it, you may be in violation of copyright laws. In addition, you cannot control external images; it can suddenly be removed or changed.
2. Relative URL - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If the URL begins without a slash, it will be relative to the current page. Example: src="img_girl.jpg". If the URL begins with a slash, it will be relative to the domain. 

### Example: `src="/images/img_girl.jpg"`.
Tip: It is almost always best to use relative URLs. They will not break if you change domain.

## The width and height Attributes
The `<img>` tag should also contain the width and height attributes, which specify the width and height of the image (in pixels):
Example
```
<img src="img_girl.jpg" width="500" height="600">
```

## The alt Attribute
The required alt attribute for the `<img>` tag specifies an alternate text for an image, if the image for some reason cannot be displayed. This can be due to a slow connection, or an error in the src attribute, or if the user uses a screen reader.
Example
```
<img src="img_girl.jpg" alt="Girl with a jacket">
```

The title Attribute
The title attribute defines some extra information about an element.
The value of the title attribute will be displayed as a tooltip when you mouse over the element:
Example
<p title="I'm a tooltip">This is a paragraph.</p>

HTML Horizontal Rules
The <hr> tag defines a thematic break in an HTML page, and is most often displayed as a horizontal rule.
The <hr> element is used to separate content (or define a change) in an HTML page:

Tag	Description
<!--...-->	Defines a commen
<button>	Defines a clickable butto




The <meta> tag defines metadata about an HTML document. Metadata is data (information) about data.
<meta> tags always go inside the <head> element, and are typically used to specify character set, page description, keywords, author of the document, and viewport settings.
Metadata will not be displayed on the page, but is machine parsable.
Metadata is used by browsers (how to display content or reload page), search engines (keywords), and other web services.

Specifying your document's character encoding
In the example we saw above, this line was included:
<meta charset="utf-8" />
Copy to Clipboard

This element specifies the document's character encoding — the character set that the document is permitted to use. utf-8 is a universal character set that includes pretty much any character from any human language. This means that your web page will be able to handle displaying any language; it's therefore a good idea to set this on every web page you create! 


Attributes
Attribute	Value	Description
charset	character_set	Specifies the character encoding for the HTML document
content	text	Specifies the value associated with the http-equiv or name attribute
http-equiv	content-security-policy
content-type
default-style
refresh	Provides an HTTP header for the information/value of the content attribute
name	application-name
author
description
generator
keywords
viewport	


More Examples
Define keywords for search engines:
<meta name="keywords" content="HTML, CSS, JavaScript">
Define a description of your web page:
<meta name="description" content="Free Web tutorials for HTML and CSS">
Define the author of a page:
<meta name="author" content="John Doe">
Refresh document every 30 seconds:
<meta http-equiv="refresh" content="30">
Setting the viewport to make your website look good on all devices:
<meta name="viewport" content="width=device-width, initial-scale=1.0">

Setting the Viewport
The viewport is the user's visible area of a web page. It varies with the device - it will be smaller on a mobile phone than on a computer screen.
You should include the following <meta> element in all your web pages:
<meta name="viewport" content="width=device-width, initial-scale=1.0">
This gives the browser instructions on how to control the page's dimensions and scaling.
The width=device-width part sets the width of the page to follow the screen-width of the device (which will vary depending on the device).
The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.
