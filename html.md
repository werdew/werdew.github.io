---     
title: HTML
layout: default
nav_order: 3
---

# HTML Reference

## Basic Structure
```html
&lt;!DOCTYPE html&gt;
&lt;html lang="en"&gt;
&lt;head&gt;
  		&lt;title&gt;Title&lt;/title&gt;
&lt;/head&gt;
&lt;body&gt;

&lt;/body&gt;
&lt;/html&gt;
```

## Headings
```html
&lt;h1&gt;Heading 1&lt;/h1&gt;
&lt;h2&gt;Heading 2&lt;/h2&gt;
&lt;h3&gt;Heading 3&lt;/h3&gt;
&lt;h4&gt;Heading 4&lt;/h4&gt;
&lt;h5&gt;Heading 5&lt;/h5&gt;
&lt;h6&gt;Heading 6&lt;/h6&gt;
```

## Text Formatting
```html
&lt;p&gt;Paragraph&lt;/p&gt;
&lt;br&gt;
&lt;strong&gt;Bold&lt;/strong&gt;
&lt;em&gt;Italic&lt;/em&gt;
&lt;u&gt;Underline&lt;/u&gt;
&lt;s&gt;Strikethrough&lt;/s&gt;
```

## Lists
```html
&lt;ul&gt;
&lt;li&gt;Unordered item&lt;/li&gt;
&lt;/ul&gt;
&lt;ol&gt;
&lt;li&gt;Ordered item&lt;/li&gt;
&lt;/ol&gt;
```

## Links & Images
```html
&lt;a href="url"&gt;Link&lt;/a&gt;
&lt;img src="image.jpg" alt="description"&gt;
```

## Tables
```html
&lt;table&gt;
&lt;tr&gt;
&lt;th&gt;Header&lt;/th&gt;
&lt;/tr&gt;
&lt;tr&gt;
&lt;td&gt;Data&lt;/td&gt;
&lt;/tr&gt;
&lt;/table&gt;
```

## Forms
```html
&lt;form&gt;
&lt;input type="text"&gt;
&lt;input type="password"&gt;
&lt;button&gt;Submit&lt;/button&gt;
&lt;/form&gt;
```

## Div & Span
```html
&lt;div&gt;Block&lt;/div&gt;
&lt;span&gt;Inline&lt;/span&gt;
```

## Comments
```html
&lt;!-- Comment --&gt;
```

## Head Section (Recommended Order)
<p><strong>Recommended order for &lt;head&gt; elements:</strong><br>
1. charset first (encoding)<br>
2. viewport for mobile rendering<br>
3. title early (shows in tab quickly)<br>
4. description &amp; author for SEO<br>
5. CSS link last</p>
```html
&lt;head&gt;
&lt;meta charset="UTF-8"&gt;
&lt;meta name="viewport" content="width=device-width, initial-scale=1.0"&gt
&lt;title&gt;Title&lt;/title&gt;
&lt;meta name="description" content="page description"&gt;
&lt;meta name="author" content="werdew"&gt;
&lt;link rel="stylesheet" href="main.css" type="text/css"&gt;
&lt;/head&gt;
```
