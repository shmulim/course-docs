[HTML 5 Syntax](#html5-syntax) | [HTML 5 Forms](#html5-forms)

## HTML Basic Syntax

Basic HTML site:
```html
<html>
	<head>
		<title></title>
	</head>
	<body>

	</body>
</html>
```

The HTML [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) tag should be used to include JavaScript and jQuery scripts. This should be done just before the closing `<body>` tag.

## HTML5 Syntax

### `<!DOCTYPE html>`

Communicates to the browser that the page will use HTML5 content. This should be placed before the `<html>` tag. [More info here.](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Introduction_to_HTML5)

### `<meta>`

This tag represents any metadata information that cannot be used in other meta elements (i.e. `<link>`, `<style>`, etc.). In HTML5, the character set can be defined using the `charset` attribute.
```html
<meta charset="UTF-8">
```

In addition, the `<meta>` tag is often used to ensure the site loads in a [mobile-friendly format](https://css-tricks.com/snippets/html/responsive-meta-tag/). The meta tag should be used within the `<head>` element.
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### `<script>`

In HTML5, the `type="text/javascript"` attribute is no longer needed. It's inferred that a script file will be a text JavaScript file.

```html
<script src="file.js"></script>
```

### `<link>`

In HTML5, the `type="text/css"` attribute is no longer needed. It's inferred that the file type is CSS for the `<link>` element.

```html
<link rel="stylesheet" href="main.css">
```

### `<header>`

This element is used to represent a group of navigational aids. It represents the [header information of an HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header) `<article>`. This element typically contains a logo or an `<h1>` element.

### `<footer>`

[The `<footer>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer) is typically used at the end of an HTML `<article>` or `<section>` and contains information about the article or section of the article (i.e. information about the author of the blog post).

### `<section>`

A generic [section](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) of content; a thematic grouping of content. Typically within an `<article>`. The `<section>` element is used for grouping together thematically related content, whereas a `<div>` element has no specific semantic meaning.

### `<article>`

[An `<article>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) represents a self-contained composition within an HTML document. This is intended to be used multiple times (i.e. syndication). This can be a news / magazine article, forum post, blog entry, etc. Nested article elements are related to the outer element.

### `<nav>`

The `<nav>` element represents a section that links to other pages or parts within a page. This element is most commonly used for navigational menus.

### `<main>`

Represents the main content of the document or application. There should not be more than one `<main>` element in a document.

### Example Site
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <title>Sample Website</title>
  </head>
  <body>
    <article>
      <header>
        <h2>Movie Review</h2>
      </header>
      <section>
        <p>Empire Strikes Back is the best Star Wars movie!</p>
        <footer>
          Posted by John Doe on <time datetime="1985-03-24">March 24</time>
        </footer>
      </section>
    </article>
  </body>
</html>
```

## HTML5 Forms

### Input Types

There are several new form input options in HTML5. If the type specified is not supported by the browser, it will default to a type of `text`.

#### Search

```html
<input type="search" />
```

This will create a search box with rounded corners and the ability to clear out the search content by clicking a small "X" on the right-hand side of the input. On mobile devices, the primary button will change to "Search."

#### Email

```html
<input type="email" />
```

On mobile devices, this input box will show useful keyboard functions like the @ symbol, underscore and period (i.e. this input loads an alternative and more relevant keyboard on a mobile device).

#### URL

```html
<input type="url" />
```

On mobile devices, this input box will show useful keyboard functions like the / symbol, '.com' and period (i.e. this input loads an alternative and more relevant keyboard on a mobile device).

#### Date

```html
<input type="date" />
```

This will change the input to a drop-down calendar date picker, allowing dates to be more easily chosen. Alternatively, both `type="month"` and `type="week"` are available for similar types of input.

#### TEL

```html
<input type="tel" />
```

On mobile devices, this input box will change to be the telephone keyboard (i.e. numpad).

#### Number

```html
<input type="number" />
```

On mobile devices, this input method will change to have numbers on the top row of the keyboard. Additionally, this will allow users to increment the numbers up and down using buttons on the right.

#### Range

```html
<input type="range" />
```

Provides a slider for choosing a number value.

### Form Elements

#### Datalist

The `<datalist>` form element represents a list of predefined options that are used by other form controls. These options will show up as auto-complete options below the text form element.

```html
<input type="text" list="fruits">
  <datalist id="fruits">
    <option value="Apple" />
    <option value="Orange" />
    <option value="Banana" />
  </datalist>
</body>
```

It's important to note that the list attribtue value and the id of the datalist must match.

### Form Attributes

#### Placeholder

The placeholder attribute will be the value present within the form element until the user interacts with that element. If all information in the element is deleted or cleared, the placeholder text will return.

```html
<input type="text" placeholder="Luke, I am your father...">
```

#### Autofocus

Automatically focuses the cursor on the specified input element when the page is rendered.

```html
<input type="text" autofocus>
```

#### Required

If this attribute is present within a form element, the user will receive an error message if left blank.

```html
<input type="email" required>
```
