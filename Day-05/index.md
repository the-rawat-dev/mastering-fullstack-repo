# Day 5: Creating Web Applications - Setup & Project Structure

## Session Overview
This session covers:
- Creating a new web application from scratch
- Understanding project structure and standards
- Setting up development environment
- Understanding static vs dynamic concepts
- Learning about web pages and their types

---

## Table of Contents
1. [Prerequisites Recap](#prerequisites-recap)
2. [Creating a New Web Application](#creating-a-new-web-application)
3. [Project Structure Standards](#project-structure-standards)
4. [Understanding package.json](#understanding-packagejson)
5. [Web Pages Explained](#web-pages-explained)
6. [Static vs Dynamic Memory](#static-vs-dynamic-memory)
7. [Static vs Dynamic Pages](#static-vs-dynamic-pages)
8. [Practice Exercises](#practice-exercises)

---

## Prerequisites Recap

### Software Requirements (Already Installed)

1. **Node.js** - JavaScript runtime environment
2. **Visual Studio Code** - Code editor
3. **VS Code Extensions:**
   - ✅ Live Server
   - ✅ VS Code Icons
   - ✅ IntelliSense for CSS class names
   - ✅ Code snippets (optional)

---

## Creating a New Web Application

### Step 1: Create Project Folder

**Important Rules:**
- ❌ Don't create on Desktop (permission issues with libraries)
- ✅ Create in C:, D:, or other drives
- ❌ Avoid spaces in folder names
- ✅ Use hyphens or continuous names

**Example Folder Names:**
```
✅ full-stack-web-application
✅ web-development
✅ MyProject
❌ Full Stack Web Application (spaces cause issues)
❌ my new project (spaces)
```

**Steps:**
1. Open File Explorer
2. Navigate to C: or D: drive
3. Create New Folder
4. Name it: `full-stack-web-application`

---

### Step 2: Open Project in VS Code

**Method 1: Direct from Home Screen**
1. Open Visual Studio Code
2. Click "Open Folder" button on home screen
3. Select your project folder

**Method 2: From File Menu**
1. Open Visual Studio Code
2. Go to **File** → **Open Folder**
3. Navigate to: `C:\full-stack-web-application`
4. Click "Select Folder"

**Result:** Empty folder opens in VS Code (left sidebar shows folder name)

---

### Step 3: Open Terminal

**Why Terminal?**
- Provides command prompt inside VS Code
- Run commands specific to the project
- No need to switch between applications
- Keeps everything unified

**Method 1: Keyboard Shortcut**
```
Ctrl + ` (backtick)
```
**Note:** Backtick (`) is on the same key as tilde (~)

**Method 2: Menu**
1. Go to **Terminal** menu (top)
2. Select **New Terminal**

---

### Step 4: Switch from PowerShell to CMD (CRITICAL!)

**Problem:** Terminal may open with PowerShell (shows `PS` prefix)

**Why Avoid PowerShell?**
- Incomplete installation on some PCs
- Commands may not execute properly
- Compatibility issues with npm commands

**Visual Indicators:**
```powershell
# ❌ PowerShell (Don't use)
PS C:\full-stack-web-application>

# ✅ Command Prompt (Use this)
C:\full-stack-web-application>
```

**How to Switch:**
1. Look at terminal (bottom of VS Code)
2. Find dropdown on right side (shows current shell type)
3. Click dropdown arrow
4. Select **Command Prompt**

---

### Step 5: Initialize Project with npm

**Command:**
```bash
npm init -y
```

**Breaking Down the Command:**

| Part | Meaning | Purpose |
|------|---------|---------|
| `npm` | Node Package Manager | Tool for managing JavaScript packages |
| `init` | Initialize | Creates a new project |
| `-y` | Yes flag | Accepts all default prompts automatically |

**What Happens:**
- Creates `package.json` file
- Configures project as Node.js application
- Makes folder an "official" web application

---

### Without `-y` Flag (What Gets Asked):

If you run `npm init` without `-y`:

```bash
npm init

# Terminal asks:
package name: (full-stack-web-application) 
version: (1.0.0)
description: 
entry point: (index.js)
test command:
git repository:
keywords:
author:
license: (ISC)
```

**Why Use `-y`?**
- Beginners don't know proper version numbering
- Avoids complex questions about metadata
- Can modify `package.json` later if needed
- Faster setup

**To Cancel Questions:** Press `Ctrl + C`

---

## Understanding package.json

### What is package.json?

**Definition:**
- File containing project metadata
- Configuration file for Node.js projects
- Records project dependencies and settings

### What It Contains

```json
{
  "name": "full-stack-web-application",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

### Key Components

#### 1. **Project Name**
```json
"name": "full-stack-web-application"
```
- Identifies your project
- Should be lowercase
- Use hyphens, not spaces

#### 2. **Version**
```json
"version": "1.0.0"
```
- Semantic versioning: `MAJOR.MINOR.PATCH`
- `1.0.0` = First stable release
- More on versioning in advanced lessons

#### 3. **Description**
```json
"description": "Full stack web development project"
```
- Brief description of your project
- Helps others understand project purpose

#### 4. **Author**
```json
"author": "Your Name"
```
- Your name or organization

#### 5. **License**
```json
"license": "MIT"
```
- Specifies how others can use your code
- Common: MIT, ISC, Apache 2.0

#### 6. **Dependencies** (Added Later)
```json
"dependencies": {
  "react": "^18.2.0",
  "express": "^4.18.2"
}
```
- Lists external libraries your project uses
- Includes version numbers

---

### Why package.json is Critical

**Scenario:** You download someone's project from GitHub

**Problem:**
- Project uses libraries not on your PC
- Don't know which libraries needed
- Don't know which versions required

**Solution:**
- Open `package.json`
- See all dependencies listed
- Run `npm install` to download everything

**Example:**
```json
{
  "dependencies": {
    "react": "^18.2.0",
    "express": "^4.18.2",
    "mongodb": "^5.1.0"
  }
}
```

You know you need: React, Express, MongoDB with specific versions!

---

### JSON Format Explained

**JSON = JavaScript Object Notation**

**Purpose:** Format for representing data

**Structure:**
```json
{
  "key": "value",
  "anotherKey": "anotherValue"
}
```

**Characteristics:**
- Uses curly braces `{}`
- Key-value pairs
- Comma-separated
- Keys in double quotes
- Values can be: strings, numbers, arrays, objects

**Example:**
```json
{
  "name": "John Doe",
  "age": 25,
  "skills": ["HTML", "CSS", "JavaScript"],
  "address": {
    "city": "New York",
    "country": "USA"
  }
}
```

---

### Editing package.json

You can manually edit:

```json
{
  "name": "my-awesome-project",
  "version": "1.0.0",
  "description": "Learning web development",
  "author": "Your Name",
  "license": "MIT"
}
```

**Save:** `Ctrl + S`

**Note:** File auto-updates when you install packages

---

## Project Structure Standards

### Why Follow Standards?

**Real-World Example:**
- Amazon uses specific colors for "Great Indian Festival"
- Orange/Yellow = Sunset/Sunrise colors
- Indicates limited-time offers (like sunset - few minutes)
- Not random choice - follows design psychology standards

**Key Point:**
> Professional developers follow industry standards, not personal preferences. Every color, font, and structure has a reason.

### Standard Folder Structure

Every professional project contains:

#### 1. **public/** Folder
```
public/
  ├── index.html
  ├── images/
  ├── docs/
  └── other static files
```

**Purpose:**
- Contains static resources
- Files that don't change dynamically

**Static Resources:**
- HTML files
- Images (.jpg, .png, .svg)
- PDF documents
- Text files
- Videos
- Fonts

#### 2. **src/** Folder
```
src/
  ├── styles.css
  ├── script.js
  ├── app.ts
  └── components/
```

**Purpose:**
- Contains dynamic resources
- Files that process/generate content

**Dynamic Resources:**
- CSS files (.css, .scss)
- JavaScript files (.js)
- TypeScript files (.ts)
- React components
- Server-side code

---

### Creating Folders in VS Code

**Method 1: Button**
1. Click "New Folder" icon (top of file explorer)
2. Type folder name: `public`
3. Press Enter

**Method 2: Right-Click**
1. Right-click in file explorer
2. Select "New Folder"
3. Name it

**IMPORTANT:**
- Click outside folder after creating it
- If folder is selected (highlighted), next item goes inside it
- Common beginner mistake!

**Create These Folders:**
```
project/
  ├── public/
  └── src/
```

---

## The index.html File

### Why "index.html"?

**Standard Rule:**
> Every website/application starts with a file named `index.html`

**Examples:**

#### 1. Amazon
```
https://amazon.in
```
Default page = `index.html` (hidden in URL)

#### 2. TutorialsPoint
```
https://tutorialspoint.com/index.htm
```
Shows `index.htm` explicitly

#### 3. Netflix
```
https://netflix.com
```
Landing page = `index.html`

---

### Creating index.html

**Location:** Always in `public/` folder

**Steps:**
1. Click on `public` folder (select it)
2. Click "New File" button
3. Name: `index.html`
4. Press Enter

**Initial Content:**
```html
Welcome to Full Stack Web Development
```
*(Just plain text for now - no HTML tags yet)*

---

### Starting the Development Server

**Method:**
1. Open `index.html` in editor
2. Right-click anywhere in the file
3. Select "Open with Live Server"

**What Happens:**
- Browser automatically opens
- Shows: `http://127.0.0.1:5500/index.html`
- Displays your content
- Auto-refreshes on file changes

**URL Breakdown:**
```
http://127.0.0.1:5500/index.html
  │       │         │      │
  │       │         │      └─ File name
  │       │         └──────── Port number
  │       └────────────────── Localhost IP
  └────────────────────────── Protocol
```

---

## Web Pages Explained

### What is a Web Page?

**Definition:**
> A web page is a hypertext document that provides a user interface (UI) for interacting with resources in an application.

**Breaking It Down:**

#### 1. **Hypertext Document**
- **Hyper** = Beyond
- Contains content beyond what you see
- Hidden content revealed on interaction (clicks)

#### 2. **User Interface (UI)**
- Visual representation
- Buttons, links, forms
- Way to interact with backend resources

#### 3. **Interacting with Resources**
- Access images, videos, documents
- Submit forms, fetch data
- Navigate between pages

---

### Visual Example: How Web Pages Work

```
┌─────────────────────────────────────────┐
│         WEB SERVER                      │
│  ┌───────────────────────────────────┐  │
│  │      WEBSITE                      │  │
│  │  ┌─────────────────────────────┐  │  │
│  │  │  Resources:                 │  │  │
│  │  │  - pic.jpg                  │  │  │
│  │  │  - doc.pdf                  │  │  │
│  │  │  - video.mp4                │  │  │
│  │  └─────────────────────────────┘  │  │
│  └───────────────────────────────────┘  │
└─────────────────────────────────────────┘
                  ↓
          Provides UI (index.html)
                  ↓
┌─────────────────────────────────────────┐
│         USER INTERFACE                  │
│  ┌────────────────┐  ┌───────────────┐  │
│  │  View Picture  │  │  View Doc     │  │
│  └────────────────┘  └───────────────┘  │
│         ↓ (clicks)          ↓ (clicks)  │
│      pic.jpg            doc.pdf          │
└─────────────────────────────────────────┘
```

---

### Practical Example: Netflix Files

**Scenario:** Netflix has resources in folders

**Files:**
```
C:\Netflix\
  ├── images\
  │   └── netflix-back.jpg
  └── docs\
      └── css-demo.pdf
```

**Problem:** Users don't know file paths!

**Solution:** Create `index.html` with links

```html
<a href="images/netflix-back.jpg">Netflix Background</a>
<a href="docs/css-demo.pdf">CSS Tutorial</a>
```

**Result:**
- User visits `netflix.com`
- Sees links (UI)
- Clicks links
- Accesses resources

**Without index.html:**
- User must type: `netflix.com/images/netflix-back.jpg`
- Must know exact path
- Typo = Error 404

---

### index.html as Default Page

**Test Case 1: With index.html**
```
URL: http://127.0.0.1/Netflix
Result: Shows index.html content automatically
```

**Test Case 2: Without index.html**
```
URL: http://127.0.0.1/Netflix
Result: Error - No content to display
```

**Test Case 3: Renamed to home.html**
```
URL: http://127.0.0.1/Netflix
Result: Error - Cannot find index.html

URL: http://127.0.0.1/Netflix/home.html
Result: Shows home.html (manual path required)
```

**Conclusion:**
- Servers configured to look for `index.html` by default
- Without it, website won't start
- Can have hundreds of pages, but only ONE index.html

---

## Static vs Dynamic Memory

### Why This Matters

**Critical Concept:**
> You CANNOT understand static vs dynamic pages without understanding static vs dynamic memory first.

### Memory Types in Computing

#### 1. **Static Memory**
- **Definition:** Continuous memory
- Memory persists across multiple uses
- Once allocated, stays allocated
- Shared across instances

#### 2. **Dynamic Memory**
- **Definition:** Discrete memory
- Memory allocated and deallocated
- Fresh allocation for each use
- Not shared across instances

---

### Code Example: Static vs Dynamic

```javascript
class Demo {
  static s = 0;  // Static variable
  n = 0;         // Non-static variable
  
  constructor() {
    Demo.s = Demo.s + 1;  // Increment static
    this.n = this.n + 1;   // Increment non-static
  }
  
  print() {
    console.log(`s = ${Demo.s}, n = ${this.n}`);
  }
}

// Create three objects
const obj1 = new Demo();
obj1.print();  // Output: s = 1, n = 1

const obj2 = new Demo();
obj2.print();  // Output: s = 2, n = 1

const obj3 = new Demo();
obj3.print();  // Output: s = 3, n = 1
```

---

### Visual Explanation

```
┌─────────────────────────────────────────┐
│   STATIC MEMORY (Continuous)           │
│   ┌────┐                                │
│   │ s  │  obj1 uses → s = 1            │
│   └────┘            ↓                   │
│                  obj2 uses → s = 2      │
│                            ↓            │
│                         obj3 uses → s=3 │
│   MEMORY PERSISTS!                      │
└─────────────────────────────────────────┘

┌─────────────────────────────────────────┐
│   DYNAMIC MEMORY (Discrete)             │
│   ┌────┐                                │
│   │ n  │  obj1 uses → n = 1, CLEANUP   │
│   └────┘                                │
│   ┌────┐                                │
│   │ n  │  obj2 uses → n = 1, CLEANUP   │
│   └────┘                                │
│   ┌────┐                                │
│   │ n  │  obj3 uses → n = 1, CLEANUP   │
│   └────┘                                │
│   MEMORY RESETS EACH TIME!              │
└─────────────────────────────────────────┘
```

**Key Observation:**
- Static `s`: 1 → 2 → 3 (continuous)
- Dynamic `n`: 1 → 1 → 1 (resets each time)

---

### Real-World Example: Database Connection

```
┌─────────────────────────────────────────┐
│         APPLICATION                     │
│  ┌──────┐  ┌──────┐  ┌──────┐          │
│  │Insert│  │Update│  │Delete│          │
│  └───┬──┘  └───┬──┘  └───┬──┘          │
│      │         │         │              │
│      └─────────┼─────────┘              │
│                │                        │
│         ┌──────▼──────┐                 │
│         │ Connection  │                 │
│         └──────┬──────┘                 │
│                │                        │
│         ┌──────▼──────┐                 │
│         │  DATABASE   │                 │
│         └─────────────┘                 │
└─────────────────────────────────────────┘
```

#### Scenario 1: Static Connection

**Flow:**
1. Click Insert → Connect → Insert → Connection stays open
2. Click Update → Use existing connection → Update
3. Click Delete → Use existing connection → Delete

**Pros:**
- ✅ Fast (no reconnection needed)
- ✅ Good for continuous operations

**Cons:**
- ❌ Memory always occupied
- ❌ Security risk (stays logged in)
- ❌ Like Gmail staying signed in - risky on shared PC

---

#### Scenario 2: Dynamic Connection

**Flow:**
1. Click Insert → Connect → Insert → **Disconnect**
2. Click Update → **Reconnect** → Update → **Disconnect**
3. Click Delete → **Reconnect** → Delete → **Disconnect**

**Pros:**
- ✅ Secure (auto logout)
- ✅ Saves memory
- ✅ Like banking app asking password for each transaction

**Cons:**
- ❌ Slower (reconnect each time)
- ❌ More resource intensive

---

### Key Takeaways

**Static Memory (Continuous):**
- Memory persists
- Good for: Frequent operations
- Bad for: Security, memory management

**Dynamic Memory (Discrete):**
- Memory resets
- Good for: Security, resource management
- Bad for: Performance in frequent operations

**Developer's Decision:**
> Choose static or dynamic based on use case, not randomly.

---

## Static vs Dynamic Pages

*Note: Detailed explanation with practical examples will be covered in next session.*

### Preview

**Static Page:**
- Content doesn't change
- Same for all users
- Fixed HTML

**Dynamic Page:**
- Content changes based on user/time
- Different for different users
- Generated on-the-fly

**Tomorrow's Topics:**
- HTML basics
- Designing static pages
- Designing dynamic pages
- Practical differences with examples

---

## Complete Project Structure Summary

```
full-stack-web-application/
│
├── package.json          # Project metadata (auto-generated)
│
├── public/              # Static resources
│   ├── index.html       # Main entry point (REQUIRED)
│   ├── images/          # Image files
│   ├── docs/            # PDF, text files
│   └── videos/          # Video files
│
└── src/                 # Dynamic resources (empty for now)
    ├── styles/          # CSS files (future)
    ├── scripts/         # JavaScript files (future)
    └── components/      # React components (future)
```

---

## Terminal Commands Reference

### Essential Commands

| Command | Purpose | Example |
|---------|---------|---------|
| `npm init -y` | Initialize Node.js project | Creates package.json |
| `Ctrl + C` | Cancel/Terminate command | Stop running process |
| `Ctrl + ` ` | Open/Close terminal | Toggle terminal |
| `cls` | Clear terminal screen | Clean display |

---

## Common Issues & Solutions

### Issue 1: PowerShell Instead of CMD

**Problem:**
```powershell
PS C:\project>
```

**Solution:**
1. Click dropdown in terminal (right side)
2. Select "Command Prompt"
3. Continue with commands

---

### Issue 2: "npm not recognized"

**Problem:**
```
'npm' is not recognized as an internal or external command
```

**Solution:**
1. Node.js not installed properly
2. Reinstall Node.js
3. Check: `node --version` in cmd
4. Restart VS Code

---

### Issue 3: Files Going Inside Wrong Folder

**Problem:** Created file appears inside `public/` instead of root

**Solution:**
1. Click OUTSIDE any folder first
2. Then click "New File"
3. Don't keep folders selected

---

### Issue 4: Live Server Not Working

**Problem:** Right-click doesn't show "Open with Live Server"

**Solution:**
1. Install Live Server extension
2. Restart VS Code
3. Make sure file is `.html` extension
4. Right-click inside file content (not on filename)

---

### Issue 5: Desktop Permission Issues

**Problem:** Can't install libraries on Desktop

**Solution:**
- ❌ Never create projects on Desktop
- ✅ Use C:, D:, or other drives
- Reason: Admin permissions needed for npm packages

---

## Best Practices Checklist

### ✅ Project Setup
- [ ] Create project folder outside Desktop
- [ ] Use hyphenated names (no spaces)
- [ ] Open folder in VS Code
- [ ] Use Command Prompt (not PowerShell)
- [ ] Run `npm init -y`
- [ ] Verify `package.json` created

### ✅ Folder Structure
- [ ] Create `public/` folder
- [ ] Create `src/` folder
- [ ] Create `index.html` in public/
- [ ] Add initial content to index.html

### ✅ Testing
- [ ] Right-click in index.html
- [ ] Open with Live Server
- [ ] Verify browser opens
- [ ] Check URL: `http://127.0.0.1:5500/index.html`
- [ ] Test auto-refresh on file save

---

## Professional Standards Review

### Why Standards Matter

**Example: Color Psychology**
- Supermarket websites → Green (fresh, organic)
- Financial websites → Blue (trust, security)
- Food delivery → Red/Orange (appetite, urgency)
- Tech companies → Blue/White (innovation, clean)

**Example: Festival Offers**
- Orange/Yellow → Sunset/Sunrise (limited time)
- Not random choice → Psychological impact
- Based on research and standards

**Key Point:**
> Professional developers justify every design decision with standards, not personal preference.

---

## Terminology Glossary

| Term | Definition |
|------|------------|
| **npm** | Node Package Manager - manages JavaScript packages |
| **package.json** | File containing project metadata and dependencies |
| **JSON** | JavaScript Object Notation - data format |
| **Terminal** | Command-line interface inside VS Code |
| **Static Resource** | Files that don't change (HTML, images, PDFs) |
| **Dynamic Resource** | Files that process/generate content (CSS, JS) |
| **index.html** | Default starting page of website |
| **Live Server** | VS Code extension for local development server |
| **Localhost** | Your own computer acting as server (127.0.0.1) |
| **Port** | Number identifying specific service (5500 for Live Server) |

---

## Next Session Preview

### Topics to be Covered:
1. HTML Basics
   - HTML syntax and structure
   - Tags and elements
   - Attributes

2. Static vs Dynamic Pages
   - Practical examples
   - Building static pages
   - Understanding when to use each

3. Page Design
   - Creating layouts
   - Using semantic HTML
   - Best practices

---

## Practice Exercises

### Exercise 1: Project Setup
1. Create a new project folder: `my-first-website`
2. Open in VS Code
3. Open terminal (Ctrl + `)
4. Run: `npm init -y`
5. Verify `package.json` created

### Exercise 2: Folder Structure
1. Create `public/` folder
2. Create `src/` folder
3. Create `index.html` in public/
4. Add text: "Hello, World!"
5. Open with Live Server

### Exercise 3: Multiple Pages
1. Create `about.html` in public/
2. Add text: "About Page"
3. Test with Live Server
4. Note: Must specify `about.html` in URL

### Exercise 4: Package.json Modification
1. Open `package.json`
2. Change project name
3. Add description
4. Add your name as author
5. Save and verify changes

### Exercise 5: Terminal Practice
1. Open terminal
2. Check if PowerShell or CMD
3. If PowerShell, switch to CMD
4. Run: `npm init -y`
5. Cancel with Ctrl + C
6. Clear screen: `cls`

---

## Key Concepts to Remember

### 🎯 Critical Points

1. **Every project needs package.json**
   - Makes folder an official Node.js project
   - Lists dependencies and metadata

2. **Always use Command Prompt, not PowerShell**
   - PowerShell may have compatibility issues
   - CMD is more reliable for npm commands

3. **Standard folder structure: public/ and src/**
   - public/ = Static files (HTML, images, PDFs)
   - src/ = Dynamic files (CSS, JS, components)

4. **Every website starts with index.html**
   - Default page shown when domain accessed
   - Must be in public/ folder
   - Server looks for this file first

5. **Static = Continuous, Dynamic = Discrete**
   - Static memory persists
   - Dynamic memory resets
   - Applies to both memory and web pages

---

## Questions to Ask Yourself

1. ❓ Why can't I create projects on Desktop?
2. ❓ What happens if I don't use `-y` flag with npm init?
3. ❓ Why must the starting page be named "index.html"?
4. ❓ What's the difference between public/ and src/ folders?
5. ❓ When would I use static vs dynamic connections?

**Answers:**
1. Admin permission issues with npm packages
2. Terminal asks many questions unsuitable for beginners
3. Web servers configured to look for index.html by default
4. public/ = static resources, src/ = dynamic/processing files
5. Static for continuous operations, dynamic for security/memory management

---

## Additional Resources

### Documentation
- Node.js Official: https://nodejs.org/
- npm Documentation: https://docs.npmjs.com/
- VS Code Docs: https://code.visualstudio.com/docs

### Extensions
- Live Server: ritwickdey.LiveServer
- VS Code Icons: vscode-icons-team.vscode-icons
- IntelliSense: Zignd.html-css-class-completion

---

## Homework

### Task 1: Complete Setup
- [ ] Create project folder
- [ ] Initialize with npm
- [ ] Create folder structure
- [ ] Add index.html
- [ ] Test with Live Server

### Task 2: Experiment
- [ ] Try npm init without -y flag (then cancel)
- [ ] Create different HTML files
- [ ] Test accessing them via URL
- [ ] Rename index.html and see what happens
- [ ] Rename back to index.html

### Task 3: Understanding
- [ ] Read about JSON format
- [ ] Research semantic versioning (1.0.0)
- [ ] Understand localhost and ports
- [ ] Read about static vs dynamic memory

---

## Summary

Today you learned:
- ✅ How to create a professional web application
- ✅ Project structure standards (public/, src/)
- ✅ What package.json is and why it matters
- ✅ How to use terminal in VS Code
- ✅ Difference between static and dynamic memory
- ✅ Why index.html is the starting point
- ✅ How to use Live Server for development
