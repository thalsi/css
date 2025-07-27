# 📦 Core Fundamentals

## 1. What is CSS, syntax, rules?

- CSS (Cascading Style Sheets) is a stylesheet language

---

### 1.1 CSS Syntax

```
selector{
    property: value;
}
```

---

### 1.2 CSS Rule

| Part            | Description                                                   |
| --------------- | ------------------------------------------------------------- |
| **Selector**    | Specifies the HTML element to style (`h1`, `.btn`, `#header`) |
| **Property**    | The style attribute to change (`color`, `font-size`, etc.)    |
| **Value**       | The value assigned to the property (`red`, `16px`, etc.)      |
| **Declaration** | A combination of property and value (`color: red;`)           |
| **Rule**        | A full set of declarations within a selector                  |

Example Rule:

```
.button {
  background-color: #007BFF;
  color: white;
  padding: 10px 20px;
}

```

CSS Rule Structure

```
selector {
  property1: value1;
  property2: value2;
  ...
}

```

CSS Rule Types

| Rule Type          | Description                            | Example                        |
| ------------------ | -------------------------------------- | ------------------------------ |
| **Element Rule**   | Targets all elements of a type         | `p { ... }`                    |
| **Class Rule**     | Targets elements with a specific class | `.menu { ... }`                |
| **ID Rule**        | Targets a specific element by its ID   | `#header { ... }`              |
| **Group Rule**     | Targets multiple selectors             | `h1, h2, h3 { ... }`           |
| **Universal Rule** | Targets all elements                   | `* { margin: 0; padding: 0; }` |

---

## 2. Types of CSS

| Type             | Where Defined                    | Syntax Example                    |
| ---------------- | -------------------------------- | --------------------------------- |
| **Inline CSS**   | Inside an HTML element           | `<p style="color: red;">Text</p>` |
| **Internal CSS** | Inside `<style>` tag in `<head>` | See below                         |
| **External CSS** | In a separate `.css` file        | See below                         |

## 3. CSS Comments

| Purpose                    | Example                             |
| -------------------------- | ----------------------------------- |
| Explain complex code       | `/* Centering the content */`       |
| Section headings           | `/* === HEADER SECTION === */`      |
| Temporarily disable a rule | `/* color: red; */`                 |
| Notes for other developers | `/* TODO: Add responsive styles */` |

---

### 4. CSS File Structure

```
/css
│
├── base/         # Reset, typography, general styles
│   └── _reset.css
│   └── _typography.css
│
├── components/   # Buttons, cards, modals, etc.
│   └── _button.css
│   └── _modal.css
│
├── layout/       # Header, footer, grid, sidebar
│   └── _header.css
│   └── _footer.css
│
├── pages/        # Page-specific styles
│   └── _home.css
│   └── _about.css
│
├── themes/       # Light/dark themes, color schemes
│   └── _dark.css
│
├── utils/        # Mixins, helpers, variables
│   └── _variables.css
│   └── _helpers.css
│
└── main.css      # Master file importing everything

```

---

# 🎯 Module 2: Selectors (Basic to Advanced)

## 1. Basic Selectors

| **Selector** | **Description**                              | **Example**                       | **Usage**                                                               |
| ------------ | -------------------------------------------- | --------------------------------- | ----------------------------------------------------------------------- |
| `*`          | Universal – selects **all elements**         | `* { box-sizing: border-box; }`   | Used for global resets or applying base rules to every element          |
| `element`    | Type selector – selects by **tag name**      | `div { margin: 1rem; }`           | Used to style all elements of a specific type like all `p`, `ul`, etc.  |
| `.class`     | Selects elements by **class**                | `.highlight { color: red; }`      | Apply common styles to multiple elements sharing the same class         |
| `#id`        | Selects a **single unique** element by ID    | `#main { padding: 20px; }`        | Target one specific element, like a main container                      |
| `A B`        | **Descendant** – selects B inside A          | `div p { color: gray; }`          | Style elements deeply nested inside containers                          |
| `A > B`      | **Direct child** – only B directly inside A  | `ul > li { list-style: square; }` | Useful when children need different styles than nested descendants      |
| `A + B`      | **Adjacent sibling** – B right after A       | `h1 + p { font-style: italic; }`  | Style paragraphs immediately following a heading                        |
| `A ~ B`      | **General sibling** – all B siblings after A | `h2 ~ p { color: red; }`          | Target all later siblings of same parent, like a group of related notes |

---

## 2. Attribute Selectors

| **Selector**     | **Description**                                      | **Example**                                  | **Usage**                                               |                                  |                                           |
| ---------------- | ---------------------------------------------------- | -------------------------------------------- | ------------------------------------------------------- | -------------------------------- | ----------------------------------------- |
| `[attr]`         | Element with the attribute, any value                | `input[required] { border: red; }`           | Highlight required fields                               |                                  |                                           |
| `[attr="value"]` | Attribute must match exactly                         | `input[type="text"] { color: blue; }`        | Style specific input types                              |                                  |                                           |
| `[attr^="val"]`  | Attribute starts with value                          | `a[href^="https"] { color: green; }`         | Target secure links                                     |                                  |                                           |
| `[attr$="val"]`  | Attribute ends with value                            | `img[src$=".jpg"] { border-radius: 8px; }`   | Style images with certain file types                    |                                  |                                           |
| `[attr*="val"]`  | Attribute contains substring                         | `div[class*="error"] { background: pink; }`  | Style all error messages, regardless of full class name |                                  |                                           |
| `[attr~="val"]`  | Attribute is a space-separated list containing value | `[title~="sale"] { font-weight: bold; }`     | Highlight products tagged with specific words           |                                  |                                           |
| \`\[attr         | ="val"]\`                                            | Attribute equals `val` or starts with `val-` | \`\[lang                                                | ="en"] { font-style: italic; }\` | Style content based on language or locale |

---

## 3. Structural Pseudo-classes

| **Selector**           | **Description**                          | **Example**                                    | **Usage**                                                      |
| ---------------------- | ---------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------- |
| `:first-child`         | First child of its parent                | `li:first-child { font-weight: bold; }`        | Style the first item in a list                                 |
| `:last-child`          | Last child of its parent                 | `li:last-child { color: red; }`                | Style the last item in a navigation or group                   |
| `:nth-child(n)`        | Select nth child (1-based index)         | `li:nth-child(2) { color: green; }`            | Zebra-striping rows or selecting specific children             |
| `:nth-last-child(n)`   | Select nth child from end                | `li:nth-last-child(1) { font-style: italic; }` | Useful when you don’t know total count but want last few items |
| `:only-child`          | Matches if it’s the only child           | `p:only-child { border: 1px solid blue; }`     | Style unique items that appear alone                           |
| `:first-of-type`       | First of specific tag among siblings     | `p:first-of-type { color: purple; }`           | When the first heading or paragraph needs emphasis             |
| `:last-of-type`        | Last of specific tag among siblings      | `p:last-of-type { font-size: 1.2em; }`         | Style last instance of repeated tag like `li` or `p`           |
| `:nth-of-type(n)`      | Nth of a specific tag                    | `div:nth-of-type(2) { background: #eee; }`     | For layout structures or column grids                          |
| `:nth-last-of-type(n)` | Nth of type from the end                 | `div:nth-last-of-type(1) { color: brown; }`    | Target last few items of same type                             |
| `:only-of-type`        | Only one of that tag type among siblings | `span:only-of-type { color: orange; }`         | Prevent duplicate styles when there's only one tag present     |
| `:empty`               | No children or content                   | `div:empty { display: none; }`                 | Hide empty wrappers or placeholders                            |

---

## 4. UI State Pseudo-classes

| **Selector**     | **Description**                        | **Example**                                          | **Usage**                                        |
| ---------------- | -------------------------------------- | ---------------------------------------------------- | ------------------------------------------------ |
| `:hover`         | When mouse hovers                      | `a:hover { color: red; }`                            | Create hover effects on links or buttons         |
| `:focus`         | Element is focused                     | `input:focus { outline: 2px solid blue; }`           | Improve keyboard accessibility and styling       |
| `:focus-within`  | Parent element with focused child      | `form:focus-within { border: 2px solid green; }`     | Highlight entire forms when any input is focused |
| `:focus-visible` | Focused by keyboard (not mouse)        | `button:focus-visible { border: 2px dashed blue; }`  | Reduce focus outlines to only keyboard users     |
| `:active`        | When element is being clicked          | `button:active { background: orange; }`              | Add button press effect                          |
| `:checked`       | Input is checked                       | `input:checked + label { font-weight: bold; }`       | Style selected checkboxes/radio buttons          |
| `:enabled`       | Input is enabled (not disabled)        | `input:enabled { background: white; }`               | Style only working input fields                  |
| `:disabled`      | Input is disabled                      | `input:disabled { background: #eee; }`               | Show disabled inputs as inactive                 |
| `:required`      | Field is required                      | `input:required { border-left: 4px solid red; }`     | Visually indicate mandatory fields               |
| `:optional`      | Field is not required                  | `input:optional { border-left: 4px solid green; }`   | Differentiate optional fields                    |
| `:read-only`     | Cannot be edited                       | `input:read-only { background: #f8f8f8; }`           | Indicate locked input fields                     |
| `:read-write`    | Can be edited                          | `textarea:read-write { background: white; }`         | Highlight editable areas                         |
| `:indeterminate` | Checkbox neither checked nor unchecked | `input:indeterminate { outline: 2px dotted black; }` | For partial selection states (JS-based)          |
| `:default`       | Default form control                   | `button:default { font-weight: bold; }`              | Highlight primary submit buttons                 |

---

## 5. Logic Selectors

| **Selector**         | **Description**                               | **Example**                                   | **Usage**                                                     |
| -------------------- | --------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------- |
| `:not(sel)`          | Select elements **not** matching selector     | `li:not(.active) { color: gray; }`            | Exclude items from style rules                                |
| `:is(sel1, sel2)`    | Matches any of listed selectors (specificity) | `:is(h1, h2) { margin: 0; }`                  | Cleaner group targeting with full specificity                 |
| `:where(sel1, sel2)` | Like `:is`, but no specificity                | `:where(section, article) { padding: 1rem; }` | Use in resets or design systems to avoid conflicts            |
| `:has(sel)`          | Select parent with matching child (modern)    | `div:has(img) { border: 1px solid red; }`     | Conditional styling when children exist (Chrome support only) |

---

## 6. Pseudo-elements

| **Selector**     | **Description**                 | **Example**                                         | **Usage**                                              |
| ---------------- | ------------------------------- | --------------------------------------------------- | ------------------------------------------------------ |
| `::before`       | Insert content before element   | `p::before { content: "→ "; }`                      | Add icons, symbols, or annotations before real content |
| `::after`        | Insert content after element    | `p::after { content: " ✓"; }`                       | Add status indicators after text                       |
| `::first-line`   | Style first line of text        | `p::first-line { font-weight: bold; }`              | Create typographic effects in paragraphs               |
| `::first-letter` | Style first letter              | `p::first-letter { font-size: 150%; }`              | Create drop caps or stylized headlines                 |
| `::selection`    | Style user-selected text        | `::selection { background: yellow; }`               | Customize highlight color                              |
| `::placeholder`  | Style input placeholder text    | `input::placeholder { color: gray; }`               | Improve placeholder visibility                         |
| `::marker`       | Style bullets or list numbers   | `li::marker { color: red; font-size: 1.5em; }`      | Custom bullets for lists                               |
| `::backdrop`     | Fullscreen background in modals | `::backdrop { background-color: rgba(0,0,0,0.8); }` | Style behind dialogs or fullscreen popups              |
| `::cue`          | Style subtitles for media       | `::cue { color: white; }`                           | Apply themes to video captions                         |

---

## 7. Other Special Selectors

| **Selector**              | **Description**                                       | **Example**                          | **Usage**                                           |
| ------------------------- | ----------------------------------------------------- | ------------------------------------ | --------------------------------------------------- |
| `:lang(lang-code)`        | Match elements by language                            | `p:lang(en) { font-style: italic; }` | Apply styles based on language locale               |
| `:dir(ltr)` / `:dir(rtl)` | Match text direction (left-to-right or right-to-left) | `:dir(rtl) { text-align: right; }`   | RTL language support                                |
| `:root`                   | Targets root element (`<html>`)                       | `:root { --main-color: #333; }`      | Define CSS custom properties (variables) globally   |
| `:scope`                  | Current context in query selector or shadow DOM       | `:scope > h2 { font-weight: bold; }` | Used in scripts or scoped styling within components |

---
