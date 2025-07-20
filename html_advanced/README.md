# HTML Advanced - Quick Reference Cheat Sheet

## 🏷️ HTML Elements
Each element typically has:
```html
<opening-tag> content </closing-tag>
```

Some elements are self-closing:
```html
<img src="image.jpg" alt="A description" />
<br />
<hr />
```

## 🧩 Attributes
Attributes give extra info and are written inside the opening tag. ✅ Example:
```html
<a href="https://example.com" target="_blank">Visit Example</a>
```
- `href`: link destination
- `target="_blank"`: open in a new tab

## 🧱 Nesting Rules
- Tags must be properly nested and closed
- Block elements can contain inline elements, but not the other way ✅ Example:
```html
<p>This is a <strong>bold</strong> word.</p>
```

## ⚙️ Meta & Structure Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<!DOCTYPE html>` | Declares document as HTML5 | `<!DOCTYPE html>` |
| `<html>` | Root of the HTML document | `<html lang="en" dir="ltr">` |
| `<head>` | Contains meta-info (not visible) | `<head><title>My Page</title></head>` |
| `<title>` | Browser tab title | `<title>Homepage</title>` |
| `<meta>` | Metadata (charset, viewport, description) | `<meta charset="UTF-8">` |
| `<link>` | Links external resources like CSS | `<link rel="stylesheet" href="style.css">` |

### ✅ Complete Document Structure:
```html
<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
    <title>Page Title - Site Name</title>
    <meta name="description" content="Brief page description">
    <link rel="icon" type="image/x-icon" href="./favicon.ico">
    <link rel="icon" type="image/png" href="./favicon.png">
</head>
<body>
    <!-- Content here -->
</body>
</html>
```

## 🧱 Semantic Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<section>` | Thematic grouping of content | `<section><h2>About</h2><p>Info</p></section>` |
| `<article>` | Self-contained content block | `<article><h3>Blog Post</h3><p>...</p></article>` |
| `<header>` | Intro content for a page or section | `<header><h1>Welcome</h1></header>` |
| `<footer>` | Footer with metadata or links | `<footer>© 2024 MySite</footer>` |
| `<nav>` | Navigation bar | `<nav><a href="#home">Home</a></nav>` |
| `<main>` | Main content of the page | `<main><section>...</section></main>` |
| `<aside>` | Sidebar or additional content | `<aside><p>Tips</p></aside>` |

## 📦 Grouping Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<div>` | Generic block-level container | `<div class="wrapper">...</div>` |
| `<span>` | Generic inline container | `<span class="highlight">Text</span>` |

## 📝 Text Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<h1>` to `<h6>` | Headings from largest to smallest | `<h2>Section Title</h2>` |
| `<p>` | Paragraph of text | `<p>This is a paragraph.</p>` |
| `<br>` | Line break (no closing tag) | `Line 1<br>Line 2` |
| `<hr>` | Horizontal rule / thematic break | `<hr>` |
| `<strong>` | Emphasized strong text (usually bold) | `<strong>Important</strong>` |
| `<em>` | Emphasized text (usually italic) | `<em>Highlighted</em>` |
| `<mark>` | Highlighted text | `<mark>highlighted</mark>` |
| `<code>` | Inline code | `<code>&lt;div&gt;</code>` |
| `<pre>` | Preformatted text block | `<pre><code>Code block</code></pre>` |

## 📋 List Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<ul>` | Unordered (bulleted) list | `<ul><li>Item A</li><li>Item B</li></ul>` |
| `<ol>` | Ordered (numbered) list | `<ol><li>Step 1</li><li>Step 2</li></ol>` |
| `<li>` | List item (used in ul or ol) | `<li>Item</li>` |

## 🔗 Media Elements

| Element | Purpose | Example |
|---------|---------|---------|
| `<a>` | Anchor / hyperlink | `<a href="https://example.com">Visit Site</a>` |
| `<img>` | Displays an image | `<img src="logo.png" alt="Company Logo">` |
| `<video>` | Embeds a video | `<video controls><source src="video.mp4"></video>` |
| `<audio>` | Embeds audio | `<audio controls><source src="audio.mp3"></audio>` |
| `<iframe>` | Embeds another web page or content | `<iframe src="page.html"></iframe>` |

## 🖼️🎵🎬 Embedding Media in HTML

### 🖼️ Image
Use the `<img>` tag to embed an image. ✅ Example:
```html
<img src="image.jpg" alt="A description" width="300" height="200" />
```
- `src`: path or URL to the image
- `alt`: alternative text (important for accessibility)
- `width` / `height`: optional sizing

### 🎵 Audio
Use the `<audio>` tag to embed sound files. ✅ Example:
```html
<audio controls>
    <source src="audio.opus" type="audio/ogg; codecs=opus">
    <source src="audio.ogg" type="audio/ogg; codecs=vorbis">
    <source src="audio.mp3" type="audio/mpeg">
    Sorry, your browser doesn't support audio element
</audio>
```
- `controls`: shows built-in play/pause UI
- `<source>`: defines audio file and format
- Fallback text appears if audio isn't supported

### 🎬 Video
Use the `<video>` tag to embed video files. ✅ Example:
```html
<video src="https://example.com/video.mp4" controls loop 
       poster="https://example.com/thumbnail.jpg">
    Sorry, your browser doesn't support HTML5 video
</video>
```
- `controls`: shows play/pause/volume bar
- `loop`: video repeats automatically
- `poster`: thumbnail image shown before play
- Add multiple `<source>` formats (.mp4, .webm, .ogg) for better compatibility

### 🎛️ Interactive Elements
```html
<!-- Details - Default collapsed -->
<details>
    <summary>Show/Hide me</summary>
    <p>Hidden content that can be toggled.</p>
</details>

<!-- Details - Always open -->
<details open>
    <summary>Always open</summary>
    <p>This content is visible by default.</p>
</details>
```

## 📊 Tables
```html
<table>
    <caption>Star Wars Trilogy Data</caption>
    <thead>
        <tr>
            <th scope="col">Title</th>
            <th scope="col">Director</th>
            <th scope="col">Release Date</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <th scope="row">Star Wars: Episode IV - A New Hope</th>
            <td>George Lucas</td>
            <td>May 25th, 1977</td>
        </tr>
    </tbody>
</table>
```

## 📝 Forms
```html
<form action="/submit" method="post">
    <label for="name">Name:</label>
    <input type="text" id="name" name="name" required>
    
    <label for="email">Email:</label>
    <input type="email" id="email" name="email" required>
    
    <button type="submit">Submit</button>
</form>
```

## 🧩 HTML Inline vs Block Elements

### ✅ Block Elements
- 📏 Start on a new line
- 📐 Take full width of the parent container
- 🔧 Can set width, height, margin, padding
- 🧱 Common: `<div>`, `<p>`, `<h1>`–`<h6>`, `<ul>`, `<section>`

### ✅ Inline Elements
- 🧵 Do not start on a new line
- 📦 Only take up as much width as content
- ⚠️ Cannot set width / height (ignored)
- 🔧 Can set horizontal padding / margin
- 🔤 Common: `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`

## ♿ Accessibility Essentials
- Always include `alt` attributes for images
- Use proper heading hierarchy
- Associate labels with form inputs
- Include `lang` attribute on `<html>`
- Use semantic elements over generic divs

## ❌ Common Mistakes to Avoid
- Missing `alt` attributes on images
- Using headings for styling instead of hierarchy
- Improper nesting (e.g., `<p><div></div></p>`)
- Using `<div>` when semantic elements exist
- Missing form labels

## 🔧 Validation Tools
- [W3C Markup Validator](https://validator.w3.org/)
- [WAVE Web Accessibility Evaluator](https://wave.webaim.org/)
- Browser Developer Tools

---
*Quick reference for HTML5 semantic markup and best practices*
