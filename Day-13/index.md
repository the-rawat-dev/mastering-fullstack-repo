# Day 13: Advanced HTML Body Elements - Lists, Terms & Definitions

## Session Overview
This session covers advanced HTML body section elements including:
- Data lists with terms and definitions
- Details and summary elements
- Fieldset and legend elements
- Box shadows and text shadows
- Ordered and unordered lists
- Advanced styling techniques

---

## Table of Contents
1. [Data Lists - Terms & Definitions](#data-lists-terms-definitions)
2. [Details and Summary](#details-and-summary)
3. [Fieldset and Legend](#fieldset-and-legend)
4. [Box Shadow and Text Shadow](#box-shadow-and-text-shadow)
5. [Ordered Lists (OL)](#ordered-lists)
6. [Unordered Lists (UL)](#unordered-lists)
7. [Practical Examples](#practical-examples)

---

## Data Lists - Terms & Definitions

### What are Data Lists?

**Definition:**
> Data lists (`<dl>`) are used to present terms and their definitions in a structured format.

### Syntax Structure

```html
<dl>  <!-- Data List -->
  <dt>Term 1</dt>       <!-- Data Term -->
  <dd>Definition 1</dd>  <!-- Data Definition -->
  
  <dt>Term 2</dt>
  <dd>Definition 2</dd>
</dl>
```

### Elements Explained

| Element | Tag | Purpose |
|---------|-----|---------|
| **Data List** | `<dl>` | Container for terms and definitions |
| **Data Term** | `<dt>` | Defines the term/label |
| **Data Definition** | `<dd>` | Defines the description/definition |

---

### Basic Example

```html
<h2>Web Technologies</h2>
<dl>
  <dt>HTML</dt>
  <dd>It is a markup language</dd>
  
  <dt>CSS</dt>
  <dd>It defines styles for HTML</dd>
  
  <dt>JavaScript</dt>
  <dd>It handles client-side interactions</dd>
</dl>
```

**Default Appearance:**
```
HTML
  It is a markup language
CSS
  It defines styles for HTML
JavaScript
  It handles client-side interactions
```

**Note:** Definitions are indented by default (browser styling)

---

### Styling Data Lists

#### Basic Styling
```css
dt {
  font-weight: bold;
  background-color: gray;
  color: white;
  text-align: left;
}
```

#### Advanced Styling - Side by Side Layout
```css
dl {
  display: grid;
  grid-template-columns: 3fr 9fr;
  gap: 1rem;
}

dt {
  font-weight: bold;
  background-color: gray;
  color: white;
  padding: 0.5rem;
  margin-bottom: 20px;
}

dd {
  padding: 0.5rem;
  margin: 0;
  margin-bottom: 20px;
}
```

**Result:** Terms on left, definitions on right (like a table layout)

---

### Multiple Terms and Definitions

#### Multiple Definitions for One Term
```html
<dl>
  <dt>JavaScript</dt>
  <dd>A programming language</dd>
  <dd>Created in 1995</dd>
  <dd>Runs in browsers</dd>
</dl>
```

#### Multiple Terms for One Definition
```html
<dl>
  <dt>HTML</dt>
  <dt>HyperText Markup Language</dt>
  <dd>The standard markup language for web pages</dd>
  
  <dt>CSS</dt>
  <dt>Cascading Style Sheets</dt>
  <dd>Style sheet language for styling HTML</dd>
</dl>
```

**Key Points:**
- ✅ Can have multiple `<dd>` under one `<dt>`
- ✅ Can have multiple `<dt>` for one `<dd>`
- ✅ Can have only terms (no definitions)
- ✅ Can have only definitions (no terms)
- ✅ No strict order required

---

### Real-World Use Case: Product Specifications

```html
<h2>Product Details</h2>
<dl>
  <dt>Name</dt>
  <dd>Samsung TV</dd>
  
  <dt>Price</dt>
  <dd>$999</dd>
  
  <dt>Stock</dt>
  <dd>Available</dd>
</dl>
```

**Styled as Two-Column Layout:**
```css
dl {
  display: grid;
  grid-template-columns: 180px 1fr;
  gap: 1rem;
  padding: 1.5rem;
  background: #f9f9f9;
  border-radius: 8px;
}

dt {
  font-weight: 600;
  color: #555;
}

dd {
  margin: 0;
  color: #333;
}
```

---

### Advanced Technique: Sticky Headers

**Problem:** Long lists lose context while scrolling

**Solution:** Make terms sticky at the top

```html
<h2>Web Technologies</h2>
<dl>
  <dt>HTML Tutorial</dt>
  <dd>Void Elements</dd>
  <dd>Normal Elements</dd>
  <dd>RC Data Elements</dd>
  <dd>Foreign Elements</dd>
  <!-- Many more items -->
  
  <dt>CSS Tutorial</dt>
  <dd>Selectors</dd>
  <dd>Box Model</dd>
  <dd>Responsive Design</dd>
  <!-- Many more items -->
  
  <dt>JavaScript Tutorial</dt>
  <dd>Variables</dd>
  <dd>Data Types</dd>
  <dd>Operators</dd>
  <!-- Many more items -->
</dl>
```

**CSS for Sticky Headers:**
```css
dt {
  position: sticky;
  top: 0px;
  background-color: black;
  color: white;
  padding: 5px;
  font-weight: bold;
  z-index: 10;
}

dd {
  padding: 10px;
  margin-left: 20px;
}
```

**Behavior:**
- Terms scroll normally until reaching top
- At top (0px), they "stick"
- Next term pushes previous one up
- User always sees current category

**Real-World Example:**
Similar to toolbar on movie booking sites (e.g., INOX) that sticks to top while scrolling.

---

## Details and Summary

### What are Details and Summary?

**Definition:**
> `<details>` creates a collapsible/expandable content section. `<summary>` defines the visible title.

### Syntax Structure

```html
<details>
  <summary>Title Goes Here</summary>
  Content that can be hidden/shown goes here
</details>
```

---

### Basic Example

```html
<h2>Select Category</h2>

<details>
  <summary>Electronics</summary>
  <dl>
    <dd>Televisions</dd>
    <dd>Mobiles</dd>
    <dd>Watches</dd>
  </dl>
</details>

<details>
  <summary>Footwear</summary>
  <dl>
    <dd>Casuals</dd>
    <dd>Boots</dd>
    <dd>Sneakers</dd>
  </dl>
</details>
```

**Default Behavior:**
- All details are collapsed (hidden)
- Click arrow (▶) to expand
- Click again to collapse

---

### Open Attribute

**By default, details are hidden.** Use `open` attribute to show by default.

```html
<details open>
  <summary>Electronics</summary>
  <dl>
    <dd>Televisions</dd>
    <dd>Mobiles</dd>
    <dd>Watches</dd>
  </dl>
</details>

<details>
  <summary>Footwear</summary>
  <dl>
    <dd>Casuals</dd>
    <dd>Boots</dd>
    <dd>Sneakers</dd>
  </dl>
</details>
```

**Result:** Electronics category opens by default, Footwear is collapsed.

---

### Key Features

| Feature | Description |
|---------|-------------|
| **Toggle Display** | Show or hide content with click |
| **Default State** | Hidden by default |
| **Open Attribute** | `open` - displays content by default |
| **Arrow Icon** | Browser adds ▶ automatically |
| **No JavaScript Needed** | Pure HTML functionality |

---

### Browser Compatibility

⚠️ **Important:**
- ❌ Not supported in **old browsers** (IE, old Chrome/Firefox)
- ✅ Supported in **modern browsers** (Chrome 90+, Firefox 88+, Safari 14+)

**If not working:**
- Update your browser to latest version
- Old browsers show all content (no collapse/expand)

---

### Styling Details and Summary

```css
details {
  margin-bottom: 1rem;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 8px;
}

summary {
  font-weight: bold;
  cursor: pointer;
  padding: 0.5rem;
  background-color: #f0f0f0;
}

summary:hover {
  background-color: #e0e0e0;
}

details[open] summary {
  margin-bottom: 1rem;
}
```

---

## Fieldset and Legend

### What are Fieldset and Legend?

**Definition:**
> `<fieldset>` creates a frame/border around content. `<legend>` adds a caption to that frame.

### Syntax Structure

```html
<fieldset>
  <legend>Title</legend>
  Your content here
</fieldset>
```

---

### Basic Example

```html
<h2>Product Details</h2>

<fieldset>
  <legend>Basic Details</legend>
  <dl>
    <dt>Name</dt>
    <dd>Samsung TV</dd>
    
    <dt>Price</dt>
    <dd>$999</dd>
  </dl>
</fieldset>

<fieldset>
  <legend>Shipping Details</legend>
  <dl>
    <dt>Stock</dt>
    <dd>Available</dd>
    
    <dt>Shipped to</dt>
    <dd>Hyderabad</dd>
    
    <dt>Vendor</dt>
    <dd>Reliance Digital</dd>
  </dl>
</fieldset>
```

**Visual Result:**
```
┌─ Basic Details ──────────┐
│ Name:    Samsung TV      │
│ Price:   $999            │
└──────────────────────────┘

┌─ Shipping Details ───────┐
│ Stock:      Available    │
│ Shipped to: Hyderabad    │
│ Vendor:     Reliance     │
└──────────────────────────┘
```

---

### Styling Fieldset and Legend

```css
fieldset {
  margin-top: 30px;
  border: 1px solid #ccc;
  border-radius: 20px;
  padding: 20px;
}

legend {
  text-align: center;
  font-size: 17px;
  font-weight: bold;
  padding: 10px;
  border: 2px solid black;
  background-color: darkcyan;
  color: white;
  width: 200px;
}

/* Data list inside fieldset */
dl {
  display: grid;
  grid-template-columns: 3fr 9fr;
  gap: 1rem;
}

dt {
  font-weight: bold;
  margin-bottom: 20px;
}

dd {
  margin: 0;
  margin-bottom: 20px;
}
```

---

### Legend Positioning

**Default:** Legend appears at top-left of border

**Center Aligned:**
```css
legend {
  text-align: center;
}
```

**Left Aligned:**
```css
legend {
  text-align: left;
}
```

**Right Aligned:**
```css
legend {
  text-align: right;
}
```

---

## Box Shadow and Text Shadow

### Box Shadow (For Containers)

**Definition:**
> Adds shadow effect to containers (divs, paragraphs, fieldsets, etc.)

### Syntax

```css
box-shadow: horizontal vertical blur color;
```

**Components:**

| Value | Description | Example |
|-------|-------------|---------|
| **Horizontal** | Shadow left/right | `5px` (right), `-5px` (left) |
| **Vertical** | Shadow up/down | `3px` (down), `-3px` (up) |
| **Blur** | Blur amount | `5px` (blurred), `0px` (solid) |
| **Color** | Shadow color | `red`, `gray`, `rgba(0,0,0,0.5)` |

---

### Examples

#### Solid Shadow (No Blur)
```css
.box {
  box-shadow: 5px 5px 0px red;
}
```
**Result:** Solid red shadow, 5px right, 5px down

#### Blurred Shadow
```css
.box {
  box-shadow: 3px 3px 5px gray;
}
```
**Result:** Soft gray shadow, slightly blurred

#### Shadow on All Sides (No Offset)
```css
.box {
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.3);
}
```
**Result:** Uniform shadow all around (like a glow)

---

### Applying Box Shadow

**On Fieldset:**
```css
fieldset {
  box-shadow: 3px 3px 2px darkcyan;
}
```

**On Legend:**
```css
legend {
  box-shadow: 3px 2px 3px gray;
}
```

**On Any Container:**
```css
div, p, blockquote, dl {
  box-shadow: 2px 2px 5px rgba(0, 0, 0, 0.2);
}
```

---

### Text Shadow (For Text Content)

**Definition:**
> Adds shadow effect to text (headings, paragraphs, spans)

**Important:** 
- ❌ `box-shadow` does NOT work on text
- ✅ Use `text-shadow` for text

### Syntax

```css
text-shadow: horizontal vertical blur color;
```

**Same values as box-shadow!**

---

### Examples

#### Heading with Shadow
```html
<h1>PRODUCT CATALOG</h1>
```

```css
h1 {
  text-align: center;
  color: yellow;
  text-shadow: 2px 3px 2px black;
}
```

#### Multiple Text Shadows
```css
h1 {
  text-shadow: 
    2px 2px 0px red,
    4px 4px 0px blue,
    6px 6px 0px green;
}
```

---

### Box Shadow vs Text Shadow

| Feature | box-shadow | text-shadow |
|---------|------------|-------------|
| **Used For** | Containers (div, p, fieldset) | Text content (h1, p, span) |
| **Syntax** | Same | Same |
| **Values** | horizontal, vertical, blur, color | horizontal, vertical, blur, color |
| **Applied To** | Block elements | Text only |

**Remember:**
```css
/* ❌ WRONG - Box shadow on text doesn't work well */
h1 {
  box-shadow: 2px 2px 5px black; /* Won't show properly */
}

/* ✅ CORRECT - Use text-shadow for text */
h1 {
  text-shadow: 2px 2px 5px black;
}
```

---

### Complete Example with Shadows

```html
<h1>Product Catalog</h1>
<fieldset>
  <legend>Basic Details</legend>
  <dl>
    <dt>Name</dt>
    <dd>Samsung TV</dd>
    <dt>Price</dt>
    <dd>$999</dd>
  </dl>
</fieldset>
```

```css
h1 {
  text-align: center;
  color: #2c3e50;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
  border: 2px solid black;
  padding: 1rem;
}

fieldset {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 3px 3px 8px rgba(0,0,0,0.2);
}

legend {
  font-weight: bold;
  padding: 0.5rem 1rem;
  background: darkcyan;
  color: white;
  border: 2px solid black;
  border-radius: 4px;
  box-shadow: 2px 2px 4px gray;
}
```

---

## Ordered Lists

### What is an Ordered List?

**Definition:**
> Ordered lists (`<ol>`) display items with automatic numbering.

### Syntax

```html
<ol>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ol>
```

**Output:**
```
1. First item
2. Second item
3. Third item
```

---

### Basic Example

```html
<h2>Web Technologies</h2>
<ol>
  <li>HTML</li>
  <li>CSS</li>
  <li>Bootstrap</li>
  <li>JavaScript</li>
</ol>
```

**Features:**
- ✅ Auto-numbering (1, 2, 3, ...)
- ✅ Numbers update automatically when items added/removed
- ✅ Default numbering: 1, 2, 3, 4...

---

### Type Attribute (Numbering Styles)

**Syntax:**
```html
<ol type="value">
```

**Available Types:**

| Type Value | Numbering Style | Example |
|------------|----------------|---------|
| `1` | Numbers (default) | 1, 2, 3, 4, 5 |
| `A` | Uppercase letters | A, B, C, D, E |
| `a` | Lowercase letters | a, b, c, d, e |
| `I` | Uppercase Roman | I, II, III, IV, V |
| `i` | Lowercase Roman | i, ii, iii, iv, v |

---

### Examples with Different Types

#### Numbers (Default)
```html
<ol type="1">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** 1. HTML, 2. CSS, 3. JavaScript

#### Uppercase Letters
```html
<ol type="A">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** A. HTML, B. CSS, C. JavaScript

#### Lowercase Letters
```html
<ol type="a">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** a. HTML, b. CSS, c. JavaScript

#### Uppercase Roman
```html
<ol type="I">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** I. HTML, II. CSS, III. JavaScript

#### Lowercase Roman
```html
<ol type="i">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** i. HTML, ii. CSS, iii. JavaScript

---

### Important Note: After Z, What Comes?

**Common Question:** "After A-Z, what's the 27th number?"

**Answer:** AA, AB, AC... (Excel-style)

```
A, B, C ... X, Y, Z, AA, AB, AC ... AZ, BA, BB...
```

This is standard in computing (like Excel columns: A, B, C ... Z, AA, AB...)

**Not a complicated question** - it's common knowledge in computing!

---

### Start Attribute (Custom Starting Number)

**Syntax:**
```html
<ol start="number">
```

**Purpose:** Defines from which level/number to start

---

### Examples with Start Attribute

#### Start from 1 (Default)
```html
<ol start="1">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** 1, 2, 3

#### Start from 51
```html
<ol start="51">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** 51, 52, 53

#### Start from 101
```html
<ol start="101">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** 101, 102, 103

---

### Start with Letters (Important!)

**Rule:** Start attribute ALWAYS uses level numbers, not letters!

#### Correct Way
```html
<ol type="A" start="4">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ol>
```
**Output:** D, E, F (starts at 4th letter = D)

#### Wrong Way
```html
<!-- ❌ WRONG - Don't use start="D" -->
<ol type="A" start="D">
  <li>HTML</li>
  <li>CSS</li>
</ol>
```

**Why?**
- Start is always a **level number**
- Level 1 = A, Level 2 = B, Level 3 = C, Level 4 = D
- To start at D, use `start="4"`

---

### Reversed Attribute (Countdown Numbering)

**Syntax:**
```html
<ol reversed>
```

**Purpose:** Reverses the numbering (countdown style)

**Important:** 
- ❌ Does NOT reverse the data/items
- ✅ Only reverses the numbers

---

### Examples with Reversed

#### Without Start (Auto-calculates)
```html
<ol reversed>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>Bootstrap</li>
</ol>
```
**Output:** 4, 3, 2, 1

#### With Start Attribute
```html
<ol reversed start="2">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>Bootstrap</li>
</ol>
```
**Output:** 2, 1, 0, -1

**Explanation:**
- Starts at level 2
- Counts down: 2 → 1 → 0 → -1 → -2...

---

### Reversed with Letters

```html
<ol type="A" reversed>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>Bootstrap</li>
</ol>
```
**Output:** D, C, B, A

```html
<ol type="A" reversed start="2">
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>Bootstrap</li>
</ol>
```
**Output:** B, A, 0, -1

**Important Question:** "After A, what comes in reverse?"

**Answer:** Numbers (0, -1, -2...)

**Why?** There are no negative letters! (-A, -B don't exist)

So it automatically uses numbers for negative values.

---

### Use Cases for Reversed

**Recent-to-Old Display:**
```html
<h3>Recently Viewed Items</h3>
<ol reversed>
  <li>Samsung TV (today)</li>
  <li>iPhone 15 (yesterday)</li>
  <li>MacBook Pro (2 days ago)</li>
  <li>iPad Air (3 days ago)</li>
</ol>
```
**Output:** 4, 3, 2, 1 (most recent = highest number)

---

## Unordered Lists

### What is an Unordered List?

**Definition:**
> Unordered lists (`<ul>`) display items with bullets (bulleted style).

### Syntax

```html
<ul>
  <li>First item</li>
  <li>Second item</li>
  <li>Third item</li>
</ul>
```

**Output:**
```
• First item
• Second item
• Third item
```

---

### Basic Example

```html
<h2>Web Technologies</h2>
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

**Features:**
- ✅ Bullets (•) by default
- ✅ No automatic numbering
- ✅ Used for non-sequential items

---

### Unordered vs Ordered Lists

| Feature | Ordered List (`<ol>`) | Unordered List (`<ul>`) |
|---------|----------------------|------------------------|
| **Marker** | Numbers, letters, Roman | Bullets |
| **Use Case** | Sequential items, steps | Non-sequential items |
| **Auto-numbering** | Yes | No |
| **Example** | Recipes, instructions | Features, lists |

---

## Practical Examples

### Example 1: Tutorial Sections with Sticky Headers

```html
<!DOCTYPE html>
<html>
<head>
  <title>Web Technologies</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      padding: 2rem;
    }
    
    h2 {
      text-align: center;
      margin-bottom: 2rem;
    }
    
    dt {
      position: sticky;
      top: 0px;
      background-color: black;
      color: white;
      padding: 10px;
      font-weight: bold;
      margin-bottom: 10px;
      z-index: 10;
    }
    
    dd {
      padding: 10px 20px;
      border-bottom: 1px solid #eee;
    }
  </style>
</head>
<body>
  <h2>Web Technologies</h2>
  <dl>
    <dt>HTML Tutorial</dt>
    <dd>Void Elements</dd>
    <dd>Normal Elements</dd>
    <dd>RC Data Elements</dd>
    <dd>Foreign Elements</dd>
    <dd>Attributes</dd>
    <dd>Forms</dd>
    <dd>Tables</dd>
    <!-- Many more items -->
    
    <dt>CSS Tutorial</dt>
    <dd>Selectors</dd>
    <dd>Box Model</dd>
    <dd>Flexbox</dd>
    <dd>Grid</dd>
    <dd>Responsive Design</dd>
    <dd>Animations</dd>
    <!-- Many more items -->
    
    <dt>JavaScript Tutorial</dt>
    <dd>Variables</dd>
    <dd>Data Types</dd>
    <dd>Functions</dd>
    <dd>Arrays</dd>
    <dd>Objects</dd>
    <dd>Promises</dd>
    <!-- Many more items -->
  </dl>
</body>
</html>
```

---

### Example 2: E-commerce Product Details

```html
<!DOCTYPE html>
<html>
<head>
  <title>Product Details</title>
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      padding: 2rem;
      background: #f5f5f5;
    }
    
    .container {
      max-width: 800px;
      margin: 0 auto;
      background: white;
      padding: 2rem;
      border-radius: 12px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }
    
    h1 {
      text-align: center;
      color: #2c3e50;
      margin-bottom: 2rem;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
    }
    
    fieldset {
      margin-top: 30px;
      border: 2px solid #3498db;
      border-radius: 12px;
      padding: 1.5rem;
      box-shadow: 0 2px 8px rgba(52, 152, 219, 0.2);
    }
    
    legend {
      font-size: 18px;
      font-weight: bold;
      padding: 8px 20px;
      background: linear-gradient(135deg, #3498db, #2980b9);
      color: white;
      border: none;
      border-radius: 20px;
      box-shadow: 0 2px 4px rgba(0,0,0,0.2);
    }
    
    dl {
      display: grid;
      grid-template-columns: 150px 1fr;
      gap: 1rem;
    }
    
    dt {
      font-weight: 600;
      color: #555;
      padding: 0.5rem 0;
    }
    
    dd {
      margin: 0;
      padding: 0.5rem 0;
      color: #333;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Samsung 55" QLED TV</h1>
    
    <fieldset>
      <legend>Basic Details</legend>
      <dl>
        <dt>Brand</dt>
        <dd>Samsung</dd>
        
        <dt>Model</dt>
        <dd>QN55Q80A</dd>
        
        <dt>Price</dt>
        <dd>$999.99</dd>
        
        <dt>Screen Size</dt>
        <dd>55 inches</dd>
      </dl>
    </fieldset>
    
    <fieldset>
      <legend>Shipping Details</legend>
      <dl>
        <dt>Stock Status</dt>
        <dd>In Stock</dd>
        
        <dt>Delivery Time</dt>
        <dd>2-3 Business Days</dd>
        
        <dt>Shipping Cost</dt>
        <dd>Free Delivery</dd>
        
        <dt>Vendor</dt>
        <dd>Reliance Digital</dd>
      </dl>
    </fieldset>
    
    <fieldset>
      <legend>Technical Specifications</legend>
      <dl>
        <dt>Display Type</dt>
        <dd>QLED</dd>
        
        <dt>Resolution</dt>
        <dd>4K UHD (3840 x 2160)</dd>
        
        <dt>HDR</dt>
        <dd>HDR10+</dd>
        
        <dt>Smart TV</dt>
        <dd>Yes (Tizen OS)</dd>
        
        <dt>Warranty</dt>
        <dd>2 Years</dd>
      </dl>
    </fieldset>
  </div>
</body>
</html>
```

---

### Example 3: Collapsible FAQ

```html
<!DOCTYPE html>
<html>
<head>
  <title>FAQ Section</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 800px;
      margin: 2rem auto;
      padding: 0 1rem;
    }
    
    h1 {
      text-align: center;
      color: #2c3e50;
      margin-bottom: 2rem;
    }
    
    details {
      margin-bottom: 1rem;
      border: 1px solid #ddd;
      border-radius: 8px;
      padding: 1rem;
      background: white;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }
    
    summary {
      font-weight: bold;
      cursor: pointer;
      padding: 0.5rem;
      color: #3498db;
      font-size: 18px;
    }
    
    summary:hover {
      color: #2980b9;
    }
    
    details[open] {
      background: #f8f9fa;
    }
    
    details[open] summary {
      margin-bottom: 1rem;
      border-bottom: 2px solid #3498db;
      padding-bottom: 0.5rem;
    }
    
    dd {
      margin-left: 1.5rem;
      padding: 0.5rem 0;
    }
  </style>
</head>
<body>
  <h1>Frequently Asked Questions</h1>
  
  <details open>
    <summary>What is HTML?</summary>
    <p>HTML (HyperText Markup Language) is the standard markup language 
    for creating web pages. It describes the structure of web pages using markup.</p>
  </details>
  
  <details>
    <summary>What is CSS?</summary>
    <p>CSS (Cascading Style Sheets) is used to style and layout web pages. 
    It controls colors, fonts, spacing, and positioning of HTML elements.</p>
  </details>
  
  <details>
    <summary>What is JavaScript?</summary>
    <p>JavaScript is a programming language that enables interactive web pages. 
    It's used for client-side scripting to create dynamic content.</p>
  </details>
  
  <details>
    <summary>Do I need to learn all three?</summary>
    <p>Yes! For modern web development:
      <ul>
        <li>HTML - Structure</li>
        <li>CSS - Styling</li>
        <li>JavaScript - Interactivity</li>
      </ul>
    </p>
  </details>
</body>
</html>
```

---

### Example 4: Shopping Categories

```html
<!DOCTYPE html>
<html>
<head>
  <title>Shop by Category</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 600px;
      margin: 2rem auto;
      padding: 0 1rem;
      background: #ecf0f1;
    }
    
    h2 {
      text-align: center;
      color: #2c3e50;
    }
    
    details {
      margin-bottom: 1.5rem;
      background: white;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    }
    
    summary {
      padding: 1rem;
      font-weight: bold;
      font-size: 18px;
      cursor: pointer;
      background: linear-gradient(to right, #3498db, #2980b9);
      color: white;
      border-radius: 8px;
      user-select: none;
    }
    
    summary:hover {
      background: linear-gradient(to right, #2980b9, #21618c);
    }
    
    dl {
      padding: 1rem;
    }
    
    dd {
      padding: 0.5rem 1rem;
      margin: 0;
      border-left: 3px solid #3498db;
      margin-bottom: 0.5rem;
      cursor: pointer;
      transition: all 0.3s ease;
    }
    
    dd:hover {
      background: #f8f9fa;
      border-left-color: #e74c3c;
      padding-left: 1.5rem;
    }
  </style>
</head>
<body>
  <h2>Select Category</h2>
  
  <details open>
    <summary>Electronics</summary>
    <dl>
      <dd>Televisions</dd>
      <dd>Mobiles</dd>
      <dd>Watches</dd>
      <dd>Laptops</dd>
      <dd>Headphones</dd>
    </dl>
  </details>
  
  <details>
    <summary>Footwear</summary>
    <dl>
      <dd>Casuals</dd>
      <dd>Boots</dd>
      <dd>Sneakers</dd>
      <dd>Sandals</dd>
      <dd>Sports Shoes</dd>
    </dl>
  </details>
  
  <details>
    <summary>Fashion</summary>
    <dl>
      <dd>Men's Clothing</dd>
      <dd>Women's Clothing</dd>
      <dd>Accessories</dd>
      <dd>Jewelry</dd>
      <dd>Bags</dd>
    </dl>
  </details>
</body>
</html>
```

---

### Example 5: Recipe with Ordered Steps

```html
<!DOCTYPE html>
<html>
<head>
  <title>Recipe: Chocolate Cake</title>
  <style>
    body {
      font-family: 'Georgia', serif;
      max-width: 700px;
      margin: 2rem auto;
      padding: 0 1rem;
      background: #f9f6f0;
    }
    
    h1 {
      text-align: center;
      color: #6b4423;
      text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
    }
    
    fieldset {
      margin: 2rem 0;
      border: 2px solid #8b5a3c;
      border-radius: 12px;
      padding: 1.5rem;
      background: white;
    }
    
    legend {
      font-size: 20px;
      font-weight: bold;
      color: white;
      background: #6b4423;
      padding: 0.5rem 1.5rem;
      border-radius: 20px;
    }
    
    ul {
      list-style-type: circle;
      line-height: 2;
    }
    
    ol {
      line-height: 2;
    }
    
    li {
      margin-bottom: 0.5rem;
    }
  </style>
</head>
<body>
  <h1>🍰 Chocolate Cake Recipe</h1>
  
  <fieldset>
    <legend>Ingredients</legend>
    <ul>
      <li>2 cups all-purpose flour</li>
      <li>2 cups sugar</li>
      <li>3/4 cup cocoa powder</li>
      <li>2 teaspoons baking soda</li>
      <li>1 teaspoon salt</li>
      <li>2 eggs</li>
      <li>1 cup vegetable oil</li>
      <li>1 cup hot water</li>
      <li>1 cup buttermilk</li>
    </ul>
  </fieldset>
  
  <fieldset>
    <legend>Instructions</legend>
    <ol>
      <li>Preheat oven to 350°F (175°C)</li>
      <li>Grease and flour two 9-inch round cake pans</li>
      <li>Mix flour, sugar, cocoa, baking soda, and salt in large bowl</li>
      <li>Add eggs, oil, buttermilk, and vanilla</li>
      <li>Beat on medium speed for 2 minutes</li>
      <li>Stir in hot water (batter will be thin)</li>
      <li>Pour batter into prepared pans</li>
      <li>Bake 30-35 minutes until toothpick comes out clean</li>
      <li>Cool 10 minutes, then remove from pans</li>
      <li>Cool completely before frosting</li>
    </ol>
  </fieldset>
  
  <fieldset>
    <legend>Tips</legend>
    <ul>
      <li>Use room temperature ingredients</li>
      <li>Don't overmix the batter</li>
      <li>Test with toothpick for doneness</li>
      <li>Let cake cool completely before frosting</li>
    </ul>
  </fieldset>
</body>
</html>
```

---

## Nested Lists (Preview)

**Note:** Detailed nested lists will be covered in next session.

### Basic Nested Structure

```html
<ol>
  <li>HTML
    <ol type="a">
      <li>Elements</li>
      <li>Attributes</li>
      <li>Forms</li>
    </ol>
  </li>
  <li>CSS
    <ol type="a">
      <li>Selectors</li>
      <li>Box Model</li>
      <li>Flexbox</li>
    </ol>
  </li>
</ol>
```

**Output:**
```
1. HTML
   a. Elements
   b. Attributes
   c. Forms
2. CSS
   a. Selectors
   b. Box Model
   c. Flexbox
```

---

## Summary Table

### Elements Learned Today

| Element | Tag | Purpose | Key Attributes |
|---------|-----|---------|---------------|
| **Data List** | `<dl>` | Container for terms/definitions | - |
| **Data Term** | `<dt>` | Term/label | - |
| **Data Definition** | `<dd>` | Definition/description | - |
| **Details** | `<details>` | Collapsible content | `open` |
| **Summary** | `<summary>` | Title for details | - |
| **Fieldset** | `<fieldset>` | Frame around content | - |
| **Legend** | `<legend>` | Caption for fieldset | - |
| **Ordered List** | `<ol>` | Numbered list | `type`, `start`, `reversed` |
| **Unordered List** | `<ul>` | Bulleted list | `type` |
| **List Item** | `<li>` | Item in list | - |

---

### CSS Properties Learned

| Property | Purpose | Values | Example |
|----------|---------|--------|---------|
| `box-shadow` | Shadow for containers | horizontal, vertical, blur, color | `3px 3px 5px gray` |
| `text-shadow` | Shadow for text | horizontal, vertical, blur, color | `2px 2px 4px black` |
| `position: sticky` | Sticky positioning | `top`, `bottom`, `left`, `right` | `top: 0px` |
| `display: grid` | Grid layout | - | `grid-template-columns` |
| `grid-template-columns` | Column widths | fractions, pixels | `3fr 9fr` |

---

## Key Concepts to Remember

### 1. Data Lists Best Practices

✅ **Use when:**
- Displaying terms with definitions
- Product specifications
- Glossaries
- Key-value pairs

❌ **Don't use when:**
- Simple lists (use `<ul>` or `<ol>`)
- Navigation menus
- Table-like data (use `<table>`)

---

### 2. Details/Summary Browser Support

⚠️ **Important:**
- Works in all modern browsers
- Not supported in Internet Explorer
- Not supported in old Chrome/Firefox versions
- **Solution:** Update to latest browser

**Check support:** https://caniuse.com/details

---

### 3. Shadow Syntax Confusion

**Remember:**
```css
/* Container shadow */
div {
  box-shadow: 3px 3px 5px gray;
}

/* Text shadow */
h1 {
  text-shadow: 2px 2px 4px black;
}
```

**Common mistake:**
```css
/* ❌ WRONG - box-shadow on text */
h1 {
  box-shadow: 2px 2px 4px black; /* Won't work properly */
}
```

---

### 4. Ordered List Numbering

**Key Points:**
- `type`: Changes numbering style (1, A, a, I, i)
- `start`: Changes starting number (always a number!)
- `reversed`: Reverses numbering (not data)

**Common mistakes:**
```html
<!-- ❌ WRONG -->
<ol type="A" start="D">

<!-- ✅ CORRECT -->
<ol type="A" start="4">  <!-- D is 4th letter -->
```

---

### 5. After Z, What Comes?

**Answer:** AA, AB, AC... (like Excel)

**Sequence:**
```
A, B, C ... X, Y, Z, AA, AB, AC ... AZ, BA, BB ... ZZ, AAA...
```

This is **standard computing convention** - not a complex question!

---

### 6. Reversed Negative Numbers

**Question:** "In reversed alphabets, after A what comes?"

**Answer:** 0, -1, -2...

**Why?** No negative letters exist (-A, -B don't exist in computing)

```html
<ol type="A" reversed start="2">
  <li>Item 1</li>  <!-- B -->
  <li>Item 2</li>  <!-- A -->
  <li>Item 3</li>  <!-- 0 -->
  <li>Item 4</li>  <!-- -1 -->
</ol>
```

---

## Common Mistakes & Solutions

### Mistake 1: Box Shadow on Text

**Problem:**
```css
h1 {
  box-shadow: 2px 2px 5px black; /* Doesn't work well */
}
```

**Solution:**
```css
h1 {
  text-shadow: 2px 2px 5px black; /* Correct */
}
```

---

### Mistake 2: Wrong Start Value for Letters

**Problem:**
```html
<ol type="A" start="E">  <!-- ❌ Wrong -->
```

**Solution:**
```html
<ol type="A" start="5">  <!-- ✅ Correct (E is 5th) -->
```

---

### Mistake 3: Not Using Sticky Positioning Correctly

**Problem:**
```css
dt {
  position: sticky;
  /* Missing top value! */
}
```

**Solution:**
```css
dt {
  position: sticky;
  top: 0px;  /* Required! */
}
```

---

### Mistake 4: Details Not Working

**Problem:** Details/summary not showing expand/collapse arrows

**Solution:**
- Update browser to latest version
- Check browser compatibility
- Ensure correct HTML structure

---

### Mistake 5: Grid Template Columns Not Working

**Problem:**
```css
dl {
  display: grid;
  /* Missing grid-template-columns! */
}
```

**Solution:**
```css
dl {
  display: grid;
  grid-template-columns: 3fr 9fr;
}
```

---

## Practice Exercises

### Exercise 1: Product Specifications
Create a product details page with:
- Fieldsets for different sections
- Data lists for specifications
- Box shadows on fieldsets
- Styled legends

### Exercise 2: FAQ Section
Create a FAQ page with:
- Details/summary for questions
- First question open by default
- Styled summary elements
- Hover effects

### Exercise 3: Tutorial Index
Create a tutorial page with:
- Sticky data terms
- Multiple topics per term
- Scrollable content
- Professional styling

### Exercise 4: Recipe Page
Create a recipe with:
- Ordered list for instructions
- Unordered list for ingredients
- Fieldsets for sections
- Attractive styling

### Exercise 5: Course Outline
Create a course outline with:
- Ordered list with Roman numerals
- Start numbering from specific point
- Reversed numbering for countdown
- Different numbering types

---

## Quick Reference

### Data List Template
```html
<dl>
  <dt>Term</dt>
  <dd>Definition</dd>
</dl>
```

### Details/Summary Template
```html
<details open>
  <summary>Title</summary>
  Content here
</details>
```

### Fieldset/Legend Template
```html
<fieldset>
  <legend>Title</legend>
  Content here
</fieldset>
```

### Ordered List Template
```html
<ol type="1" start="1">
  <li>Item</li>
</ol>
```

### Shadow Template
```css
/* Box shadow */
element {
  box-shadow: 3px 3px 5px gray;
}

/* Text shadow */
text {
  text-shadow: 2px 2px 4px black;
}
```

### Sticky Positioning Template
```css
element {
  position: sticky;
  top: 0px;
  z-index: 10;
}
```

---

## Next Session Preview

### Topics to be Covered:
1. **Nested Lists**
   - Lists inside lists
   - Multi-level numbering
   - Complex hierarchies

2. **Font Effects**
   - Bold, italic, underline
   - Strikethrough, subscript, superscript
   - Font families and sizes

3. **Text Formatting**
   - Text alignment
   - Text decoration
   - Letter and word spacing

4. **More Styling**
   - Colors and backgrounds
   - Borders and outlines
   - Advanced effects

---

## Important Notes

### Browser Compatibility
- ✅ Data lists: All browsers
- ✅ Fieldset/legend: All browsers
- ⚠️ Details/summary: Modern browsers only (not IE)
- ✅ Ordered/unordered lists: All browsers
- ✅ Box/text shadows: Modern browsers (IE9+)
- ✅ Sticky positioning: Modern browsers (not IE)

### Performance Tips
- Use shadows sparingly (affects rendering)
- Sticky positioning is better than fixed positioning
- Grid layout is performant for large lists

### Accessibility
- Use semantic HTML (dl, dt, dd)
- Ensure proper heading hierarchy
- Add ARIA labels where needed
- Test keyboard navigation

---

## Homework

### Task 1: Product Page
Create a complete product details page with:
- Multiple fieldsets
- Data lists for specs
- Shadows for depth
- Professional styling

### Task 2: Learning Portal
Create a learning portal with:
- Sticky course headers
- Collapsible sections
- Ordered topics
- Clean layout

### Task 3: FAQ Section
Build an FAQ with:
- 5+ questions
- Details/summary
- First question open
- Styled and responsive

### Task 4: Recipe Collection
Create 2-3 recipes with:
- Ordered instructions
- Unordered ingredients
- Fieldsets for sections
- Print-friendly styling

---

## Additional Resources

### Documentation
- MDN: Definition Lists - https://developer.mozilla.org/en-US/docs/Web/HTML/Element/dl
- MDN: Details Element - https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details
- MDN: Fieldset - https://developer.mozilla.org/en-US/docs/Web/HTML/Element/fieldset

### Tools
- Can I Use: Check browser support - https://caniuse.com/
- CSS Grid Generator - https://cssgrid-generator.netlify.app/
- Box Shadow Generator - https://cssgenerator.org/box-shadow-css-generator.html

---

## Summary

Today you learned:
- ✅ Data lists (dl, dt, dd) for terms and definitions
- ✅ Details and summary for collapsible content
- ✅ Fieldset and legend for grouped content
- ✅ Box shadows for containers
- ✅ Text shadows for typography
- ✅ Ordered lists with different numbering styles
- ✅ Start and reversed attributes
- ✅ Sticky positioning for scrollable content
- ✅ Grid layout for side-by-side terms

**Key Takeaway:** Professional websites use these elements to create organized, accessible, and visually appealing content structures!

