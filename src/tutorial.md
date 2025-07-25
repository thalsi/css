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
