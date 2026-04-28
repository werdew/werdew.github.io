---     
title: HTML
layout: default
nav_order: 3
---

# HTML Reference

**Official resources**  
• [HTML Living Standard](https://html.spec.whatwg.org/)  
• [MDN Web Docs — HTML elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Element)

## Basic Document Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
</head>
<body>
    <!-- Main content -->
</body>
</html>
```

## Head Section
Recommended order for \<head> elements:
1. charset first (encoding)
2. viewport for mobile rendering
3. title early (shows in tab quickly)
4. description &amp; author for SEO
5. CSS link last

```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Page Title</title>
    <meta name="description" content="page description">
    <meta name="author" content="werdew">
    <link rel="stylesheet" href="styles.css">
</head>
```

## Tags
Tags let you containerise groups of elements on your webpage so they can be easily targeted for CSS styling and JavaScript. Semantic tags describe the purpose of the content (for maintainability and SEO). Non-semantic tags are generic containers to be used when no semantic tag fits.

```html
<header>...</header>
<nav>...</nav>
<main>...</main>
<article>...</article>
<section>...</section>
<aside>...</aside>
<footer>...</footer>

<div>...</div>
<span>...</span>
```

It is best to use semantic tags whenever possible:
- `<header>` for introductory content such as logos and navigation,
- `<nav>` for major navigation links,
- `<main>` for the central unique content of the page (only once per page),
- `<article>` for self-contained pieces like blog posts or products,
- `<section>` for thematic groupings of related content,
- `<aside>` for related but separate content such as sidebars or ads, and
- `<footer>` for closing information like copyright or legal notes.

Non-semantic containers are fallback options:
- `<div>` for generic block-level for layout and grouping
- `<span>` generic inline for small pieces of text.


## Text & Formatting
```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 5</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>

<p>Paragraph</p>
<strong>Bold</strong>
<em>Italic</em>
<u>Underline</u>
<s>Strikethrough</s>
<br>Line break
<!-- Comment -->
```

## Lists
```html
<!-- Unordered List -->
<ul>
    <li>First item</li>
    <li>Second item</li>
</ul>

<!-- Ordered List -->
<ol>
    <li>First item</li>
    <li>Second item</li>
</ol>
```

## Links & Images
The basic link element is `<a></a>`, the `target="_blank"` opens the link in a new tab (user stays on page), the `rel="noopener"` blocks the new page from accessing, `noreferrer` hides the HTTP Referer header.

```html
<!-- Links -->
<a href="https://example.com">Simple link</a>
<a href="/about" target="_blank" rel="noopener">Open in new tab</a>

<!-- Images -->
<img src="image.jpg" alt="Description" width="600" height="400">

<!-- Video / Audio (HTML5) -->
<video controls><source src="video.mp4" type="video/mp4"></video>
<audio controls><source src="audio.mp3" type="audio/mpeg"></audio>
```

## Tables
```html
<table>
    <thead>
        <tr>
            <th>Header 1</th>
            <th>Header 2</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Data 1</td>
            <td>Data 2</td>
        </tr>
    </tbody>
</table>
```

## Forms
```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>

    <label for="email">Email:</label>
    <input type="email" id="email" name="email">

    <label for="password">Password:</label>
    <input type="password" id="password" name="password>

    <button type="submit">Submit</button>
</form>
```
The `action` and `submit` attributes tell the browser where and how to send the data.
The attribute `required` makes the field mandatory to submit.
