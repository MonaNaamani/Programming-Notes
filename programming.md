# Programming Notes

#### Using Markdown for Note Taking

- Text formating: *italics* **bold** _combined_** ~~Scratch this.~~
- Colors: Use this code: <font color=red>Text</font>
- Numbered lists: Start with 1. followed by a space, then it starts numbering for you. Start each line with some number and a period, then a space.
    - To create a sub bullet, use a tab followed a dash and a space. You can also use an asterisk instead of a dash, and it works the same.
> Quoting: Use a greater than sign (>) and then a space, then type the text. Use the > symbol for every line you want to continue as a blockquote.
> If you want to add another quote inside a blockquote, you need to add multiple > symbols as per the level of quotes added.
- Links 
    - [I'm an inline-style link](https://www.google.com) 
    - [I'm an inline-style link with title](https://www.google.com "Google's Homepage") 
    - [I'm a relative reference to a repository file](../blob/master/LICENSE)
- Internal links: To link to a heading, use this code: [heading title](#heading-title) For the text in the parentheses, replace spaces and special characters with a hyphen.Alternatively, you can add an ID for a heading right above the title. Use this code: <a id="heading_ID"></a> Make sure that the heading_ID is unique within the notebook. Use this code for the link [heading title](#heading_ID)


## CSS basics

#### Class selectors 

* { } The universal selector will select elements of any type, hence the name “universal”, and the syntax for it is a simple asterisk.

Class selectors will select all elements with the given class, which is just an attribute you place on an HTML element. 

.alert-text { color: red;} 

Note the syntax for class selectors: a period immediately followed by the case-sensitive value of the class attribute. Another thing you can do with the class attribute is to add multiple classes to a single element as a space-separated list, such as class="alert-text severe-alert". 

To cut down on the repetition, we can group selectors together as a comma-separated list. .read,.unread { color: white; background-color: black;}

If we only want to apply a separate rule to the element that also has header as a second class we could chain both the class selectors together in our CSS like so: .subsection.header { color: red;} 

#### ID selectors 

Instead of a period, we use a hashtag immediately followed by the case-sensitive value of the ID attribute. An element can only have one ID. An ID cannot be repeated on a single page, and the ID attribute should not contain any whitespace at all.
We can also chain a class and an ID .subsection#preview { color: blue;}

#### Descendant combinator

A descendant combinator will only cause elements that match the 
last selector to be selected if they also have an ancestor (parent, grandparent, etc) that matches the previous selector. So something like .ancestor .child would select an element with the class child if it has an ancestor with the class ancestor.

#### CSS Properties

- Color
- Font Size
- Text-align
- Font-weight
- Font-family
- Background Color
- Background
- Height/Width (auto)
- Border
- Border Radius
- Adding CSS to HTML

#### CSS stylesheet

- External: involves creating a separate file for the CSS and linking it inside of an HTML’s opening and closing <head> tags with a self-closing <link> element: <head> <link rel="stylesheet" href="styles.css" /> </head> The href attribute is the location of the CSS file.

- Internal: With the internal method, you place all the rules inside of a pair of opening and closing <style> tags, which are then placed inside of the opening and closing <head> tags of your HTML file.

- Inline: <body> <div style="color: white; background-color: black;">...</div> </body>

## Cascade
Specificity: A CSS declaration that is more specific will take precedence over less specific ones.
ID selectors (most specific selector)
Class selectors
Type selectors
