# T1A1 Workbook

William Robertson

# Q1: **Identify** and **explain** common and important components and concepts of web development markup languages

Currently, web development is compromised of three different languages. **HTML**, or HyperText Markup Language, which represents a document's structure. MDN describes this as "a basic building block of the web" (1), as without HTML, there is no content to be displayed on the page. This isn't necessarily true with newer approaches to web content, which involve fetching content after an initial HTML page has been received, using JavaScript.

## HTML

HTML is composed of `tags`, which represent different elements on the page. A tag is a string or character surrounded by `<` and `>` characters. Most HTML tags _open_ and _close_. That is to say, any opened tag like `<p>` needs to be accompanied by a closing `</p>` tag. There are some HTML tags that do not require a closing tag, for example `<img>` and `<br>`.

Arguably, the three most important tags in HTML are `<html>` itself, which defines the start and end of the document, `<head>` which contains elements that are needed for rendering the page, but do not appear on the rendered page, and `<body>`, which specifically contains elements that display in the browser.

If a tag is inside another HTML tag, it's said to be a **child** of that element. In this way, HTML builds up a tree - with `<html>` as the root, containing `<head>` and `<body>`, and then building from there.

> There is one more important tag - to be properly processed by modern browsers, an opening tag of `<!DOCTYPE html>` is required. The reasons for this are historical, but it needs to accompany any HTML document to comply with this.

There are over 100 tags in the modern HTML 5 spec, including everything from `<h1>` to `<h6>` for headings, `<p>` for paragraphs, `<img>` for images, `<a>` tags for "anchors" - links to internal and external page content - to more esoteric tags like `<code>` for blocks of code, `<script>` for embedding JavaScript on the page or sourcing it externally, `<link>` for linking style sheets, and more.

With HTML 5, the most recent definition of the HTML spec, there was a recent shift towards **semantic elements**. These are elements that have meaning, unlike `<div>` which is meaningless and serves only to *div*ide content. These include tags like;

- `main`, for the main content of a page
- `article`, for an article that could be rendered elsewhere online
- `nav`, for navigation elements like links to other pages
- `header` & `footer` for the top and bottom of page content.

Every HTML tag can possess **attributes**. An attribute is an additional piece of information about the element. They don't appear as content, but affect the document. Examples include `class` and `id` that can be used in CSS, `href` for anchor links that represent the link destination, `src` for images that include the relative or absolute path to an image and more. They can be important for styling as mentioned above, for accessibility in the case of attributes like `alt` for alt-text, `for` for labelling input fields in a way that can be parsed by screen-readers, or in adjusting behaviour like `autoplay` for video and `autocomplete` for inputs.

With just HTML, a page would look rather plain, just a step above plaintext. Each browser applies some default styling, but they're quite barebones. To add significant styling to a HTML document, we need to add **CSS**.

## CSS

CSS stands for Cascading Style Sheets. CSS applies _styles_ to particular elements. It uses **selectors**, which are typically HTML elements, classes, or IDs, but in more complicated situations, can include pseudo-classes like `:hover`.

There are three ways to style an element with CSS. You can add a style **in-line** in the HTML itself, by adding a `style` attribute to an element. EG, `<h1 style="color:red">I'm red` would create an H1 element with a red colour. This can be useful, but can quickly get messy. The next is to add a `<style>` tag to the head of the document, and do styling in there. The most common way is to use an external stylesheet, or multiple external stylesheets. This is done using a `<link>` element, like this: `<link rel="stylesheet" href="./styles.css">`.

CSS is a fundamental part of the modern web, modifying the position, display, color, size of elements.

## JavaScript

The final element of web development is not really part of markup languages, but it is a fundamental part of the modern web. JavaScript is a **programming** language. It is used to add interactivity to the modern web. Mosts sites now extensively use JavaScript to do everything from listen to page events, change HTML elements on-the-fly, or even play games.

# Q2: Define the following features (packets, IP addresses, routers & routing, domains & DNS) and explain how each technology has contributed to the development of the internet.

## Packets

## IP Addresses

## Routers and Routing

## Domains and DNS

# Q3: Define the features of the following technologies (TCP, HTTP & HTTPS, web browsers: requests, rendering and developer tools) that are essential in terms of the development of the internet.

## TCP

## HTTP & HTTPS

## Web Browsers: Requests, Rendering and DevTools

### References

(1) MDN Web Docs (2018). HTML: HyperText Markup Language. [online] MDN Web Docs. Available at: https://developer.mozilla.org/en-US/docs/Web/HTML].
