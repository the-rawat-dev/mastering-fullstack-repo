# HTML Fundamentals - Complete Notes

## Web Pages Classification

### Static Pages
- **Definition**: Same content displayed to all users
- **File Extensions**: `.html`, `.htm`
- **Characteristics**: Fixed content, no user interaction changes

### Dynamic Pages
- **Definition**: Initially looks same but changes based on user interaction
- **File Extensions**: `.js`, `.php`, `.jsp`, `.asp`, `.aspx`
- **Examples**:
  - `www.inoxmovies.com/bookseat.aspx` (dynamic)
  - `www.irctc.co.in/` (initially static, becomes dynamic with interaction)

**Important Note**: HTML is used for both static and dynamic pages, contrary to common misconceptions.

## What is HTML?

**HTML (HyperText Markup Language)** is used for the structure of web pages.

### HyperText
- **"Hyper"** means "beyond"
- Specifies that text contains information beyond what you see
- Links and references to other content

### Markup Language
- **"Markup"** derived from "marking up" - preparing content for presentation
- A language used for presentation
- Designed to present content on browsers

## Evolution of HTML

### Timeline
1. **GML (Generic Markup Language)** - First markup language used on Internet
   - Developed by CERN Labs (Council for European Search and Nuclear Research)

2. **SGML (Standard Generalised Markup Language)** - Evolution from GML

3. **1990** - Tim Berners-Lee invented HTML

4. **HTML Versions 1.0 - 3.2** - Developed by IETF (Internet Engineering Task Force)

5. **2004** - HTML 4.0 and beyond developed jointly by:
   - **WHATWG** (Web Hypertext Application Technology Working Group)
   - **W3C** (World Wide Web Consortium)

6. **Current Version**: HTML5

## Browser Architecture

### Popular Browsers
- Chrome
- Edge
- Safari
- And others

**Key Point**: Every browser has different engines, resulting in different UI implementations.

### Browser Rendering Process

#### HTML Parsing Pipeline
```
Bytes → Characters → Tokens → Nodes → DOM
```

**Stage 1**: Convert binary data to characters

**Stage 2**: **Tokenization** - Convert characters into tokens
- Example: `<p>Hello</p>` becomes `<p>`, `Hello`, `</p>`

**Stage 3**: Convert tokens into **nodes/elements**

**Stage 4**: Create **DOM Tree** (Document Object Model)
- Hierarchical structure: `window → document → body → p`
- HTML is a collection of **elements**, not tags
- In browser inspect tab, you see elements, not tags

#### Complete Rendering Process
```
HTML Parsing → DOM Creation → Layout → Painting → Rendering → Display
```

### Critical Rendering Path
```
Network → HTML + CSS → JavaScript → DOM → Rendering → Layout → Painting → Display
```

**Memory Analysis**: Use browser inspect tab → Performance → Take snapshot to analyze memory usage.

## HTML Element Types

HTML elements are classified into 5 types:

### 1. Normal Elements
- **Characteristics**:
  - Returns presentation directly on callback
  - Does not stop presentation automatically
  - Does not require additional attributes
  - **Requires both start and end tags**

- **Example**:
  ```html
  Welcome to <b>HTML.</b> It is a markup language.
  ```

### 2. Void Elements
- **Characteristics**:
  - **"Void"** indicates no return type or value
  - Discards return value
  - **Requires additional attributes**
  - Returns and stops presentation implicitly
  - **Does not require end tag**
  - Also known as **"self-ending elements"**

- **Examples**:
  ```html
  <p>Welcome to HTML</p>
  <img src="image.jpg">
  <br>
  ```

- **Framework Considerations**:
  - In VS Code: `<br/>` (with slash to prevent warnings)
  - In browser: displays as `<br>` (no slash needed)
  - Some frameworks (like React) require end tags for void elements
  - **Technology dependent implementation**

### 3. RC Data Elements (Rich Content Data Elements)
- **Characteristics**:
  - Rich content data elements
  - **Will not allow any other element within the context**
  - Only for plain text content

- **Example**:
  ```html
  <textarea>Plain text only - no other HTML elements allowed here</textarea>
  ```

### 4. Raw Text Elements
- **Characteristics**:
  - Present content using raw text
  - No tags required within content

### 5. Foreign Elements
- Elements from other markup languages (like SVG, MathML)

## HTML Entities

Raw text representation using special characters:

- **Copyright Symbol**: `&copy;` → ©
- **Indian Rupee Symbol**: `&#8377;` → ₹
- **Usage Example**: `&#8377; 45,000.00 /-` → ₹ 45,000.00 /-

## Key Takeaways

1. **HTML Structure**: HTML defines the structure and presentation of web content
2. **DOM Understanding**: Learning HTML means learning how to present content in the DOM
3. **Element vs Tags**: HTML consists of elements, not tags (as seen in browser inspect)
4. **Browser Differences**: Different browsers have different engines and rendering behaviors
5. **Element Classification**: Understanding the 5 types of HTML elements is crucial for proper implementation
6. **Framework Considerations**: Some frameworks have specific requirements for element syntax

## Basic HTML Document Structure

```html
<!DOCTYPE html>
<html>
<head>
    <!-- Metadata, links to CSS, etc. -->
</head>
<body>
    <!-- Visible content -->
</body>
</html>
```

This structure represents the foundation of all HTML documents and follows the DOM hierarchy principles outlined above.