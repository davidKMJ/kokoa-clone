# kokoa-clone

## Table of Contents

1. [HTML Fundamentals](#html-fundamentals)
2. [CSS Basics](#css-basics)
3. [Layout & Positioning](#layout--positioning)
4. [Advanced CSS](#advanced-css)
5. [Responsive Design](#responsive-design)
6. [CSS Architecture](#css-architecture)

---

## HTML Fundamentals

### Document Structure

Every HTML document needs proper structure with semantic elements:

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Page Title</title>
        <link rel="stylesheet" href="css/styles.css" />
    </head>
    <body>
        <!-- Content goes here -->
    </body>
</html>
```

**Example in project**: See `index.html` for complete document structure.

### Semantic HTML Elements

Use semantic elements to give meaning to your content:

-   `<header>` - Page or section header
-   `<main>` - Main content area
-   `<nav>` - Navigation links
-   `<section>` - Thematic grouping of content
-   `<article>` - Self-contained content
-   `<aside>` - Sidebar content
-   `<footer>` - Page or section footer

**Example in project**: Check `friends.html` for semantic structure with header, main, and nav elements.

### Form Elements

HTML provides various input types and form controls:

```html
<form action="friends.html" method="get" id="login-form">
    <input
        name="username"
        type="text"
        placeholder="Email or phone number"
        required
    />
    <input name="password" type="password" placeholder="Password" required />
    <input type="submit" value="Log In" />
    <a href="#">Find Account</a>
</form>
```

**Example in project**: See `index.html` for login form implementation.

### HTML Attributes

Attributes provide additional information about elements:

-   `class` - CSS class selector
-   `id` - Unique identifier
-   `src` - Source URL for media
-   `alt` - Alternative text for images
-   `href` - Link destination
-   `type` - Input type specification
-   `placeholder` - Input placeholder text
-   `required` - Form validation

**Example in project**: Check `chat.html` for various attribute usage.

---

## CSS Basics

### CSS Selectors

CSS uses selectors to target HTML elements:

```css
/* Element selector */
body {
    background-color: #303030;
}

/* Class selector */
.welcome-header {
    margin: 90px 0px;
}

/* ID selector */
#login-form {
    display: flex;
}

/* Attribute selector */
input[type="submit"] {
    background-color: var(--yellow);
}

/* Pseudo-selector */
input:focus {
    border-color: var(--yellow);
}
```

**Example in project**: See `css/screens/login.css` for various selector types.

### CSS Properties

Essential CSS properties for styling:

#### Box Model

-   `width` / `height` - Element dimensions
-   `margin` - Space outside element
-   `padding` - Space inside element
-   `border` - Element border
-   `box-sizing` - How dimensions are calculated

#### Typography

-   `font-family` - Font type
-   `font-size` - Text size
-   `font-weight` - Text thickness
-   `color` - Text color
-   `text-align` - Text alignment

#### Background & Colors

-   `background-color` - Background color
-   `background-image` - Background image
-   `opacity` - Element transparency

**Example in project**: Check `css/variables.css` for color definitions and `css/screens/login.css` for typography.

### CSS Cascade & Specificity

CSS follows a cascade order:

1. Browser defaults
2. External stylesheets
3. Internal stylesheets
4. Inline styles

Specificity determines which rule applies:

-   Inline styles (1000)
-   IDs (100)
-   Classes (10)
-   Elements (1)

**Example in project**: See how `css/styles.css` imports other stylesheets in order.

---

## Layout & Positioning

### Flexbox

Flexbox is a powerful layout method for one-dimensional layouts:

```css
.container {
    display: flex;
    justify-content: space-between; /* Horizontal alignment */
    align-items: center; /* Vertical alignment */
    flex-direction: column; /* Direction of flex items */
}
```

**Example in project**: Check `css/components/nav-bar.css` for flexbox navigation layout.

### Positioning

CSS positioning controls element placement:

-   `static` - Default positioning
-   `relative` - Positioned relative to normal position
-   `absolute` - Positioned relative to nearest positioned ancestor
-   `fixed` - Positioned relative to viewport
-   `sticky` - Combination of relative and fixed

```css
.nav {
    position: fixed;
    bottom: 0;
    width: 100%;
}
```

**Example in project**: See `css/components/nav-bar.css` for fixed positioning.

### Display Properties

Control how elements are displayed:

-   `block` - Full width, new line
-   `inline` - Width of content, same line
-   `inline-block` - Width of content, respects width/height
-   `flex` - Flexbox container
-   `grid` - CSS Grid container
-   `none` - Hidden element

**Example in project**: Check `css/components/user-component.css` for display properties.

---

## Advanced CSS

### CSS Variables (Custom Properties)

Store reusable values:

```css
:root {
    --yellow: #fae100;
    --horizontal-space: 25px;
    --main-border: 1px solid rgba(255, 255, 255, 0.4);
    --dark-background: #303030;
    --dark-text: #ededed;
}

.element {
    background-color: var(--dark-background);
    color: var(--dark-text);
}
```

**Example in project**: See `css/variables.css` for variable definitions.

### Pseudo-selectors

Target elements based on state or position:

```css
/* Hover state */
.button:hover {
    background-color: #ccc;
}

/* Focus state */
input:focus {
    border-color: var(--yellow);
}

/* First child */
.nav__btn:first-child {
    margin-left: 0;
}

/* Nth child */
.nav__btn:nth-child(2) {
    animation-delay: 0.2s;
}
```

**Example in project**: Check `css/screens/login.css` for focus states and `css/components/nav-bar.css` for nth-child selectors.

### Transitions

Smooth property changes over time:

```css
.element {
    transition: property duration timing-function;
    transition: border-color 0.1s ease-in-out;
}
```

**Example in project**: See `css/screens/login.css` for input focus transitions.

### Animations

Keyframe-based animations:

```css
@keyframes notificationAnimation {
    0% {
        transform: none;
    }
    50% {
        transform: translateY(-3px) rotateY(180deg);
    }
    100% {
        transform: none;
    }
}

.element {
    animation: notificationAnimation 3s ease-in-out infinite;
}
```

**Example in project**: Check `css/components/nav-bar.css` for notification animations.

### Transform Properties

Modify element appearance:

-   `translate()` - Move element
-   `rotate()` - Rotate element
-   `scale()` - Resize element
-   `skew()` - Skew element

```css
.element {
    transform: translateY(80px) rotate(45deg) scale(1.2);
}
```

**Example in project**: See `css/components/nav-bar.css` for transform usage in animations.

---

## Responsive Design

### Mobile-First Approach

Design for mobile devices first, then enhance for larger screens:

```css
/* Mobile styles (default) */
.container {
    padding: 10px;
}

/* Tablet and up */
@media (min-width: 768px) {
    .container {
        padding: 20px;
    }
}

/* Desktop and up */
@media (min-width: 1024px) {
    .container {
        padding: 30px;
    }
}
```

### Viewport Meta Tag

Essential for mobile responsiveness:

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

### Media Queries

Apply styles based on device characteristics:

```css
/* Hide on large screens */
@media (min-width: 645px) {
    #no-mobile {
        display: none;
    }
}
```

**Example in project**: See `css/components/no-mobile.css` for responsive behavior.

---

## CSS Architecture

### BEM Methodology

Block-Element-Modifier naming convention:

```css
/* Block */
.nav {
}

/* Element */
.nav__list {
}
.nav__btn {
}
.nav__link {
}

/* Modifier */
.nav__btn--active {
}
.nav__notification--dot {
}
```

**Example in project**: Check `css/components/nav-bar.css` for BEM implementation.

### Component-Based CSS

Organize CSS by components and screens:

```
css/
├── components/     # Reusable UI components
│   ├── nav-bar.css
│   ├── status-bar.css
│   └── user-component.css
├── screens/        # Screen-specific styles
│   ├── login.css
│   ├── friends.css
│   └── chat.css
├── variables.css   # CSS custom properties
└── styles.css      # Main import file
```

**Example in project**: See the entire `css/` directory structure.

### CSS Reset

Normalize browser differences:

```css
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    padding: 0;
}
```

**Example in project**: Check `css/reset.css` for reset styles.

### Import Organization

Structure CSS imports logically:

```css
/* Reset and variables first */
@import "reset.css";
@import "variables.css";

/* Components */
@import "components/status-bar.css";
@import "components/nav-bar.css";

/* Screens */
@import "screens/login.css";
@import "screens/friends.css";
```

**Example in project**: See `css/styles.css` for import organization.
