# Programming Notes 
## Table of contents

1. [Markdown](#Markdown)
2. [Terminal](#Terminal)
3. [GitHub](#GitHub)
4. [HTML basics](#HTML)
5. [CSS basics](#CSS)
6. [Flexbox](#Flexbox)


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

## GitHub <a id="GitHub"></a>

In order to clone your repository from GitHub onto your computer we type git clone followed by the URL with the SHH option. The full command should look similar to `git clone git@github.com:USER-NAME/REPOSITORY-NAME.git`

`git remote -v` will display the URL of the repository you created on GitHub, which is the remote for your local copy
`git status`: if a file is in red it means it is not staged, if it's green it means that it is staged.
`git add`: This command adds your file to the staging area in Git. 
`git commit -m "Add hello_world.txt"` or `git commit`
`git log` allows us to look at our commit history
`git add .` to add all files in the current directory and all subsequent directories to the staging area.
`git push` allows us to upload your work to the GitHub repository
`git pull`allows us to fetch and download content from a remote repository and update the local repository to match that content. 

## HTML basics <a id="HTML"></a>

All HTML documents must start with a document type declaration: `<!DOCTYPE html>`. The `<!DOCTYPE>` declaration represents the document type, and helps browsers to display web pages correctly. It must only appear once, at the top of the page (before any HTML tags). The HTML document itself begins with `<html>` and ends with `</html>`. The visible part of the HTML document is between `<body>` and `</body>`. You should always include the lang attribute inside the `<html>` tag, to declare the language of the Web page. This is meant to assist search engines and browsers. The following example specifies English as the language: `<html lang="en">`. Country codes can also be added to the language code in the lang attribute. So, the first two characters define the language of the HTML page, and the last two characters define the country, for example `<html lang="en-US">`

#### Meta Tag

The `<meta>` tag defines metadata about an HTML document. Metadata is data (information) about data. `<meta>` tags always go inside the `<head>` element, and are typically used to specify character set, page description, keywords, author of the document, and viewport settings.
Metadata will not be displayed on the page, but is machine parsable.

- `<meta charset="utf-8"/>` This element specifies the document's character encoding — the character set that the document is permitted to use. utf-8 is a universal character set that includes pretty much any character from any human language. This means that your web page will be able to handle displaying any language; it's therefore a good idea to set this on every web page you create! 
- `<meta name="keywords" content="HTML, CSS, JavaScript">` Keywords for search engines
- `<meta name="description" content="Free Web tutorials for HTML and CSS">` Description of the web page
- `<meta name="author" content="John Doe">` Defines the author of a page
- `<meta http-equiv="refresh" content="30">` Refresh document every 30 seconds
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">` Sets the viewport to make the website look good on all devices. The viewport is the user's visible area of a web page. It varies with the device - it will be smaller on a mobile phone than on a computer screen. This code gives the browser instructions on how to control the page's dimensions and scaling. The width=device-width part sets the width of the page to follow the screen-width of the device (which will vary depending on the device). The initial-scale=1.0 part sets the initial zoom level when the page is first loaded by the browser.

#### Other HTML Tags

- `<head>` The head tag contains all the elements describing the document
- `<title>` The title tag specifies the HTML page title, which is shown in the browser's title bar
- `<body>` The body tag is where you insert your web page's content
- `<br>`: defines a line break, and is an empty element without a closing tag
- `<p>` Paragraph
- `<h1>` Heading. The `<h1>` tag defines the most important tag, and `<h6>` defines the least.
- `<strong>`
- `<em>` Emphasize
- `<b>` Bold
- `<i>` Italic
- `<u>` Underline
- `<abbr>` Abbreviation
- `<address>` Contact Information
- `<q>` Inline Quotation
- `<code>` Display A Part Of Programming Code
- `<div>` Division
- `<section>` Defines a section in a document
- `<ul>` Unordered List
- `<ol>` Ordered List
- `<li>` List: `list-style-type: none` this removes the dots on the list items
- `<dl>` Description List
- `<dt>` Term In Description List
- `<dd>` Definition/Description Of A Term In Description List
- `<!--...-->` Defines a comment
- `<button>` Defines a clickable button
- `<hr>` Separates content (or defines a change)
- `<a>` Hyperlink. The href attribute specifies the URL of the page the link goes to: `<a href="https://www.w3schools.com">Visit W3Schools</a>`. `text-decoration: none` removes the line under the links.
  

#### Image Tag

There are two ways to specify the URL in the **src attribute**:
1. Absolute URL - Links to an external image that is hosted on another website. Example: `src="https://www.w3schools.com/images/img_girl.jpg"`
2. Relative URL - Links to an image that is hosted within the website. Here, the URL does not include the domain name. If the URL begins without a slash, it will be relative to the current page. Example: `src="img_girl.jpg"`. If the URL begins with a slash, it will be relative to the domain. Example: `src="/images/img_girl.jpg"`.

The required **alt attribute** for the `<img>` tag specifies an alternate text for an image, if the image for some reason cannot be displayed. This can be due to a slow connection, or an error in the src attribute, or if the user uses a screen reader. Example:
```
<img src="img_girl.jpg" alt="Girl with a jacket">
```
The **width and height Attributes**
The `<img>` tag should also contain the width and height attributes, which specify the width and height of the image (in pixels), example:
```
<img src="img_girl.jpg" width="500" height="600">
```

## CSS Basics <a id="CSS"></a>

#### CSS stylesheet

- External: involves creating a separate file for the CSS and linking it inside of an HTML’s opening and closing `<head>` tags with a self-closing `<link>` element: ```<head> <link rel="stylesheet" href="styles.css" /> </head>``` The href attribute is the location of the CSS file.

- Internal: With the internal method, you place all the rules inside of a pair of opening and closing `<style>` tags, which are then placed inside of the opening and closing `<head>` tags of your HTML file.

- Inline: `<body> <div style="color: white; background-color: black;">...</div> </body>`

#### Class and ID selectors

- `* { }` The universal selector will select elements of any type, hence the name “universal”, and the syntax for it is a simple asterisk.
- `.alert-text { color: red;}` One class selector
- `.read,.unread { color: white; background-color: black;}` Two class selectors
- `class="alert-text severe-alert"` A single element with 2 classes
- `.subsection.header { color: red;}` An element that has both subsection as a first class and header as a second class
- `.subsection#preview { color: blue;}` chainning a class and an ID
- `.ancestor .child` **descendant combinator**
- `.container > div` all the direct kids 

#### CSS Properties

- Color
- Font-size
- Text-align
- Font-weight
- Background Color
- Height/Width
- Line-height
- Cursor
- `list-style-type: none`: removes the dots on the list items
- [Background-image](#background-image)
- [Button](#button)
- [Font-family](#font-family)
- [Display](#display)
- **padding** increases the space between the border of a box and the content of the box.
- **border** adds space (even if it’s only a pixel or two) between the margin and the padding.
- **margin** increases the space between the borders of a box and the borders of adjacent boxes. Margins are set using lengths, percentages, or the keyword auto and can have negative values. Margin is a shorthand property and accepts up to four values. If fewer than four values are set, the missing values are assumed based on the ones that are defined. Each of the margin properties can also accept a value of auto. Auto is useful only for horizontal centering, and so using auto for top and bottom margins will not center an element vertically. The order is `margin-top, margin-right, margin-bottom, margin-left`

**The Box Model Tip**: Always start by setting margin and padding to 0 for all elements to clear out all margins and paddings in the document. `box-sizing: border-box` tells the browser to account for any border and padding in the values you specify for an element's width and height. If you set an element's width to 100 pixels, that 100 pixels will include any border or padding you added, and the content box will shrink to absorb that extra width. This typically makes it much easier to size elements.
```
* {margin: 0;
  padding: 0;
  box-sizing: border-box;}
```

#### Background Image <a id="background-image"></a>

To add a background image, you must add it in css as `background-image: url()`, always add a background color as well in case the picture doesn't load.

Some of the properties to add to a background image are:
- background-repeat
- background-size
- background-position

#### Button Styling <a id="button"></a>

To style buttons, you can use the following properties:

- `Border Radius`: both px and %, example: {border-radius: 50%;}
- `box-shadow`: box Shadow on hover example: {box-shadow: ...;}
- `width`: both px and % to change the button size. By default, the size of a button is determined by its text content.
- `opacity`: creates a disabled look for button by adding transparency to the button, giving it a faded appearance. Example: {opacity: 0.5;}. 
- `cursor: not-allowed`: you can add the cursor property with a value of "not-allowed", which changes the cursor to a "no parking sign" symbol when hovering over the button.
- `.button:active`
- `transition`

#### Font Family <a id="font-family"></a>

- Serif: The most prominent style attribute of serif fonts is the presence of small, additional strokes by the edges of the letters. While initially used for ink printing purposes, the style is now associated with a sense of formality and elegance.Websites mainly use Serif for body text, as it is highly legible and helps readers quickly skim written content. Popular Serif fonts include Times New Roman, Cambria, and Garamond. 
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
10. <p style="font-family: Calibri">Calibri</p>
11. <p style="font-family: Optima">Optima</p>
12. <p style="font-family: Cambria">Cambria</p>
13. <p style="font-family: Garamond">Garamond</p>
14. <p style="font-family: Perpetua">Perpetua</p>
15. <p style="font-family: 'Brush Script'">Brush Script</p>
16. <p style="font-family: 'Lucida Bright'">Lucida Bright</p>

#### Display <a id="display"></a>

The display property specifies the display behavior (the type of rendering box) of an element.

- inline: displays an element as an inline element `(like <span>)`. Any height and width properties will have no effect
- block: displays an element as a block element `(like <p>)`. It starts on a new line and takes up the full width available.
- inline-block: The element itself is formatted as an inline element, but you can apply height and width values. inline-block brought a new way to create side by side boxes that collapse and wrap properly depending on the available space in the containing element. The major difference between inline-block and inline is that it allows us to set a width and height on the element, as for inline top and bottom margins and paddings are not respected. Now, the difference between inline-block and block is that, block, a line break happens after the element, so a block element doesn’t sit next to other elements.

##### Here are all the block-level elements in HTML:
```
<address> / <article> / <aside> / <blockquote> / <canvas> / <dd> / <div> / <dl> / <dt> / <fieldset> / <figcaption> / <figure> / <footer> / <form> / <h1>-<h6> / <header> / <hr> / <li> / <main> / <nav> / <noscript> / <ol> / <p> / <pre> / <section> / <table> / <tfoot> / <ul> / <video>
```
##### Here are all the inline elements in HTML:
```
<a> / <abbr> /<acronym> / <b> / <bdo> / <big> / <br> / <button> / <cite>/ <code> / <dfn> / <em> / <i> / <img> / <input> / <kbd> / <label> / <map> / <object> / <output> / <q> / <samp> / <script> / <select> / <small> / <span> / <strong> / <sub> / <sup> / <textarea> / <time> / <tt> / <var>
```
#### Link Styling

Links can be styled differently depending on their state. The four link states commonly used are:

- a:link - Represents a normal, unvisited link.
- a:visited - Represents a link that the user has visited.
- a:hover - Represents a link when the user hovers over it.
- a:active - Represents a link at the moment it is clicked.

`Text Decoration`: The text-decoration property controls the appearance of the link's text decoration, such as underlining. When set to none it removes the line under the links. Here are some commonly used text decoration values for styling links:
- Underline: Adds a line beneath the link text.
- Overline: Adds a line above the link text.
- Line-through: Adds a line through the link text.

#### Cascade

Specificity: A CSS declaration that is more specific will take precedence over less specific ones.
1. ID selectors (most specific selector)
2. Class selectors
3. Type selectors

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

- We've added `height: 100vh` to the `body`... this makes the body exactly the same height as the viewport. To stick the footer to the bottom you will need to use flex and change the direction to column.

this is some magical font-importing.  
you'll learn about it later.
@import url('https://fonts.googleapis.com/css2?family=Besley:ital,wght@0,400;1,900&display=swap');

position: fixed;?

## JavaScript

#### JavaScript can be added in two ways:

- External script: involves creating a separate file for the JavaScript and linking it inside of an HTML’s body, preferably towards the end. `<script src="javascript.js"></script>`
- Internal script: `<script> </script>`

JavaScript ignores multiple spaces. You can add white space to your script to make it more readable.

JavaScript statements can be grouped together in code blocks, inside curly brackets {...}. Variables declared inside a { } block cannot be accessed from outside the block. 
``` 
{
  let x = 2;
}
// x can NOT be used here
```

- #### JavaScript Display Possibilities

JavaScript can "display" data in different ways:

- Writing into an HTML element, using `innerHTML`: To access an HTML element, JavaScript can use the document.getElementById(id) method. The id attribute defines the HTML element. The innerHTML property defines the HTML content.
- Writing into the HTML output using `document.write()`: for testing purposes, it is convenient to use this method. Using document.write() after an HTML document is loaded, will delete all existing HTML.
- Writing into an alert box, using `alert()`
- Writing into the browser console, `using console.log()`
- You can also call the `window.print()` method in the browser to print the content of the current window

#### What Can JavaScript Do?

- Change HTML Content: `document.getElementById("demo").innerHTML = "Hello JavaScript";` this findss an HTML element (with id="demo"), and changes the element content (innerHTML) to "Hello JavaScript".
- Change HTML Attribute Values: For example, JavaScript can change the value of the src (source) attribute of an image. `<button onclick="document.getElementById('myImage').src='pic_bulbon.gif'">Turn on the light</button>`
- Change HTML Styles (CSS): `<button type="button" onclick="document.getElementById('demo').style.fontSize='35px'">Click Me!</button>`
- Hide HTML Elements: Hiding HTML elements can be done by changing the display style. `document.getElementById("demo").style.display = "none";`
- Show HTML Elements: Showing hidden HTML elements can also be done by changing the display style `document.getElementById("demo").style.display = "block";`

#### JavaScript Keywords

- `var`	Declares a variable
- `let`	Declares a block variable
- `const`	Declares a block constant
- `if`	Marks a block of statements to be executed on a condition
- `switch`	Marks a block of statements to be executed in different cases
- `for`	Marks a block of statements to be executed in a loop
- `function`	Declares a function
- `return`	Exits a function
- `try`	Implements error handling to a block of statements

#### JavaScript Values

The JavaScript syntax defines two types of values:

- Fixed values: called Literals, such as numbers and strings (text, written within double or single quotes). If you put a number in quotes, it will be treated as a text string.
- Variable values: var, let and const. A JavaScript variable can hold any type of data.

JavaScript has 8 Datatypes:
1. String
2. Number: NaN is a JavaScript reserved word indicating that a number is not a legal number. We can use isNaN() to find out if a value is a not a number.
3. Bigint
4. Boolean: true/false
5. Undefined: a variable without a value, has the value undefined. The type is also undefined.
6. Null
7. Symbol
8. Object: the object data type can contain: an object, an array, a date. 
  - // Object: objects are written with curly braces {}. `const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};` The object (person) in the example above has 4 properties: firstName, lastName, age, and eyeColor.
  - // Array object: `const cars = ["Saab", "Volvo", "BMW"];` arrays are written with square brackets.
  - // Date object: `const date = new Date("2022-03-25");`

#### Variables and Constants

JavaScript Variables can be declared either automatically or using var/let/const. It's a good programming practice to declare all variables at the beginning of a script.

Creating a variable in JavaScript is called "declaring" a variable, and we use the `let` keyword such as `let message;`. After the declaration, the variable has no value (technically it is undefined). To assign a value to the variable, use the equal sign: `message = 'Hello';` or `let message = 'Hello!'`. 

To declare a constant (unchanging) variable, use const: `const myBirthday = '18.04.1982';` Variables declared using const are called “constants”. They cannot be reassigned. An attempt to do so would cause an error. Being a “constant” just means that a variable’s value never changes. But there are constants that are known prior to execution (like a hexadecimal value for red) and there are constants that are calculated in run-time, during the execution, but do not change after their initial assignment. Capital-named constants are only used as aliases for “hard-coded” values. For example `const COLOR_RED = "#F00";`.

Declaring twice triggers an error. A variable should be declared only once.

There are two limitations on variable names in JavaScript:
1. The name must contain only letters, digits, or the symbols $ and _.
2. The first character must not be a digit.

There is a list of reserved words, which cannot be used as variable names because they are used by the language itself. For example: let, class, return, and function are reserved.

#### Operators

The numbers (in an arithmetic operation) are called operands. The operation (to be performed between the two operands) is defined by an operator.

Increment/decrement can only be applied to variables. Trying to use it on a value like 5++ will give an error.The operators ++ and -- can be placed either before or after a variable.

- “postfix form”: when the operator goes after the variable `counter++`.If we’d like to increment a value but use its previous value, we need the postfix form. counter++ returns the "old" value.
- “prefix form”: is when it goes before the variable `++counter`. If we’d like to increase a value and immediately use the result of the operator, we need the prefix form

`++`	Increment: ++ increases a variable by 1
`--`	Decrement: -- decreases a variable by 1

In JavaScript, the equal sign (=) is an **assignment operator**, not an "equal to" operator. The "equal to" operator is written like == in JavaScript.

`+=`	x += y	x = x + y
`-=`	x -= y	x = x - y
`*=`	x *= y	x = x * y
`/=`	x /= y	x = x / y
`%=`	x %= y	x = x % y
`**=`	x **= y	x = x ** y

Both ==  and ===  are used for comparisons and to find the degree of sameness or equality between the things we are comparing, they return true if they find equality and false otherwise. All the **comparison operators** can also be used on strings too. 

`==`	equal to: if the datatypes of the operands we are comparing are different, then the JavaScript Engine automatically converts one of the operands to be the same as the other one in order to make the comparison possible.
`===`	equal value and equal type
`!=`	not equal
`!==`	not equal value or not equal type
`>`	greater than
`<`	less than
`>=`	greater than or equal to
`<=`	less than or equal to
`?`	ternary operator

**Logical Operators**

- `&&`	logical and
- `||`	logical or
- `!`	logical not

**Type Operators**

- `typeof`	Returns the type of a variable
- `instanceof`	Returns true if an object is an instance of an object type.