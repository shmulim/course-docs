#### HTML Basic Syntax

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

#### HTML5 Syntax

**`<!DOCTYPE html>`**

Communicates to the browser that the page will use HTML5 content. This should be placed before the `<html>` tag. [More info here.](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5/Introduction_to_HTML5)

**`<meta>`**

This tag represents any metadata information that cannot be used in other meta elements (i.e. `<link>`, `<style>`, etc.). In HTML5, the character set can be defined using the `charset` attribute.
```html
<meta charset="UTF-8">
```

In addition, the `<meta>` tag is often used to ensure the site loads in a [mobile-friendly format](https://css-tricks.com/snippets/html/responsive-meta-tag/). The meta tag should be used within the `<head>` element.
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

**`<header>`**

This element is used to represent a group of navigational aids. It represents the [header information of an HTML](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/header) `<article>`. This element typically contains a logo or an `<h1>` element.


**`<footer>`**

[The `<footer>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/footer) is typically used at the end of an HTML `<article>` or `<section>` and contains information about the article or section of the article (i.e. information about the author of the blog post).

**`<section>`**

A generic [section](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/section) of content; a thematic grouping of content. Typically within an `<article>`.

**`<article>`**

[An `<article>` element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/article) represents a self-contained composition within an HTML document. This is intended to be used multiple times (i.e. syndication). This can be a news / magazine article, forum post, blog entry, etc. Nested article elements are related to the outer element.

#### Example Site
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




