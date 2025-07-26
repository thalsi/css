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

| Selector Type      | Syntax          | Example           | Selects...                                      |
| ------------------ | --------------- | ----------------- | ----------------------------------------------- |
| **Universal**      | `*`             | `* {}`            | All elements on the page                        |
| **Type (Element)** | `element`       | `p {}`            | All `<p>` elements                              |
| **Class**          | `.classname`    | `.btn {}`         | All elements with `class="btn"`                 |
| **ID**             | `#idname`       | `#header {}`      | The element with `id="header"`                  |
| **Group**          | `selector, ...` | `h1, .box, #main` | All matching `h1`, class `.box`, and ID `#main` |
| **Descendant**     | `A B`           | `div p {}`        | All `<p>` inside `<div>`                        |

---

## 2. Grouping & Combinators

### 2.1 Grouping Selector

| Selector      | Description                  | Example                     |
| ------------- | ---------------------------- | --------------------------- |
| `h1, p, .box` | Styles all matching elements | `h1`, all `<p>`, and `.box` |

---

### 2.2 Combinators

| Combinator     | Syntax  | Description                                     | Example   | Matches...                                 |
| -------------- | ------- | ----------------------------------------------- | --------- | ------------------------------------------ |
| **Descendant** | `A B`   | Selects `B` **inside** `A` (any level deep)     | `div p`   | All `<p>` inside any `<div>`               |
| **Child**      | `A > B` | Selects `B` that is a **direct child** of `A`   | `ul > li` | `<li>` directly inside `<ul>`              |
| **Adjacent**   | `A + B` | Selects `B` that is the **next sibling** of `A` | `h2 + p`  | `<p>` that comes **right after** an `<h2>` |
| **General**    | `A ~ B` | Selects **all siblings** `B` after `A`          | `h2 ~ p`  | All `<p>` siblings after an `<h2>`         |

---

### 2.3 Attribute Selectors

| Selector          | Meaning             | Example             |
| ----------------- | ------------------- | ------------------- |
| `[attr]`          | Has that attribute  | `[disabled]`        |
| `[attr="value"]`  | Exact match         | `[type="checkbox"]` |
| `[attr^="value"]` | Starts with         | `[href^="https"]`   |
| `[attr$="value"]` | Ends with           | `[src$=".jpg"]`     |
| `[attr*="value"]` | Contains (anywhere) | `[title*="sale"]`   |

---

### 2.4 Advanced Selectors

### 1. Attribute Selectors

| Selector          | Meaning            | Example                        |          |                        |
| ----------------- | ------------------ | ------------------------------ | -------- | ---------------------- |
| `[attr]`          | Has attribute      | `input[required]`              |          |                        |
| `[attr="value"]`  | Exact value        | `a[target="_blank"]`           |          |                        |
| `[attr~="value"]` | Contains word      | `[title~="sale"]`              |          |                        |
| \`\[attr          | ="value"]\`        | Exact or value followed by `-` | \`\[lang | ="en"]`→`en`, `en-US\` |
| `[attr^="value"]` | Starts with        | `a[href^="https"]`             |          |                        |
| `[attr$="value"]` | Ends with          | `img[src$=".jpg"]`             |          |                        |
| `[attr*="value"]` | Contains substring | `div[class*="header"]`         |          |                        |

---

### 2. Combinators

| Selector | Meaning                      | Example   |
| -------- | ---------------------------- | --------- |
| `A B`    | Descendant                   | `div p`   |
| `A > B`  | Direct child                 | `ul > li` |
| `A + B`  | Adjacent sibling (next only) | `h2 + p`  |
| `A ~ B`  | General sibling (any after)  | `h2 ~ p`  |

---

### 3. Grouping

| Selector      | Description                  | Example                     |
| ------------- | ---------------------------- | --------------------------- |
| `h1, p, .box` | Styles all matching elements | `h1`, all `<p>`, and `.box` |

---

### 4. Pseudo-Classes

| Selector                    | Meaning                     |
| --------------------------- | --------------------------- |
| `:hover`                    | Mouse over                  |
| `:active`                   | While clicking              |
| `:focus`                    | Focused (e.g., input field) |
| `:checked`                  | Checked checkbox/radio      |
| `:disabled`                 | Disabled form field         |
| `:enabled`                  | Enabled form field          |
| `:required`                 | Required field              |
| `:optional`                 | Optional field              |
| `:valid`, `:invalid`        | Form validation states      |
| `:read-only`, `:read-write` | Input read-only/write       |

---

### 5. Structural Selectors

| Selector             | Example                                                    |
| -------------------- | ---------------------------------------------------------- |
| `:first-child`       | `li:first-child { font-weight: bold; }`                    |
| `:last-child`        | `li:last-child { color: red; }`                            |
| `:nth-child(3)`      | `li:nth-child(3) { background: yellow; }`                  |
| `:nth-last-child(2)` | `li:nth-last-child(2) { color: purple; }`                  |
| `:only-child`        | `div:only-child { margin: 2rem; }`                         |
| `:first-of-type`     | `p:first-of-type { font-size: 20px; }`                     |
| `:last-of-type`      | `p:last-of-type { font-style: italic; }`                   |
| `:nth-of-type(2)`    | `p:nth-of-type(2) { color: green; }`                       |
| `:only-of-type`      | `h2:only-of-type { border: 2px solid blue; }`              |
| `:empty`             | `div:empty { height: 30px; background: lightgray; }`       |
| `:not(selector)`     | `div:not(.active) { opacity: 0.5; }`                       |
| `:is(h1, h2, h3)`    | `:is(h1, h2, h3) { margin: 0; }`                           |
| `:where(h1, h2, h3)` | `:where(h1, h2, h3) { font-weight: normal; }`              |
| `:has(img)`          | `div:has(img) { padding: 1rem; }` (🧪 modern support only) |

--
