# Programming Notes 
## Table of contents <a id="top"></a>

1. [Markdown](#Markdown)
2. [Terminal](#Terminal)
3. [GitHub](#GitHub)
4. [HTML basics](#HTML)
5. [CSS basics](#CSS)
6. [Flexbox](#Flexbox)
7. [Open Source Projects](#Open-Source)


## Markdown <a id="Markdown"></a>

- Text formating: `*italics*` `**bold**` `~~Scratch this~~`
- Colors: `<font color=red>Text</font>`
> Quoting: Use a greater than sign (>) and then a space, then type the text. Use the > symbol for every line you want to continue as a blockquote.
> If you want to add another quote inside a blockquote, you need to add multiple > symbols as per the level of quotes added.
- Links 
    - `[I'm an inline-style link](https://www.google.com)` 
    - `[I'm an inline-style link with title](https://www.google.com "Google's Homepage")` 
    - `[I'm a relative reference to a repository file](../blob/master/LICENSE)`
- Internal links: To link to a heading, use this code: `[heading title](#heading-title)` For the text in the parentheses, replace spaces and special characters with a hyphen. Alternatively, you can add an ID for a heading right above the title. Use this code: `<a id="heading_ID"></a>` Make sure that the heading_ID is unique within the notebook.

[Back to top](#top)

## Terminal <a id="Terminal"></a>

`/`: there are two meanings for this character. When it appears at the front of a file or directory name, it refers to the root directory. When it appears inside a path, it’s just a separator. In the ls function, any names in the output that don’t have a classification symbol are files in the current working directory.
`~`: stands for the user’s home directory 

#### Essential Commands
- `cd -`: Goes back to where I was last
- `Ctrl-L`: Clears the terminal
- `Ctrl Shift +`: Zooms in
- `Ctrl Alt T`: Opens terminal
- `ls --help` or we can read its manual with `man ls`
- `ls -Fa`: -a stands for ‘show all’ (including hidden files)
- `ls -s` displays the size of files and directories alongside the names
- `ls -S` sorts the files and directories by size.
- `pwd`: prints the user’s current working directory.
- `ls -F`: Classifies the output by adding a marker to file and directory names to indicate what they are:
        - a trailing `/` indicates that this is a directory
        - `@` indicates a link
        - `*` indicates an executable
- `cd ..`: .. is a special directory name meaning “the directory containing this one”, or more succinctly, the parent of the current directory. 
- `mkdir`: is used to create a folder or a directory, this function means ‘make directory’.
- `mkdir -p`: mkdir is not limited to creating single directories one at a time. The -p option allows mkdir to create a directory with nested subdirectories in a single operation for example `mkdir ../project/data ../project/results`
- `nano draft.txt`:  this function creates a file in a text editor, write nano followed by the file name such as: draft.txt
- `touch draft.txt`: this function creates an empty file 
- `rm my_file.txt`: remove function only removes files and not directories.
- `rmdir test/` : removes empty directories
- `mv thesis/draft.txt thesis/quotes.txt`: renaming, the first argument tells mv what we’re ‘moving’, while the second is where it’s to go. In this case, we’re moving thesis/draft.txt to thesis/quotes.txt, which has the same effect as renaming the file. One must be careful when specifying the target file name, since mv will silently overwrite any existing file with the same name, which could lead to data loss. By default, mv will not ask for confirmation before overwriting files. However, an additional option, `mv -i` (or mv --interactive), will cause mv to request such confirmation.
- `mv sucrose.dat maltose.dat ../raw`: moving the two files into the raw directory.
- `sudo apt update && sudo apt upgrade -y`
- `cat` : print the content of a file onto the standard output stream.

[Back to top](#top)

## GitHub <a id="GitHub"></a>

In order to clone your repository from GitHub onto your computer we type git clone followed by the URL with the SHH option. The full command should look similar to `git clone git@github.com:USER-NAME/REPOSITORY-NAME.git`

- `git remote -v` will display the URL of the repository you created on GitHub, which is the remote for your local copy.
- `git status`: if a file is in red it means it is not staged, if it's green it means that it is staged.
- `git add`: This command adds your file to the staging area in Git. 
- `git commit -m "Add hello_world.txt"` or `git commit`.
- `git log` allows us to look at our commit history.
- `git add .` to add all files in the current directory and all subsequent directories to the staging area.
- `git push` allows us to upload your work to the GitHub repository.
- `git pull` allows us to fetch and download content from a remote repository and update the local repository to match that content. 
- `git branch <branch_name>` creates new branches.
- `git checkout <branch_name>` changes to the specified branch.
- `git checkout -b <branch_name>` creates a new branch and change to it in a single command.
- `git branch` shows us all our current branches, the branch that you’re currently on will be indicated with an asterisk. 
- `git checkout main` to change back to main from any other branch.
- `git merge <branch_name>` which will take the changes you’ve committed in branch_name and add them to the branch that you’re currently on.
- `git branch -d <branch_name>` to delete a branch if the branch has already been merged into main.
- `git branch -D <branch_name>` if the branch hasn't already been merged into main.

[Back to top](#top)

## HTML basics <a id="HTML"></a>

1. [HTML Tag](#htmlTag)
2. [HTML head Tag](#headTag)
3. [Meta Tags](#metaTags)
4. [Other HTML Tags](#otherTags)
5. [Attributes](#attributes)

### HTML Tag <a id="htmlTag"></a>

All HTML documents must start with a document type declaration: `<!DOCTYPE html>`. The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly. It must only appear once, at the top of the page (before any HTML tags). The HTML document itself begins with `<html>` and ends with `</html>`. The visible part of the HTML document is between `<body>` and `</body>`. You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers. The following example specifies English as the language: `<html lang="en">`. Country codes can also be added to the language code in the lang attribute, for example `<html lang="en-US">`. You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers. The following example specifies English as the language: `<html lang="en">`. Country codes can also be added to the language code in the lang attribute, for example `<html lang="en-US">`.

### HTML head Tag <a id="headTag"></a>

The `<head>` tag in HTML is used to define the head portion of the document which contains information related to the document. It contains other head elements such as `<title>, <meta>, <link>, <style> <link> etc.` 

```
<head>
<title>Title of the document</title>
<link rel="stylesheet" href="resetstyle.css">
<link rel="stylesheet" href="style.css">
<script src="main.js" defer></script>
</head>
```
### Meta Tags <a id="metaTags"></a>

The `<meta>` tag defines information about an HTML document. `<meta>` tags always go inside the `<head>` element, and are typically used to specify character set, page description, keywords, author of the document, and viewport settings. Metadata will not be displayed on the page, but is machine parsable.

- `<meta charset="utf-8"/>`: This element specifies the document's character encoding — the character set that the document is permitted to use. utf-8 is a universal character set that includes pretty much any character from any human language. This means that your web page will be able to handle displaying any language; it's therefore a good idea to set this on every web page you create! 

Many `<meta>` elements include name and content attributes: `name` specifies the type of meta element it is; what type of information it contains. `content` specifies the actual meta content.

- `<meta name="description" content="Free Web tutorials for HTML and CSS">`
- `<meta name="author" content="John Doe">`
- `<meta http-equiv="refresh" content="30">`: Refresh document every 30 seconds.
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: Sets the viewport to make the website look good on all devices. The viewport is the user's visible area of a web page. It varies with the device - it will be smaller on a mobile phone than on a computer screen. This code gives the browser instructions on how to control the page's dimensions and scaling. The width=device-width part sets the width of the page to follow the screen-width of the device (which will vary depending on the device). The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.

Specifying an author is beneficial in many ways: it is useful to be able to understand who wrote the page, if you have any questions about the content and you would like to contact them. Some content management systems have facilities to automatically extract page author information and make it available for such purposes.

Specifying a description that includes keywords relating to the content of your page is useful as it has the potential to make your page appear higher in relevant searches performed in search engines (such activities are termed Search Engine Optimization, or SEO.)

#### Favicon

The humble favicon has been around for many years. It is the first icon of this type: a 16-pixel square icon used in multiple places. You may see (depending on the browser) favicons displayed in the browser tab containing each open page, and next to bookmarked pages in the bookmarks panel.

1. Saving it in the same directory as the site's index page, saved in .ico format (most also support favicons in more common formats like .gif or .png).
2. Adding the following line into your HTML's <head> block to reference it:
HTML `<link rel="icon" href="favicon.ico" type="image/x-icon" />`

### Other HTML Tags <a id="otherTags"></a>

- `<br>` defines a line break, and is an empty element without a closing tag
- `<p>` Paragraph
- `<h1>` Heading. The `<h1>` tag defines the most important tag, and `<h6>` defines the least
- `<strong>`
- `<em>` Emphasize
- `<b>` Bold
- `<i>` Italic
- `<u>` Underline
- `<abbr>` Abbreviation
- `<address>` Contact information
- `<q>` Inline Quotation
- `<code>` Display a part of programming code
- `<div>`
- `<section>` Defines a section in a document
- `<ul>` Unordered list
- `<ol>` Ordered list
- `<li>`
- `<dl>` Description list
- `<dt>` Term in description list
- `<dd>` Definition/Description of a term in description list
- `<button>`
- `<hr>` Separates content (or defines a change)
- `<a>` Hyperlink
- `<span>`
- `<kbd>`
- `<form>`
- `<input>` 

#### Hyperlink Tag

The href attribute specifies the URL of the page the link goes to: `<a href="https://www.w3schools.com">Visit W3Schools</a>`. 

`text-decoration: none` removes the line under the links.

#### input Tag

The Input tag is an empty element which only contains attributes. Syntax:
```
<input type = "value" .... />
```
How an `<input>` works varies considerably depending on the value of its type attribute. If this attribute is not specified, the default type adopted is text. For example:

- checkbox: `<input type="checkbox" name="checkbox"/>`
- date: `<input type="date" name="date"/>`

#### Image Tag

There are two ways to specify the URL in the src attribute:
1. Absolute URL - Links to an external image that is hosted on another website. Example: `src="https://www.w3schools.com/images/img_girl.jpg"`
2. Relative URL - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If the URL begins without a slash, it will be relative to the current page. Example: `src="img_girl.jpg"`. If the URL begins with a slash, it will be relative to the domain. Example: `src="/images/img_girl.jpg"`.

The required alt attribute for the `<img>` tag specifies an alternate text for an image, if the image for some reason cannot be displayed. Example:
```
<img src="img_girl.jpg" alt="Girl with a jacket">
```
The width and height Attributes
The `<img>` tag should also contain the width and height attributes, which specify the width and height of the image (in pixels), example:
```
<img src="img_girl.jpg" width="500" height="600">
```
### Attributes <a id="attributes"></a>
 
An attribute is used to define the characteristics of an HTML element and is placed inside the element's opening tag. The four core attributes that can be used on the majority of HTML elements (although not all) are: Id, title, class, and style.

The behavior of the title attribute will depend upon the element that carries it, although it is often displayed as a tooltip when cursor comes over the element or while the element is loading.

#### Data attributes

The syntax is simple. Any attribute on any element whose attribute name starts with data- is a data attribute. 
```
<article
  id="electric-cars"
  data-columns="3"
  data-index-number="12314"
  data-parent="cars">
  …
</article>
```
#### JavaScript access via dataset property

To get a data attribute through the dataset object, get the property by the part of the attribute name after data- (note that dashes are converted to camelCase).
```
const article = document.querySelector("#electric-cars");
// The following would also work:
// const article = document.getElementById("electric-cars")

article.dataset.columns; // "3"
article.dataset.indexNumber; // "12314"
article.dataset.parent; // "cars"
```
#### CSS access

We can use the attribute selectors in CSS to change styles according to the data:
```
article[data-columns="3"] {
  width: 400px;
}
article[data-columns="4"] {
  width: 600px;
}
```
Data values are strings. Number values must be quoted in the selector for the styling to take effect.

[Back to top](#top)

## CSS Basics <a id="CSS"></a>

1. [CSS stylesheet](#stylesheet)
2. [Class and ID selectors](#selectors)
3. [Cascade](#Cascade)
4. [CSS Properties](#Properties)
5. [The Box Model Tip](#Box)
6. [Pseudo-classes](#Pseudo)
7. [Custom properties and Variables](#customProperties)

### CSS stylesheet <a id="stylesheet"></a>

- External: ```<head> <link rel="stylesheet" href="styles.css" /> </head>```

- Internal: With the internal method, you place all the rules inside of a pair of opening and closing `<style>` tags, which are then placed inside of the opening and closing `<head>` tags of your HTML file.

- Inline: `<body> <div style="color: white; background-color: black;">...</div> </body>`

### Class and ID selectors <a id="selectors"></a>

- `* { }` The universal selector will select elements of any type, hence the name “universal”, and the syntax for it is a simple asterisk.
- `.alert-text { color: red;}` One class selector
- `.read,.unread { color: white; background-color: black;}` Two class selectors
- `class="alert-text severe-alert"` A single element with 2 classes
- `.subsection#preview { color: blue;}` chaining a class and an ID
- `.ancestor .child` descendant combinator
- `.container > div` all the direct kids 

### Cascade <a id="Cascade"></a>

Specificity: A CSS declaration that is more specific will take precedence over less specific ones.
1. ID selectors (most specific selector)
2. Class selectors
3. Type selectors

### CSS Properties <a id="Properties"></a>

- Font-size
- Text-align
- Font-weight
- Line-height
- Cursor
- Border
- Opacity
- Box shadow
- Border Radius
- [Background-image](#background-image)
- [Font-family](#font-family)
- [Display](#display)
- [Transition](#Transition)
- [Transform](#Transform)
- [Filters](#Filters)
- [Spacing](#Spacing)

#### Background Image <a id="background-image"></a>

To add a background image, you must add it in css as `background-image: url()`, always add a background color as well in case the picture doesn't load.

Some of the properties to add to a background image are:
- background-repeat
- background-size
- background-position

#### Font Family <a id="font-family"></a>

- Serif: While initially used for ink printing purposes, the style is now associated with a sense of formality and elegance. Websites mainly use Serif for body text, as it is highly legible and helps readers quickly skim written content. Popular Serif fonts include Times New Roman, Cambria, and Garamond. 
- Sans serif: These fonts are simple and straightforward, they do not display additional strokes attached to their letters.
- Cursive: Cursive fonts imitate handwriting, usually having the letters joined together in a looped, flowing manner.
- Fantasy: The Fantasy font family generally features decorative attributes present on each letter.
- Monospace: Each letter and symbol found in Monospace fonts are of the same width. Since the fonts are consistent and easy to distinguish, they are often the default font for typewriters and computer terminals.

If the user has the first font in the list installed on their computer, their browser will display that font. If they don't, the browser will try to display the next font in the list. The last font in the list should always be one of the five generic font families.

"Times New Roman" appears in quotation marks, whereas the other fonts don't. Anytime a font's name is more than one word, it must be in quotation marks

**Best Web-Safe HTML Fonts**

Web-safe fonts are fonts that come pre-installed across most operating systems. This ensures that the fonts render as intended when accessed from various devices and browsers. Most popular examples of web-safe fonts include Arial, Times New Roman, and Helvetica.
1. <p style="font-family: Arial">Arial</p>
2. <p style="font-family: Arial Narrow">Arial Narrow</p>
3. <p style="font-family: 'Times New Roman'">Times New Roman</p>
4. <p style="font-family: Helvetica">Helvetica</p>
5. <p style="font-family: Courier">Courier</p>
6. <p style="font-family: Verdana">Verdana</p>
7. <p style="font-family: Candara">Candara</p>
8. <p style="font-family: Geneva">Geneva</p>
9.  <p style="font-family: Calibri">Calibri</p>
10. <p style="font-family: Optima">Optima</p>
11. <p style="font-family: Cambria">Cambria</p>
12. <p style="font-family: Garamond">Garamond</p>
13. <p style="font-family: Perpetua">Perpetua</p>
14. <p style="font-family: 'Brush Script'">Brush Script</p>
15. <p style="font-family: 'Lucida Bright'">Lucida Bright</p>

#### Display <a id="display"></a>

The display property specifies the display behavior (the type of rendering box) of an element.

- inline: displays an element as an inline element `(like <span>)`. Any height and width properties will have no effect
- block: displays an element as a block element `(like <p>)`. It starts on a new line and takes up the full width available.
- inline-block: The element itself is formatted as an inline element, but you can apply height and width values. inline-block brought a new way to create side by side boxes that collapse and wrap properly depending on the available space in the containing element. The major difference between inline-block and inline is that it allows us to set a width and height on the element, as for inline top and bottom margins and paddings are not respected. Now, the difference between inline-block and block is that, block, a line break happens after the element, so a block element doesn’t sit next to other elements.

#### Transition <a id="Transition"></a>

To use transitions in CSS, you can use the various transition properties or the transition shorthand property.

```
transition: [transition-property] [transition-duration] [transition-timing-function] [transition-delay];
```
1. <u>Transition-property</u>

The transition-property property specifies which style(s) to transition. The transition-property accepts one or more CSS property names in a comma-separated list. `transition-property: background-color, transform;`

Optionally, you may use `transition-property: all` to indicate that every property should transition.

2. <u>Transition-duration</u>

The transition-duration property is used to define the length of time that a transition will take to complete. transition-duration accepts time units, either in seconds (s) or milliseconds (ms) and defaults to 0s.

3. <u>Transition-timing-function</u>

By default, CSS will transition your elements at a constant speed (transition-timing-function: linear). Linear transitions can end up looking somewhat artificial, though: in real life, objects have weight and can't stop and start instantly. Easing into or out of a transition can make your transitions more lively and natural. Other timing functions are: ease, ease-in, ease-out, ease-in-out, steps, and cubic.

4. <u>Transition-delay</u>

Use the transition-delay property to specify the time at which a transition will start. If transition-duration is not specified, transitions will start instantly because the default value is 0s. This property accepts a time unit, for example seconds (s) or milliseconds (ms). This property is useful for staggering transitions, achieved by setting a longer transition-delay for each subsequent element in a group.

Different transitions for enter or exit
```
.my-element {
  background: red;

  /* This transition is applied on the "exit" transition */
  transition: background 2000ms ease-in;
}

.my-element:hover {
  background: blue;

  /* This transition is applied on the "enter" transition */
  transition: background 150ms ease;
}
```
#### Transform <a id="Transform"></a> 

All of the following functions are used with the transform property.
- Rotation
- Scale
- Translate
- Skewing
- Perspective
  
**Rotation**

You can rotate an element using the rotate() function, which will rotate an element on its center axis. You can also use the rotateX(), rotateY() and rotateZ() functions to rotate an element on a specific axis instead. You can pass degree, turn and radian units to determine the level of rotation.
```
.my-element {
  transform: rotateX(10deg) rotateY(10deg) rotateZ(10deg);
}
```
The rotate3d() function takes four arguments. The first 3 arguments are numbers, which define the X, Y and Z coordinates. The fourth argument is the rotation which, like the other rotation functions, accepts degrees, angle and turns.

**Scale**

You can change the scaling of an element with transform and the scale() function. The function accepts one or two numbers as a value which determine a positive or negative scaling. If you only define one number argument, both the X and Y axis will be scaled the same and defining both is a shorthand for X and Y. Just like rotate(), there are scaleX(), scaleY() and scaleZ() functions to scale an element on a specific axis instead. Also like the rotate function, there is a scale3d() function. This is similar to scale(), but it takes three arguments: the X, Y and Z scale factor.
```
.my-element {
  transform: scaleX(1.2) scaleY(1.2);
}
```
**Translate**

The translate() functions move an element while it maintains its position in the document flow. They accept length and percentage values as arguments. The translate() function translates an element along the X axis if one argument is defined, and translates an element along the X and Y axis if both arguments are defined. You can—just like with other transform functions—use specific functions for a specific axis, using translateX, translateY and translateZ. You can also use translate3d which allows you to define the X, Y and Z translation in one function.
```
.my-element {
  transform: translateX(-100px) translatey(25px);
}
```
**Skewing**

If you only define one argument, it will only affect the X axis and if you define both, it will affect the X and Y axis. You can also use skewX and skewY to affect each axis independently.
```
.my-element {
  transform: skew(10deg);
}
```
**Perspective**

Prespective gives the feeling of distance and can be used to create a depth of field in your designs.

#### Filters <a id="Filters"></a> 

`filter: blur(0.2em);` This applies a gaussian blur and the only argument you can pass is a radius, which is how much blur is applied. This needs to be a length unit, like 10px. Percentages are not accepted. 

`filter: brightness(80%);` The brightness value is expressed as a percentage with the unchanged image being expressed as a value of 100%. A value of 0% turns the image completely black, therefore values between 0% and 100% make the image less bright. Use values over 100% to increase the brightness.

`filter: drop-shadow(5px 5px 10px orange);` The drop-shadow filter takes a shadow parameter which contains space separated offset-x, offset-y, blur and color values. 

Other properties include: contrast, grayscale, and opacity.

#### Spacing <a id="Spacing"></a> 

If you want to add space to the outside of an element, you use the margin property. The margin property is shorthand for `margin-top, margin-right, margin-bottom and margin-left`. You can also use a value of auto for margin. For block level elements with a restricted size, an auto margin will take up available space in the direction that it is applied to. A good example is this one, from the flexbox module, where the items push away from each other. Negative values can also be used for margin. Instead of adding space between adjacent sibling elements, it will reduce space between them. This can result in overlapping elements, if you declare a negative value that's more than the available space.

 Just like margin, padding has logical properties, too: padding-block-start, padding-inline-end, padding-block-end and padding-inline-start.

 **Positioning**

if you set a value for position that is anything other than static, you can space elements with the top, right, bottom and left properties. There are some differences with how these directional values behave:

- `position: relative` will maintain its place in the document flow, even when you set these values. They will be relative to your element's position too.
- `position: absolute` will base the directional values from the relative parent's position.
- `position: fixed` will base the directional values on the viewport.
- `position: sticky` will only apply the directional values when it is in its docked/stuck state.

**Z-index**

The z-index property explicitly sets a layer order for HTML based on the 3D space of the browser—the Z axis. This is the axis which shows which layers are closer to and further from you.

In normal flow, if you set a specific value for z-index and it isn't working, you need to set the element's position value to anything other than static. This is a common place where people struggle with z-index.

To set an element behind another element, add a negative value for z-index.

#### Other Information 

`list-style-type: none` removes the dots on the list items

### The Box Model Tip <a id="Box"></a>

Always start by setting margin and padding to 0 for all elements to clear out all margins and paddings in the document. `box-sizing: border-box` tells the browser to account for any border and padding in the values you specify for an element's width and height. If you set an element's width to 100 pixels, that 100 pixels will include any border or padding you added, and the content box will shrink to absorb that extra width. This typically makes it much easier to size elements.
```
* {margin: 0;
  padding: 0;
  box-sizing: border-box;}
```

### Pseudo-classes <a id="Pseudo"></a> 

Below is a list of some pseudo-classes and events that can trigger state changes in elements.

- `:hover`: matches if the cursor is over the element.
- `:focus`: matches if the element is focused.
- `:focus-within`: matches if the element or any of its descendants are focused.
- `:target:` matches when the current URL's fragment matches the element's id.
:active: matches when the element is being activated (typically when the mouse is pressed over it).
- class change from JavaScript: when an element's CSS class changes via JavaScript, CSS will transition eligible properties that have changed.

Links can be styled differently depending on their state. If you define a :visited style, it can be overridden by a link pseudo-class with at least equal specificity. Because of this, it's recommended that you use the LVHA rule for styling links with pseudo-classes in a particular order: :link, :visited, :hover, :active.

- a:link - Represents a normal, unvisited link.
- a:visited - Represents a link that the user has visited.
- a:hover - Represents a link when the user hovers over it.
- a:active - Represents a link at the moment it is clicked.

`Text Decoration`: The text-decoration property controls the appearance of the link's text decoration, such as underlining. When set to none it removes the line under the links.

#### Form states `:disabled and :enabled`

If a form element, such as a button is disabled by the browser, you can hook on to that state with the :disabled pseudo-class. The :enabled pseudo-class is available for the opposite state, though form elements are also :enabled by default, therefore you might not find yourself reaching for this pseudo-class.

#### `:checked and :indeterminate`

The :checked state is a binary(true or false) state, but checkboxes do have an in-between state when they are neither checked or unchecked. This is known as the :indeterminate state.

#### Validation states

The :valid and :invalid pseudo-classes are useful for contexts such as an email field that has a pattern that needs to be matched, for it to be a valid field. 

The :in-range pseudo-class is available if an input has a min and max, such as a numeric input and the value is within those bounds.

With HTML forms, you can determine that a field is required with the required attribute. The :required pseudo-class will be available for required fields. Fields that are not required can be selected with the :optional pseudo-class.

### Custom properties and Variables <a id="customProperties"></a> 
A custom property is a variable which allows you to tokenize values in your CSS code. Custom properties are also affected by the cascade which means they can be contextually manipulated or redefined. A custom property must be prefixed with two dashes (--) and are case sensitive.

```
:root {
	--base-color: #ff00ff;
}

.my-element {
	background: var(--base-color);
}
```
The var() function takes one required argument: the custom property that you are trying to return as a value. In the above snippet, the var() function has --base-color passed as an argument. If --base-color is defined, then var() will return the value.
```
.my-element {
	background: var(--base-color, hotpink);
}
```
You can also pass a fallback declaration value into the var() function. This means that if --base-color can't be found, the passed declaration will be used instead, which in this sample's case is the hotpink color.


[Back to top](#top)


## Flexbox <a id="Flexbox"></a>

In Flexbox, you work with two main concepts: flex containers and flex items. A flex container is an element that has the `display: flex;`. This property defines the element as a flex container and enables the use of Flexbox properties. Flex items are the direct children of a flex container. Any element can be a flex item, and elements can be both flex containers and flex items simultaneously. 

#### Flex Container Direction and Alignment

The `flex-direction` property determines the direction in which flex items are laid out within the flex container. The available values are:

- row: The default value. Flex items are arranged in a horizontal row.
- column: Flex items are stacked vertically from top to bottom.
- row-reverse: Flex items are arranged in a horizontal row, but in reverse order.
- column-reverse: Flex items are stacked vertically from bottom to top.

The `justify-content` property controls the alignment of flex items along the main axis (horizontal axis for row and row-reverse, vertical axis for column and column-reverse). Available values include:

- flex-start: Items are aligned to the start of the container.
- flex-end: Items are aligned to the end of the container.
- center: Items are centered within the container.
- space-between: Items are evenly distributed with equal space between them.
- space-around: Items are evenly distributed with equal space around them.
- space-evenly: Items are evenly distributed with equal space around and between them.

The `align-items` property controls the alignment of flex items along the cross axis. The cross axis is the perpendicular axis to the main axis. The possible values are:

- stretch: Items are stretched to fill the container vertically (default).
- flex-start: Items are aligned to the start of the container on the cross axis.
- flex-end: Items are aligned to the end of the container on the cross axis.
- center: Items are centered vertically within the container.
- baseline: Items are aligned based on their baseline.

The `align-content` property is used to control the spacing between flex lines (rows or columns) when there is extra space on the cross axis. It only applies when flex items wrap into multiple lines. Available values are similar to justify-content.

#### Flex Item Order and Alignment

The order in which flex items appear within the flex container can be controlled using the order property. By default, all items have an order value of 0, but you can assign positive or negative values to change their order. Items with lower order values appear first, while items with higher order values appear later. This allows you to rearrange the visual order of items without modifying their HTML structure.

#### Flex

The flex property is a shorthand for three individual properties: flex-grow, flex-shrink, and flex-basis. It allows you to control the behavior of flex items regarding their growth, shrinking, and initial size.

- `flex-grow` determines the ability of an item to grow and how much it should grow relative to other items. By default, it is set to 0, meaning items won't grow.
- `flex-shrink` defines the ability of an item to shrink and how much it should shrink relative to other items when there is insufficient space. By default, it is set to 1, allowing items to shrink equally.
- `flex-basis` specifies the initial size of an item before any available space is distributed. It can be set as a fixed length, percentage, or auto.

To align flex items to the left or right of a container, you can also use auto-margins (`margin-left: auto`; or `margin-right: auto`;) on flex items. This automatically consumes any available space on the main axis, pushing the item to the desired side.

- `flex: initial`: Equivalent to flex: 0 1 auto. (This is the initial value.) Makes the flex item inflexible when there is positive free space, but allows it to shrink to its minimum size when there is insufficient space.
- `flex: auto`: Equivalent to flex: 1 1 auto. Sizes the item based on the width/height properties, but makes them fully flexible, so that they absorb any free space along the main axis. If all items are either flex: auto, flex: initial, or flex: none, any positive free space after the items have been sized will be distributed evenly to the items with flex: auto.
- `flex: none`: Equivalent to flex: 0 0 auto. This value sizes the item according to the width/height properties, but makes the flex item fully inflexible. This is similar to initial, except that flex items are not allowed to shrink, even in overflow situations.
- `flex: <positive-number>`: Equivalent to flex: <positive-number> 1 0. Makes the flex item flexible and sets the flex basis to zero, resulting in an item that receives the specified proportion of the free space in the flex container. If all items in the flex container use this pattern, their sizes will be proportional to the specified flex factor. By default, flex items won’t shrink below their minimum content size (the length of the longest word or fixed-size element). To change this, set the min-width or min-height property.

#### Other Properties for Alignment

In addition to the properties mentioned earlier (justify-content, align-items, align-self, and align-content), there are a few more properties that can help with alignment in Flexbox:

- `justify-self`: This property is similar to justify-content, but it applies to individual flex items within the container. It allows you to align items along the main axis independently.
- `place-content`: This shorthand property combines justify-content and align-content properties to control both main axis and cross axis alignment simultaneously.
- `place-items`: This shorthand property combines align-items and justify-items properties to control both cross axis and main axis alignment simultaneously.
- `place-self`: This property combines align-self and justify-self properties to control both cross axis and main axis alignment for individual flex items.
- `gap`: This property allows you to add space between flex items, similar to applying margins to the items themselves. It is a shorthand for both row-gap (vertical gap) and column-gap (horizontal gap) properties.
- `align-self`: This property can be used on individual flex items to override the alignment set by the flex container. It accepts the same values as align-items and allows you to align a specific item differently from the others.
- `flex-wrap`: This property forces items that don’t fit to get bumped down to the next row.

## Notes for Later

- We've added `height: 100vh` to the `body`... this makes the body exactly the same height as the viewport.

this is some magical font-importing.  
you'll learn about it later.
@import url('https://fonts.googleapis.com/css2?family=Besley:ital,wght@0,400;1,900&display=swap');

rem
text-transform
letter-spacing
vh

## FreeCodeCamp Notes to Sort Later

min-height

## HTML 

HTML5 has some elements that identify different content areas. These elements make your HTML easier to read and help with Search Engine Optimization (SEO) and accessibility.

Identify the **main section** of this page by adding a `<main>` opening tag before the h1 element, and a </main> closing tag after the p element.

The **figure element** represents self-contained content and will allow you to associate an image with a caption.
A **figure caption** (figcaption) element is used to add a caption to describe the image contained within the figure element.

```
<figure>
  <img>
  <figcaption></figcaption>
</figure>
```

Form Element: Now you will add a web form to collect information from users.
The action attribute indicates where form data should be sent. For example, <form action="/submit-url"></form> tells the browser that the form data should be sent to the path /submit-url.

In order for a form's data to be accessed by the location specified in the action attribute, you must give the text field a name attribute and assign it a value to represent the data being submitted. For example, you could use the following syntax for an email address text field: <input type="text" name="email">.

Placeholder text is used to give people a hint about what kind of information to enter into an input. For example, <input type="text" placeholder="Email address">.

To prevent a user from submitting your form when required information is missing, you need to add the required attribute to an input element. There's no need to set a value to the required attribute. Instead, just add the word required to the input element, making sure there is space between it and other attributes.

You can use radio buttons for questions where you want only one answer out of multiple options.

label elements are used to help associate the text for an input element with the input element itself (especially for assistive technologies like screen readers). For example, <label><input type="radio"> cat</label> makes it so clicking the word cat also selects the corresponding radio button.

Notice that both radio buttons can be selected at the same time. To make it so selecting one radio button automatically deselects the other, both buttons must have a name attribute with the same value

If you select the Indoor radio button and submit the form, the form data for the button is based on its name and value attributes. Since your radio buttons do not have a value attribute, the form data will include indoor-outdoor=on, which is not useful when you have multiple buttons.

The fieldset element is used to group related inputs and labels together in a web form. fieldset elements are block-level elements, meaning that they appear on a new line.

The legend element acts as a caption for the content in the fieldset element. It gives usersThere's another way to associate an input element's text with the element itself. You can nest the text within a label element and add a for attribute with the same value as the input element's id attribute.

Like radio buttons, form data for selected checkboxes are name / value attribute pairs. While the value attribute is optional, it's best practice to include it with any checkboxes or radio buttons on the page.
`<label for="email" >Enter Your Email: <input id="email" /></label>`
Now you will add a footer section to the page.

After the main element, add a footer element.


Another project - Registration Form

The vh unit stands for viewport height, and is relative to 1% of the height of the viewport.

It is time to spruce the project up with some CSS. Begin by giving the body a width of 100%, and a height of 100vh.

The HTML | action Attribute is used to specify where the form data is to be sent to the server after the submission of the form. It can be used in the <form> element. Attribute Values: URL: It is used to specify the URL of the document where the data is to be sent after the submission of the form.

The method attribute specifies how to send form-data to the URL specified in the action attribute. The form-data can be sent via a GET request as URL parameters (with method="get") or via a POST request as data in the request body (with method="post").

Specifying the type attribute of a form element is important for the browser to know what kind of data it should expect. If the type is not specified, the browser will default to text.

Give the first two input elements a type attribute of text, the third a type attribute of email, and the fourth a type attribute of password.

The email type only allows emails with a @ and a . in the domain. The password type obscures the input, and warns if the site does not use HTTPS.
```
 <fieldset>
        <label for="profile-picture">Upload a profile picture: <input id="profile-picture" type="file" /></label>
        <label for="age">Input your age (years): <input id="age" type="number" min="13" max="120" /></label>
        <label for="referrer">How did you hear about us?
          <select id="referrer">
            <option value="">(select one)</option>
            <option value="1">freeCodeCamp News</option>
            <option value="2">freeCodeCamp YouTube Channel</option>
            <option value="3">freeCodeCamp Forum</option>
            <option value="4">Other</option>
          </select>
        </label>
        <label for="bio">Provide a bio:
          <textarea id="bio"></textarea>
        </label>
      </fieldset>
```
Certain type attribute values come with built-in form validation. For example, type="email" requires that the value be a valid email address.

Add custom validation to the password input element, by adding a minlength attribute with a value of 8. Doing so prevents inputs of less than 8 characters being submitted.

With type="password" you can use the pattern attribute to define a regular expression that the password must match to be considered valid.

Add a pattern attribute to the password input element to require the input match: [a-z0-5]{8,}

The above is a regular expression which matches eight or more lowercase letters or the digits 0 to 5. Then, remove the minlength attribute, and try it out.

You only want one radio input to be selectable at a time. However, the form does not know the radio inputs are related.

To relate the radio inputs, give them the same name attribute with a value of account-type. Now, it is not possible to select both radio inputs at the same time.

Nest the select element (with its option elements) within a label element with the text How did you hear about us?. The text should come before the select element.
```
 <fieldset>
        <label>Upload a profile picture: <input type="file" /></label>
        <label>Input your age (years): <input type="number" min="13" max="120" /></label>
        <label>How did you hear about us?
          <select>
            <option value="">(select one)</option>
            <option value="1">freeCodeCamp News</option>
            <option value="2">freeCodeCamp YouTube Channel</option>
            <option value="3">freeCodeCamp Forum</option>
            <option value="4">Other</option>
          </select>
        </label>
      </fieldset>
```

The textarea element acts like an input element of type text, but comes with the added benefit of being able to receive multi-line text, and an initial number of text rows and columns.

With form submissions, it is useful, and good practice, to provide each submittable element with a name attribute. This attribute is used to identify the element in the form submission.

The border of the last fieldset element looks a little out of place. You can select the last element of a specific type using the last-of-type CSS pseudo-class, like this:

`p:last-of-type { }` That will select the last p element. 

Select all input, textarea, and select elements, and make them take up the full width of their parent elements. `width:100%;`

width of unset. This will remove the earlier rule which set all the input elements to width: 100%.

If you look close enough, you will notice the .inline elements are too high on the line.

To combat this, set the vertical-align property to middle.

To style the submit button, you can use an attribute selector, which selects an element based on the given attribute value. Here is an example:

input[name="password"]
The above selects input elements with a name attribute value of password.

When you have specified a width on the object that you have applied margin: 0 auto to, the object will sit centrally within it's parent container.

Specifying auto as the second parameter basically tells the browser to automatically determine the left and right margins itself, which it does by setting them equally. It guarantees that the left and right margins will be set to the same size. The first parameter 0 indicates that the top and bottom margins will both be set to 0.

margin-top: 0;
margin-bottom: 0;
margin-left: auto;
margin-right: auto;

## Open Source Projects <a id="Open-Source"></a>

Select an issue to start contributing. You can find such issues under the tag good first issue for beginners.