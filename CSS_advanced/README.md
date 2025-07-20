# CSS Advanced - Quick Reference Cheat Sheet

## 🎨 CSS Fundamentals

### Basic Syntax
```css
selector {
    property: value;
    another-property: value;
}
```

## 🔗 Linking CSS to HTML

### ✅ External CSS (Recommended)
Link external stylesheet in the `<head>` section:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <link rel="stylesheet" href="styles.css">
    <link rel="stylesheet" href="css/main.css">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans">
</head>
<body>
    <h1>Hello CSS!</h1>
</body>
</html>
```

### ✅ Internal CSS
CSS inside `<style>` tags in `<head>`:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>My Page</title>
    <style>
        h1 {
            color: deepskyblue;
            text-align: center;
        }
        .highlight {
            background-color: yellow;
        }
    </style>
</head>
<body>
    <h1>Hello CSS!</h1>
</body>
</html>
```

### ✅ Inline CSS
CSS directly in HTML elements:
```html
<h1 style="color: deepskyblue; text-align: center;">Hello CSS!</h1>
<p style="font-size: 18px; margin: 20px;">Styled paragraph</p>
```

### CSS Application Methods Comparison

| Method | Example | Pros | Cons | Use Case |
|--------|---------|------|------|----------|
| **External** | `<link rel="stylesheet" href="styles.css">` | Reusable, cacheable, maintainable, separation of concerns | Extra HTTP request | Production sites, multiple pages |
| **Internal** | `<style>h1 { color: red; }</style>` | Page-specific, no extra request | Not reusable, mixes content with style | Single-page apps, email templates |
| **Inline** | `<p style="color: red;">Text</p>` | Highest specificity, quick fixes | Hard to maintain, not reusable, poor separation | Dynamic styles, overrides, testing |

### ⚠️ CSS Precedence Order (Highest to Lowest)
1. **Inline styles** (`style=""`) - Specificity: 1000
2. **IDs** (`#id`) - Specificity: 100  
3. **Classes, attributes, pseudo-classes** (`.class`, `[attr]`, `:hover`) - Specificity: 10
4. **Elements** (`div`, `p`) - Specificity: 1

```css
/* This will be overridden by inline styles */
#myId { color: blue !important; }    /* Specificity: 100 + !important */
.myClass { color: green; }           /* Specificity: 10 */
p { color: red; }                    /* Specificity: 1 */
```

```html
<!-- Inline style wins despite lower CSS specificity -->
<p id="myId" class="myClass" style="color: purple;">This text will be purple</p>
```

## 🎯 Selectors & Specificity

### Selector Types (Lowest to Highest Specificity)
```css
* { }                    /* Universal selector */
element { }              /* Element selector */
.class { }               /* Class selector */
#id { }                  /* ID selector */
element[attribute] { }   /* Attribute selector */
element:hover { }        /* Pseudo-class */
element::before { }      /* Pseudo-element */
```

### ✅ Selector Combinations
```css
.parent .child { }       /* Descendant */
.parent > .child { }     /* Direct child */
.element + .next { }     /* Adjacent sibling */
.element ~ .sibling { }  /* General sibling */
```

## 🎨 Colors & Values

### Color Formats
```css
.element {
    color: red;                    /* Named color */
    color: #ff0000;               /* Hex */
    color: #f00;                  /* Short hex */
    color: rgb(255, 0, 0);        /* RGB */
    color: rgba(255, 0, 0, 0.5);  /* RGB with alpha */
    color: hsl(0, 100%, 50%);     /* HSL */
    color: hsla(0, 100%, 50%, 0.5); /* HSL with alpha */
}
```

### CSS Variables
```css
:root {
    --primary-color: #3498db;
    --font-size: 16px;
    --spacing: 1rem;
}

.element {
    color: var(--primary-color);
    font-size: var(--font-size);
    margin: var(--spacing);
}
```

## 📏 Units & Values

### Absolute Units
- `px` - Pixels (most common)
- `pt` - Points
- `in` - Inches

### Relative Units
- `rem` - Relative to root element font-size
- `em` - Relative to parent element font-size
- `%` - Percentage of parent
- `vw/vh` - Viewport width/height
- `vmin/vmax` - Viewport minimum/maximum

```css
.element {
    font-size: 2rem;        /* 32px if root is 16px */
    padding: 1.2rem 2rem;   /* Responsive spacing */
    width: 50vw;            /* 50% of viewport width */
}
```

## 📦 Box Model

### Box Sizing
```css
/* Default - padding/border added to width */
.content-box {
    box-sizing: content-box;
}

/* Recommended - padding/border included in width */
.border-box {
    box-sizing: border-box;
}
```

### Box Model Properties
```css
.box {
    width: 200px;
    height: 100px;
    padding: 20px;           /* Inner spacing */
    border: 2px solid black; /* Border */
    margin: 10px;            /* Outer spacing */
}
```

## 🧱 Display & Layout

### Display Types
```css
.block { display: block; }           /* Full width, new line */
.inline { display: inline; }         /* Content width, same line */
.inline-block { display: inline-block; } /* Best of both */
.flex { display: flex; }             /* Flexbox container */
.grid { display: grid; }             /* Grid container */
.none { display: none; }             /* Hidden */
```

### Block vs Inline Elements

#### ✅ Block Elements
- 📏 Start on new line
- 📐 Take full width available
- 🔧 Can set width, height, margin, padding
- 🧱 Examples: `div`, `p`, `h1-h6`, `section`

#### ✅ Inline Elements
- 🧵 Stay on same line
- 📦 Only take content width
- ⚠️ Cannot set width/height
- 🔧 Can set horizontal margin/padding only
- 🔤 Examples: `span`, `a`, `strong`, `em`

## 🎨 Text Styling

### Text Properties
```css
.text {
    font-family: 'Arial', sans-serif;
    font-size: 16px;
    font-weight: bold;           /* or 700 */
    line-height: 1.5;           /* Minimum for accessibility */
    text-align: center;         /* left, right, center, justify */
    text-decoration: underline; /* none, underline, line-through */
    text-transform: uppercase;  /* lowercase, capitalize */
    letter-spacing: 0.1em;
    color: #333;
}
```

## 🎯 Pseudo-Classes vs Pseudo-Elements

### Pseudo-Classes (Single colon `:`)
Target element states:
```css
a:link { color: blue; }         /* Unvisited link */
a:visited { color: purple; }    /* Visited link */
a:hover { color: red; }         /* Mouse over */
a:active { color: orange; }     /* Being clicked */
a:focus { outline: 2px solid blue; } /* Keyboard focus */

li:first-child { font-weight: bold; }
li:nth-child(odd) { background: #f0f0f0; }
```

### Pseudo-Elements (Double colon `::`)
Create virtual elements:
```css
p::before {
    content: "→ ";
    color: blue;
}

p::after {
    content: " ←";
    color: red;
}

p::first-letter {
    font-size: 2em;
    float: left;
}
```

## 🌈 Backgrounds & Gradients

### Background Properties
```css
.background {
    background-color: #f0f0f0;
    background-image: url('image.jpg');
    background-size: cover;        /* contain, 100px 200px */
    background-position: center;   /* top, bottom, left, right */
    background-repeat: no-repeat;  /* repeat, repeat-x, repeat-y */
    
    /* Shorthand */
    background: #f0f0f0 url('image.jpg') center/cover no-repeat;
}
```

### Gradients
```css
/* Linear gradients */
.linear {
    background: linear-gradient(to right, #ff7e5f, #feb47b);
    background: linear-gradient(45deg, #667eea 0%, #764ba2 100%);
}

/* Radial gradients */
.radial {
    background: radial-gradient(circle, #ff7e5f, #feb47b);
    background: radial-gradient(ellipse at center, #667eea 0%, #764ba2 100%);
}
```

## 🔄 CSS Transforms

### 2D Transforms
```css
.transform-2d {
    transform: translate(50px, 100px);    /* Move */
    transform: rotate(45deg);             /* Rotate */
    transform: scale(1.5);                /* Scale */
    transform: skew(20deg, 10deg);        /* Skew */
    
    /* Multiple transforms */
    transform: translate(50px, 100px) rotate(45deg) scale(1.2);
}
```

### 3D Transforms
```css
.transform-3d {
    transform-style: preserve-3d;
    perspective: 1000px;
    
    transform: translateZ(50px);
    transform: rotateX(45deg);
    transform: rotateY(45deg);
    transform: rotate3d(1, 1, 0, 45deg);
}
```

## 🎬 CSS Animations

### Keyframes
```css
@keyframes slideIn {
    0% {
        transform: translateX(-100%);
        opacity: 0;
    }
    100% {
        transform: translateX(0);
        opacity: 1;
    }
}

.animated {
    animation: slideIn 0.5s ease-in-out;
}
```

### Animation Properties
```css
.element {
    animation-name: slideIn;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
    animation-delay: 0.5s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
    animation-fill-mode: forwards;
    
    /* Shorthand */
    animation: slideIn 2s ease-in-out 0.5s infinite alternate forwards;
}
```

### Transitions
```css
.button {
    background-color: blue;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: red;
}
```

## 🏗️ Grid Systems with Floats

### Float-Based Grid
```css
.container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
}

.row::after {
    content: "";
    display: table;
    clear: both;
}

.col {
    float: left;
    padding: 0 15px;
}

.col-1 { width: 8.33%; }
.col-2 { width: 16.66%; }
.col-3 { width: 25%; }
.col-4 { width: 33.33%; }
.col-6 { width: 50%; }
.col-12 { width: 100%; }
```

## 🎨 Modern Layout: Flexbox

### Flex Container
```css
.flex-container {
    display: flex;
    justify-content: center;    /* horizontal alignment */
    align-items: center;        /* vertical alignment */
    flex-direction: row;        /* row, column, row-reverse, column-reverse */
    flex-wrap: wrap;           /* nowrap, wrap, wrap-reverse */
    gap: 20px;                 /* spacing between items */
}
```

### Flex Items
```css
.flex-item {
    flex: 1;                   /* flex-grow: 1, flex-shrink: 1, flex-basis: 0% */
    flex-grow: 1;              /* how much to grow */
    flex-shrink: 0;            /* how much to shrink */
    flex-basis: 200px;         /* initial size */
    align-self: flex-start;    /* override container's align-items */
}
```

## 🎨 Modern Layout: CSS Grid

### Grid Container
```css
.grid-container {
    display: grid;
    grid-template-columns: 1fr 2fr 1fr;    /* 3 columns */
    grid-template-rows: auto 1fr auto;     /* 3 rows */
    gap: 20px;                             /* spacing */
    grid-template-areas: 
        "header header header"
        "sidebar main aside"
        "footer footer footer";
}
```

### Grid Items
```css
.grid-item {
    grid-column: 1 / 3;        /* span from column 1 to 3 */
    grid-row: 2;               /* place in row 2 */
    grid-area: header;         /* use named area */
}
```

## 🔧 CSS Reset & Normalization

### Basic Reset
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

html, body {
    height: 100%;
    font-family: Arial, sans-serif;
}
```

### Modern Reset
```css
*, *::before, *::after {
    box-sizing: border-box;
}

body, h1, h2, h3, h4, p, figure, blockquote, dl, dd {
    margin: 0;
}

img, picture {
    max-width: 100%;
    display: block;
}
```

## 🎯 Attribute Selectors

```css
/* Exact match */
a[href="https://example.com"] { color: blue; }

/* Contains */
a[href*="facebook"] { color: #3C5A99; }

/* Starts with */
a[href^="#"] { background-color: gold; }

/* Ends with */
a[href$=".org"] { color: red; }

/* Word in space-separated list */
[class~="highlight"] { background: yellow; }
```

## 🖼️ Icons: Web Fonts vs SVG

### Web Font Icons
```css
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css');

.icon {
    font-family: 'Font Awesome 6 Free';
    font-weight: 900;
}
```
**Pros**: Easy to style, scalable  
**Cons**: Extra HTTP request, limited customization

### SVG Icons
```css
.svg-icon {
    width: 24px;
    height: 24px;
    fill: currentColor;
}
```
**Pros**: Highly customizable, better performance  
**Cons**: More complex markup

## 🔧 Vendor Prefixes

### Common Prefixes
- `-webkit-` (Chrome, Safari, newer Opera)
- `-moz-` (Firefox)
- `-ms-` (Internet Explorer, Edge)
- `-o-` (Old Opera)

```css
.element {
    -webkit-transform: rotate(45deg);
    -moz-transform: rotate(45deg);
    -ms-transform: rotate(45deg);
    -o-transform: rotate(45deg);
    transform: rotate(45deg);
}
```

**Modern Approach**: Use tools like Autoprefixer to add prefixes automatically.

## 📍 Positioning

```css
.positioned {
    position: static;      /* Default */
    position: relative;    /* Relative to normal position */
    position: absolute;    /* Relative to positioned parent */
    position: fixed;       /* Relative to viewport */
    position: sticky;      /* Hybrid of relative and fixed */
    
    top: 10px;
    right: 20px;
    bottom: 30px;
    left: 40px;
    z-index: 999;
}
```

## ❌ Common Mistakes to Avoid
- Not using `box-sizing: border-box`
- Forgetting CSS reset/normalize
- Using `!important` excessively
- Not considering accessibility (contrast, focus states)
- Mixing layout methods unnecessarily

## 🔧 Validation & Tools
- [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- [Can I Use](https://caniuse.com/) - Browser compatibility
- [Autoprefixer](https://autoprefixer.github.io/) - Add vendor prefixes
- Browser Developer Tools

---
*Quick reference for CSS fundamentals, layout, and modern techniques*
