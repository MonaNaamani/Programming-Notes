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
- `<li>` List
- `<dl>` Description List
- `<dt>` Term In Description List
- `<dd>` Definition/Description Of A Term In Description List
- `<!--...-->` Defines a comment
- `<button>` Defines a clickable button
- `<hr>` Separates content (or defines a change)
- `<a>` Hyperlink. The href attribute specifies the URL of the page the link goes to: `<a href="https://www.w3schools.com">Visit W3Schools</a>`

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

#### CSS Properties

- Color
- Font-size
- Text-align
- Font-weight
- Background Color
- Height/Width
- Line-height
- [Background-image](#background-image)
- [Font-family](#font-family)
- [Display](#display)
- **padding** increases the space between the border of a box and the content of the box.
- **border** adds space (even if it’s only a pixel or two) between the margin and the padding.
- **margin** increases the space between the borders of a box and the borders of adjacent boxes. Margins are set using lengths, percentages, or the keyword auto and can have negative values. Margin is a shorthand property and accepts up to four values. If fewer than four values are set, the missing values are assumed based on the ones that are defined. Each of the margin properties can also accept a value of auto. Auto is useful only for horizontal centering, and so using auto for top and bottom margins will not center an element vertically. The order is `margin-top, margin-right, margin-bottom, margin-left`

**The Box Model Tip**: Always start by setting margin and padding to 0 for all elements to clear out all margins and paddings in the document.

#### Background Image <a id="background-image"></a>

To add a background image, you must add it in css as `background-image: url()`, always add a background color as well in case the picture doesn't load.

Some of the properties to add to a background image are:
- background-repeat
- background-size
- background-position

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
#### Cascade

Specificity: A CSS declaration that is more specific will take precedence over less specific ones.
1. ID selectors (most specific selector)
2. Class selectors
3. Type selectors

## Flexbox <a id="Flexbox"></a>

Flexbox is a way to arrange items into rows or columns. These items will flex (i.e. grow or shrink) based on some simple rules that you can define.
flex: 1 equates to: flex-grow: 1, flex-shrink: 1, flex-basis: 0.
flex-grow expects a single number as its value, and that number is used as the flex-item’s “growth factor”. When we applied flex: 1 to every div inside our container, we were telling every div to grow the same amount. The result of this is that every div ends up the exact same size. If we instead add flex: 2 to just one of the divs, then that div would grow to 2x the size of the others.
If you do not want an item to shrink then you can specify flex-shrink: 0;. You can also specify higher numbers to make certain items shrink at a higher rate than normal.

Here’s an example. Note that we’ve also changed the flex-basis for reasons that will be explained shortly. If you shrink your browser window you’ll notice that .two never gets smaller than the given width of 250px, even though the flex-grow rule would otherwise specify that each element should be equally sized.

flex-basis simply sets the initial size of a flex item, so any sort of flex-growing or flex-shrinking starts from that baseline size. The shorthand value defaults to flex-basis: 0%. The reason we had to change it to auto in the flex-shrink example is that with the basis set to 0, those items would ignore the item’s width, and everything would shrink evenly. Using auto as a flex-basis tells the item to check for a width declaration (width: 250px).

There is a difference between the default value of flex-basis and the way the flex shorthand defines it if no flex-basis is given. The actual default value for flex-basis is auto, but when you specify flex: 1 on an element, it interprets that as flex: 1 1 0. If you want to only adjust an item’s flex-grow you can simply do so directly, without the shorthand. Or you can be more verbose and use the full 3 value shorthand flex: 1 1 auto, which is also equivalent to using flex: auto.