## CSS Basic Syntax

Basic CSS syntax follows this pattern:

```css
selector {
	property: value;
}
```

### Selectors

CSS selectors target HTML tags to apply styling. An example of a very simple selector is:

```css
p {
	property: value;
}
```

CSS classes can be selected using the period (`.`) before the name of the class in the stylesheet. Similarly, IDs can be selected using the hash symbol (`#`).

```css
.container {
	property: value;
}

`#logo` {
	property: value;
}
```

Note that the order in which selectors are used within the stylesheet is important. Any subsequent styling that references an element with previously defined styles will be overwritten.

#### Descendant Selectors

Descendant selectors will only select tags that are children of the parent tag.

```css
parent-tag child-tag {
	property: value;
}

<!-- Example -->

ul li {
	background-color: black;
}
```

Selectors can be chained together using a comma between selectors.

```css
h1, h2, h3 {
	property: value;
}
```

#### Additional Operators

The `+` sign can be used to target only adjacent elements.

```css
ul + p {
	property: value;
}
```

The above example would only style paragraph tags that are immediately preceded by an unordered list.

The `>` operator can be used to only select direct child elements of a parent.

```css
.container > ul {
	property: value;
}
```

Using this syntax will only select child elements that are direct descendants of of the container class. If there are further `ul` elements embededd within the unordered list, those will not be targeted. For that instance, it's best to use the `parent-element child-element { ... }` syntax (i.e. `.container ul { ... }`.

The tilde (`~`) operator can be used in place of the the `+` operator when all elements of type need to be selected following a parent element. 

```css
ul ~ p {
	property: value;
}
```

In this example, all `<p>` elements that follow `<ul>` elements would be selected, whereas using `ul + p` would select _only_ the `<p>` elements that immediately follow a `<ul>` (i.e. no nested elements).

### Pseudo-Classes

Pseudo-selectors are a modifier of selectors that will only modify a tag when certain conditions are met / have occurred.

```css
selector:action {
	property: style;
}

<!-- Example -->

a:hover {
	color: red;
}
```

#### Common Pseudo-Classes

- `:first-child`: only selects the first child element of the parent
- `:last-child`: only selects the last child element of the parent
- `:visited`: only selects anchor elements which have been previously visited / clicked on
- `:link`: only selects anchor elements which have NOT previously been visited / clicked on
- `:checked`: selects UI elements that have been checked (i.e. radio buttons or checkboxes)
- `:before` and `:after`: can be used to prepend or append content to an element
- `:hover`: applies styling when a user hovers over an element
- `:not(selector)`: will select elements of a particular class, excluding those within parentheses (i.e. `ul:not(#nav) { ... }`)
- `::pseudoElement` - selects a portion of the element specified after the double-colon (i.e. `p::first-line` will select the first line of every paragraph element)
- `:nth-child(n)`: selects the `n` child of the parent element. It's possible to use `odd` or `even` in place of `n`
- `:nth-of-type(n)`: selects the `n` child of the parent element where the type is specified (i.e. `li:nth-of-type(2)` would select the second `<li>` element)

### Attribute Selectors

A CSS attribute selector can be used to select all HTML elements on a page that possess a specified HTML attribute.

```css
element[attribute] {
	property: value;
}

<!-- Example -->

input[type=submit] {
	property: value;
}
```
The above example would select all `<input>` elements that have an attribute of `type="submit"`. It's important to note that quotes are not necessary in the CSS selector for the attribute value.

There are several additional helper operators that assist in making more specific attribute selections:

- `element[attr*=value] { ... }`: This will find any element where the value is contained somewhere within the attribute value. For example `a[href*="goo"]` would select any anchor elements with an attribute of `http://google.com` or even `http://www.goodygoody.com`.
- `element[attr^=value] { ... }`: This targets all elements whose attribute begins with the specified value (i.e. `a[href^="http"]` selects all anchor elements that have an href value that begins with `http`)
- `element[attr$=value] { ... }`: The same as the `^` symbol, but looks for the specified value at the end. An example of this would be `img[src$=".png"]`.

## Borders

CSS borders can be applied using the `border` property. It's also possible to use separate and more specific border properties.

```css

element {
	border: width style color;
}

element {
	border-width: 1px;
}

element {
	border-style: dashed;
}

element {
	border-color: #FF0000;
}

<!-- Examples -->

div {
	border: 3px solid #000000;
}

div {
	border-width: 2px;
}

div {
	border-style: dotted;
}

div {
	border-color: #00FF00;
}
```

## Box Model

The box model is the method by which HTML elements are constructed and CSS uses to manipulate the size and spacing of elements.

..............................................
:                                            :
:    ------------------------------------    :
:(1) |                                  |    :
:    |          Element Content         |    :
:   (2)                                 |    :
:    |                                  |    :
:    |  (3)                             |    :
:    |                                  |    :
:    ------------------------------------    :
:                                            :
:.............................................

- 1 = Margin
- 2 = Border
- 3 = Padding

Margin and padding can be manipulated on each side. In order to center a block element on the page, it's possible to use `margin-left: auto` and `margin-right: auto`.

The values of the margin and padding properties are set in clockwise motion beginning with the top (i.e. top-right-bottom-left).

```css
element {
	margin: 0 auto;
}

element {
	margin: 0 0 0 10px;
}

element {
	padding-top: 10px;
}
```

## Floats and Positioning

### Floats

Floats enable items to be stacked horizontally (i.e. two items stacked in a row). Each subsequent item's position is determined by the previous item's position, allowing for interesting layouts similar to those in magazine articles where an image is embedded into the text of the article.

There are 4 possible values for the CSS float property:

- **left** - the element will float to the left side of its containing block
- **right** - the element will float to the right side of its containing block
- **none** - the element will not have any float associated with it
- **inherit** - the element will inherit the float property of its parent element

### Clearing Floats

It's common to need to remove a float property once it has been set on an element or a parent element. There are several ways to accomplish this: the empty div method, the default method, the overflow method and the clearfix method. Of these, the default and clearfix methods are the most widely recommended.

**The Empty Div Method**

This method consists of simply putting an empty `<div>` element after the float element, and assigning the clear property a value of 'both'.

**The Default Method**

The default way to clear a float is to simply apply the `clear: both` property to the subsequent element on the page. However, this is not always possible and is why additional clearing methods exist.

**The Overflow Method**

 This method requires the overflow property of the parent element to be set to `auto` or `hidden`. this will force the parent element to expand and encompass the floating element, and thus any subsequent elements will not have a float property.

 **The Clearfix Method**

 When this method is used on a parent element, child elements will self-clear. This is a very robust way to clear, and accounts for older browsers.

 ```css
 .group:before,
 .group:after {
 	content: "";
 	display: table;
 }
 .group:after {
 	clear: both;
 }
 .group {
 	zoom: 1; /* IE6&7 support */
 }

### Positioning



- Units of measure
	- em
	- rem
	- percentage
	- px
- Modify DOM elements (i.e. text)
- Browser prefixes