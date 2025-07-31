# 📘 Module 2: CSS Selectors (Complete List: Basic to Advanced)

> Learn **every type of CSS selector** — including rare, advanced, and future-ready selectors.

---

## 🔹 1. Universal and Type Selectors

| Selector  | Example | Description                                                |
| --------- | ------- | ---------------------------------------------------------- |
| `*`       | `* {}`  | Selects all elements.                                      |
| `element` | `p {}`  | Selects all specific elements (like `<p>`, `<div>`, etc.). |

---

## 🔹 2. ID and Class Selectors

| Selector | Example    | Description                    |
| -------- | ---------- | ------------------------------ |
| `#id`    | `#main {}` | Selects element with an `id`.  |
| `.class` | `.btn {}`  | Selects elements with a class. |

---

## 🔹 3. Attribute Selectors

| Selector          | Example             | Description                 |
| ----------------- | ------------------- | --------------------------- | ------- | --------------------------------------------- |
| `[attr]`          | `[required]`        | Has attribute.              |
| `[attr="value"]`  | `[type="checkbox"]` | Exact value.                |
| `[attr^="value"]` | `[href^="https"]`   | Starts with.                |
| `[attr$="value"]` | `[src$=".jpg"]`     | Ends with.                  |
| `[attr*="value"]` | `[title*="sale"]`   | Contains value.             |
| `[attr~=value]`   | `[title~="hello"]`  | Space-separated word match. |
| `[attr            | =value]`            | `[lang                      | ="en"]` | Exact or starts with `value-` (like `en-US`). |

---

## 🔹 4. Combinators

| Selector | Example   | Description             |
| -------- | --------- | ----------------------- |
| `A B`    | `div p`   | Descendant (any level). |
| `A > B`  | `ul > li` | Direct child.           |
| `A + B`  | `h1 + p`  | Adjacent sibling.       |
| `A ~ B`  | `h1 ~ p`  | General sibling.        |

---

## 🔹 5. Pseudo-Classes

### 📌 User Interaction

| Selector         | Example                | Description                |
| ---------------- | ---------------------- | -------------------------- |
| `:hover`         | `a:hover`              | On mouse hover.            |
| `:active`        | `button:active`        | While being clicked.       |
| `:focus`         | `input:focus`          | On focus (keyboard/mouse). |
| `:focus-visible` | `button:focus-visible` | Focused via keyboard.      |
| `:focus-within`  | `form:focus-within`    | Has a child with focus.    |

### 📌 UI State

| Selector                      | Example               | Description              |
| ----------------------------- | --------------------- | ------------------------ |
| `:checked`                    | `input:checked`       | Checked radio/checkbox.  |
| `:disabled`                   | `input:disabled`      | Disabled input.          |
| `:enabled`                    | `input:enabled`       | Enabled input.           |
| `:read-only`                  | `input:read-only`     | Not editable.            |
| `:read-write`                 | `input:read-write`    | Editable input.          |
| `:required`                   | `input:required`      | Input marked required.   |
| `:optional`                   | `input:optional`      | Not required.            |
| `:valid` / `:invalid`         | `input:valid`         | Valid/invalid form data. |
| `:in-range` / `:out-of-range` | `input:in-range`      | Range input constraints. |
| `:default`                    | `input:default`       | Default form control.    |
| `:indeterminate`              | `input:indeterminate` | Checkbox in mixed state. |

### 📌 Structural

| Selector             | Example                | Description            |
| -------------------- | ---------------------- | ---------------------- |
| `:first-child`       | `li:first-child`       | First child of parent. |
| `:last-child`        | `li:last-child`        | Last child of parent.  |
| `:nth-child(n)`      | `li:nth-child(2)`      | Specific child number. |
| `:nth-last-child(n)` | `li:nth-last-child(1)` | From end.              |
| `:only-child`        | `p:only-child`         | The only child.        |
| `:first-of-type`     | `p:first-of-type`      | First of its type.     |
| `:last-of-type`      | `p:last-of-type`       | Last of its type.      |
| `:nth-of-type(n)`    | `p:nth-of-type(2)`     | Based on type.         |
| `:only-of-type`      | `h1:only-of-type`      | Only one of its type.  |
| `:empty`             | `div:empty`            | No children or text.   |

### 📌 Logical

| Selector   | Example                  | Description                                             |
| ---------- | ------------------------ | ------------------------------------------------------- |
| `:not()`   | `div:not(.active)`       | Excludes matching selector.                             |
| `:is()`    | `:is(h1, h2)`            | Matches any in list (with specificity).                 |
| `:where()` | `:where(article, aside)` | Like `:is()` but no specificity.                        |
| `:has()`   | `div:has(img)`           | Selects parents with matching children (Chrome/Safari). |

---

## 🔹 6. Pseudo-Elements

| Selector                 | Example                       | Description                    |
| ------------------------ | ----------------------------- | ------------------------------ |
| `::before`               | `p::before`                   | Insert content before element. |
| `::after`                | `p::after`                    | Insert content after element.  |
| `::first-letter`         | `p::first-letter`             | Style first letter.            |
| `::first-line`           | `p::first-line`               | Style first line.              |
| `::selection`            | `::selection`                 | Selected text.                 |
| `::placeholder`          | `input::placeholder`          | Placeholder text.              |
| `::marker`               | `li::marker`                  | Bullet or list marker.         |
| `::file-selector-button` | `input::file-selector-button` | File input browse button.      |
| `::backdrop`             | `dialog::backdrop`            | Dialog overlay.                |
| `::cue`                  | `::cue`                       | WebVTT captions (video).       |

---

## 🔹 7. Language and Direction

| Selector  | Example     | Description               |
| --------- | ----------- | ------------------------- |
| `:lang()` | `:lang(en)` | Language-specific styles. |
| `:dir()`  | `:dir(rtl)` | Directionality (ltr/rtl). |

---

## 🔹 8. Special Global Keywords

These are not selectors, but **universal keywords** that affect all properties:

| Keyword      | Example                 | Description                               |
| ------------ | ----------------------- | ----------------------------------------- |
| `inherit`    | `color: inherit`        | Inherit value from parent.                |
| `initial`    | `color: initial`        | Set to default CSS value.                 |
| `unset`      | `color: unset`          | Resets depending on inheritability.       |
| `revert`     | `color: revert`         | Reverts to browser/user-agent stylesheet. |
| `!important` | `color: red !important` | Overrides everything.                     |

---

## 🔹 9. Specificity & Best Practices

| Specificity Level | Selector                        | Power         |
| ----------------- | ------------------------------- | ------------- |
| Type              | `div`, `a`                      | Low           |
| Class/Attr        | `.btn`, `[type=text]`, `:hover` | Medium        |
| ID                | `#nav`                          | High          |
| Inline            | `style="..."`                   | Very High     |
| `!important`      | `color: red !important`         | Overrides all |

---

## ✅ Example

```html
<ul>
  <li class="active">Item 1</li>
  <li>Item 2</li>
</ul>
```

```css
ul > li:first-child {
  color: red;
}
ul li:last-child:hover {
  color: blue;
}
ul:has(.active) {
  border: 2px solid green;
}
```

---
