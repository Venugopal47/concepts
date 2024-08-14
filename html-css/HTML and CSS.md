# HTML and CSS 

## 1. Box Model

The **CSS Box Model** is a fundamental concept that describes the rectangular boxes generated for elements in the document tree. It consists of the following parts:

- **Content**: The actual content of the element.
- **Padding**: Clears an area around the content; it's inside the border.
- **Border**: A border that surrounds the padding (if any) and content.
- **Margin**: Clears an area outside the border; it's the outermost part.

## 2. Inline versus Block Elements

### Inline Elements
- Do not start on a new line.
- Only take up as much width as necessary.
- Examples: `<span>`, `<a>`, `<img>`.

### Block Elements
- Always start on a new line.
- Take up the full width available (100% of the parent container).
- Examples: `<div>`, `<p>`, `<h1>`, `<section>`.

## 3. Positioning: Relative/Absolute

### Relative Positioning
- Elements are positioned relative to their normal position.
- Use `top`, `right`, `bottom`, and `left` properties to adjust the position.

### Absolute Positioning
- Elements are positioned relative to their nearest positioned ancestor (anything other than `static`).
- If no such ancestor exists, it is positioned relative to the initial containing block (usually the viewport).

## 4. Common CSS Structural Classes

### Structural Classes:
- **`container`**: Centers content and gives it a maximum width.
- **`row`**: Used in grid systems to create horizontal groups of columns.
- **`col`**: Defines a column within a row.

## 5. Common CSS Styling Classes

- **`text-center`**: Centers text horizontally.
- **`bg-primary`**: Applies a primary background color.
- **`text-muted`**: Applies a muted (less prominent) text color.
- **`d-flex`**: Applies a flexbox layout to the element.

## 6. CSS Specificity

CSS specificity determines which CSS rule is applied when multiple rules could apply to the same element. It is calculated based on the types of selectors used:

- **Inline styles**: `style=""` (highest specificity).
- **IDs**: `#id`.
- **Classes, attributes, and pseudo-classes**: `.class`, `[attribute]`, `:hover`.
- **Elements and pseudo-elements**: `div`, `h1`, `:before`.

## 7. CSS Responsive Queries

Responsive design allows a webpage to adjust its layout based on the screen size or device. Media queries are used to apply different styles based on conditions such as screen width:

```css
@media (max-width: 600px) {
  .container {
    width: 100%;
  }
}
```
## 8. Flexbox/Grid

### Flexbox

Flexbox is a layout model that allows elements within a container to be automatically arranged in a flexible manner, accommodating different screen sizes.

```
.container {
  display: flex;
  justify-content: space-between;
}
```
### Grid
CSS Grid Layout is a 2D grid system that allows you to create complex layouts with rows and columns.

```
.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 10px;
}
```

## 9. Common Header Meta Tags
Meta tags provide metadata about the HTML document and are placed inside the <head> section:

- **`<meta charset="UTF-8">`** : Specifies the character encoding for the HTML document.
- **`<meta name="viewport" content="width=device-width, initial-scale=1.0">`** : Ensures proper scaling on mobile devices.
- **`<meta name="description" content="A brief description of the page">`** : Provides a summary of the page's content.

  
## 10. Different Types of Encoders
Encoders convert data from one format to another, typically for efficient storage or transmission:

-**Base64 Encoder**: Encodes binary data into a text string using 64 ASCII characters.
-**URL Encoder**   : Encodes special characters in URLs to ensure safe transmission.
-**HTML Encoder**  : Converts special HTML characters into their respective HTML entities (e.g., `<` becomes `&lt;`).
