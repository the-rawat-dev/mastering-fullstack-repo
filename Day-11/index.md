# HTML5 Semantic Elements and CSS Layout Design

## Session Overview
This session covers working with HTML5 semantic elements and basic CSS styling to create website layouts.

---

## HTML5 Semantic Elements Review

### Why HTML5 Semantic Elements?
- Older HTML versions used tables for layout design
- Tables had issues with data presentation and were not SEO-friendly
- HTML5 introduced semantic elements for better structure and SEO optimization

### Key Semantic Elements

#### 1. **`<aside>`**
- Contains information not directly related to main website content
- Typically used for advertisements

#### 2. **`<article>`**
- Publishes highlights and updates about the website
- Contains important content updates

#### 3. **`<dialog>`**
- Used for optional user interactions
- Creates pop-ups that users can open/close
- Requires `open` attribute to display by default
- Advanced positioning requires JavaScript

#### 4. **`<figure>` and `<figcaption>`**
- Used to display pictures with captions
- Makes images search engine friendly
- Helps search engines identify pictures based on captions

#### 5. **`<header>`**
- Displays content in the top margin of the page

#### 6. **`<footer>`**
- Displays content in the bottom margin of the page

#### 7. **`<section>`**
- Contains main content between header and footer
- Holds the primary information of the website

#### 8. **`<nav>`**
- Used for navigation bar
- Contains navigation menu items

#### 9. **`<menu>`**
- Contains items inside navigation bar
- **Note:** Recent HTML versions have deprecated `<menu>` tag
- Modern websites use `<ul>` or `<ol>` directly in `<nav>`

#### 10. **`<main>`**
- Contains the main content area of the website

#### 11. **`<div>`**
- Used for block-level content
- Content appears one below another

#### 12. **`<span>`**
- Used for inline content
- Content appears side by side

---

## CSS Basics for Layout Design

### Embedding CSS Styles

**Embedded Technique:**
```html
<head>
  <style>
    /* CSS rules here */
  </style>
</head>
```

- Styles written in the same page
- Available only for that specific page
- For multiple pages, use external stylesheets (covered later)

### CSS Syntax Structure

```css
element-name {
  attribute: value;
  attribute: value;
}
```

**Example:**
```css
header {
  background-color: tomato;
  color: white;
  padding: 20px;
  font-size: 25px;
  text-align: center;
}
```

---

## Important CSS Properties

### 1. **Color Properties**

#### Background Color
```css
background-color: tomato;
background-color: black;
```

#### Text Color
```css
color: white;
color: #ff6347; /* Hexadecimal code */
```

### 2. **Padding**
- Space around content inside the container
- Distance between content and container border

```css
padding: 20px;
padding: 10px;
padding: 5px;
```

**Visual Understanding:**
- Container has a border
- Text inside container
- Padding = space around the text (inside border)

### 3. **Margin**
- Space around the container
- Distance between page and container

**Types:**
```css
margin-top: 20px;
margin-bottom: 20px;
margin-left: 200px;
margin-right: 20px;
```

**Visual Understanding:**
- Page contains container
- Margin = space between page edge and container
- Can set margins for all four sides

### 4. **Font Properties**

#### Font Size
```css
font-size: 20px;
font-size: 40px;
```

#### Font Weight
```css
font-weight: bold;
```

#### Font Style
```css
font-style: italic;
```

#### Font Family
```css
font-family: Arial;
font-family: "Times New Roman";
```

### 5. **Text Alignment**
```css
text-align: left;
text-align: center;
text-align: right;
text-align: justify; /* Reduces raggedness of right edge */
```

### 6. **Dimensions**

#### Width
```css
width: 200px;
width: 100px;
```

#### Height
```css
height: 400px;
height: 450px;
```

**Standard Page Dimensions:**
- Width: 1200 pixels
- Height: 700-720 pixels

### 7. **Border Properties**

#### Basic Border
```css
border: 2px solid black;
border: 2px dotted tomato;
border: 2px dashed red;
```

**Border Styles:**
- `solid` - Solid line
- `dotted` - Dotted line
- `dashed` - Dashed line
- `double` - Double line
- `groove` - 3D grooved border

#### Border Radius (Curved Corners)
```css
border-radius: 10px;
border-radius: 5px;
```

---

## Creating Multi-Column Layouts

### Using CSS Grid

#### Step 1: Set Display to Grid
```css
section {
  display: grid;
}
```

#### Step 2: Define Grid Template Columns
```css
section {
  display: grid;
  grid-template-columns: 200px 800px 200px;
}
```

**Using Fractions (Recommended):**
```css
section {
  display: grid;
  grid-template-columns: 2fr 8fr 2fr;
}
```

**Why Fractions are Better:**
- Pixels are fixed and don't adapt to different screen sizes
- Fractions adjust according to device width
- Mobile devices typically support max 500px width
- Using pixels (e.g., 800px) on mobile causes layout issues
- Fractions automatically fit content to device screen

**Maximum Columns:**
- Can divide into maximum 12 columns
- Total fractions should not exceed 12

**Examples:**
```css
/* 3 columns */
grid-template-columns: 2fr 8fr 2fr;

/* 5 columns */
grid-template-columns: 2.5fr 2.5fr 3fr 2.5fr 2.5fr;
```

---

## CSS Selectors

### 1. Element Selector
```css
header {
  /* styles */
}
```

### 2. Multiple Elements (Comma)
```css
header, footer {
  /* same styles for both */
}
```

### 3. Descendant Selector (Space)
```css
nav div {
  /* styles for div inside nav only */
}
```

### 4. ID Selector (Hash)
```css
#title {
  font-weight: bold;
}

#topic {
  font-size: 12px;
  color: lightyellow;
}
```

**In HTML:**
```html
<div id="title">Books</div>
<div id="topic">Art and Collection</div>
```

---

## Practical Layout Example

### Basic Page Structure

```html
<!DOCTYPE html>
<html>
<head>
  <title>Layout</title>
  <style>
    /* CSS styles here */
  </style>
</head>
<body>
  <header>
    <div>Amazon Shopping</div>
  </header>
  
  <section>
    <nav>
      <div>Home</div>
      <div>Electronics</div>
      <div>Footwear</div>
      <div>Fashion</div>
    </nav>
    
    <main>
      <div>Welcome to Online Shopping Store</div>
      <div>Special Offers</div>
      <article>70% off on Electronics</article>
      <figure>
        <img src="tv.jpg" alt="TV">
        <figcaption>Samsung TV</figcaption>
      </figure>
      <dialog open>Any Help?</dialog>
    </main>
    
    <aside>
      <article>Ads Here</article>
    </aside>
  </section>
  
  <footer>
    <div>&copy; Copyright 2021</div>
  </footer>
</body>
</html>
```

### Complete CSS Styling

```css
/* Header Styling */
header {
  background-color: tomato;
  color: white;
  padding: 20px;
  font-size: 25px;
  text-align: center;
  border: 2px solid black;
}

/* Footer Styling */
footer {
  background-color: black;
  color: white;
  text-align: center;
  font-size: 20px;
  padding: 5px;
  border: 2px solid black;
}

/* Section Layout */
section {
  height: 450px;
  margin-top: 20px;
  display: grid;
  grid-template-columns: 2fr 8fr 2fr;
}

/* Navigation Styling */
nav div {
  border: 2px solid black;
  width: 120px;
  margin-bottom: 20px;
  padding: 10px;
  font-size: 20px;
  background-color: tomato;
  color: white;
  border-radius: 10px;
}

/* Main Content Styling */
main div {
  font-size: 40px;
  text-align: center;
}

/* Article Styling */
article {
  width: 200px;
  background-color: darkcyan;
  color: white;
  padding: 5px;
  font-size: 25px;
  text-align: center;
  margin-left: 300px;
}

/* Figure Styling */
figure {
  height: 100px;
  width: 200px;
  border: 2px double black;
}

/* Aside (Advertisement) Styling */
aside {
  width: 100px;
  height: 50px;
  border: 2px dotted black;
  text-align: center;
}

/* Dialog Styling */
dialog {
  position: absolute;
  right: 0px;
}
```

---

## Special HTML Entities

### Copyright Symbol
```html
&copy;
<!-- Displays: © -->
```

---

## Important Notes and Best Practices

### 1. **Dialog Element**
- Must include `open` attribute to display by default
- Without `open`, dialog remains hidden
- Advanced positioning requires JavaScript knowledge

### 2. **Menu Element Deprecation**
- Recent HTML5 versions deprecated `<menu>` tag
- Modern websites use `<ul>` (unordered list) or `<ol>` (ordered list) directly in `<nav>`
- Using `<menu>` adds unnecessary left indentation

### 3. **Responsive Design**
- Always use fractions (fr) instead of pixels for grid columns
- Ensures layout adapts to different screen sizes
- Critical for mobile responsiveness

### 4. **Standard Page Dimensions**
- Width: 1200 pixels
- Height: 700-720 pixels
- Keep these standards when designing layouts

### 5. **CSS Learning Approach**
- Focus only on concepts covered in current session
- Don't get overwhelmed by additional CSS features
- Complete CSS will be covered in dedicated CSS course
- Practice given examples thoroughly before moving forward

### 6. **Style Organization**
- No specific order required for CSS properties within a rule
- Can write properties in any sequence
- Keep styles within `<style>` tags in `<head>` section

---

## Practice Exercise - Amazon Footer Layout

### HTML Structure
```html
<footer>
  <div id="title">AbeBooks</div>
  <div id="topic">Books, Art and Collection</div>
  
  <div id="title">Amazon Web Services</div>
  <div id="topic">Scalable Cloud Computing Services</div>
  
  <div id="title">Audible</div>
  <div id="topic">Download Audio Books</div>
  
  <div id="title">DPReview</div>
  <div id="topic">Digital Photography</div>
  
  <div id="title">IMDb</div>
  <div id="topic">Movies, TV and Celebrities</div>
</footer>
```

### CSS Styling
```css
footer {
  height: 300px;
  background-color: black;
  color: white;
  font-size: 20px;
  padding: 20px;
  display: grid;
  grid-template-columns: 2.5fr 3fr 2.5fr 2.5fr 2.5fr;
}

#title {
  font-weight: bold;
  font-family: Arial;
  font-size: 18px;
}

#topic {
  font-size: 12px;
  color: lightyellow;
}
```

---

## Key Takeaways

1. HTML5 semantic elements improve SEO and code readability
2. CSS Grid is powerful for creating multi-column layouts
3. Use fractions instead of pixels for responsive design
4. Padding is space inside container, margin is space outside
5. Practice embedded CSS before learning external stylesheets
6. Focus on current lesson concepts before exploring advanced features
7. Standard page dimensions: 1200px width × 700px height

---

## Next Session Preview

- More body section attributes
- Handling paragraphs and headings
- Working with real website layouts
- Practice exercises for layout design
- Advanced styling techniques

---

## Assignment

1. Practice the layout example created in class
2. Review all semantic elements and their usage
3. Experiment with different color combinations
4. Try creating variations of the grid layout
5. Practice Amazon footer example
6. Be prepared for design exercises in next session

---
