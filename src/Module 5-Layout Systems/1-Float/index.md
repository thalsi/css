# CSS `float` – Full Reference

## 📘 Definition:

The `float` property places an element on the left or right side of its container, allowing text and inline elements to wrap around it.

---

## ✅ Syntax:

```css
float: left | right | none | inline-start | inline-end;
```

---

## 🔹 Values:

| Value          | Description                                                                |
| -------------- | -------------------------------------------------------------------------- |
| `left`         | Floats the element to the left. Content wraps on the right.                |
| `right`        | Floats the element to the right. Content wraps on the left.                |
| `none`         | Default. Element does **not** float.                                       |
| `inline-start` | Floats to the **start** edge of inline direction (logical `left`/`right`). |
| `inline-end`   | Floats to the **end** edge of inline direction.                            |
| `inherit`      | Inherits the float value from the parent.                                  |

---

## 🧱 Example:

```html
<div class="box left">Left Float</div>
<div class="box right">Right Float</div>
<p>This text wraps around floated elements.</p>
```

```css
.box {
  width: 150px;
  height: 150px;
  margin: 10px;
  padding: 10px;
  background: lightblue;
}
.left {
  float: left;
}
.right {
  float: right;
}
```

---

## 🔄 Related Property: `clear`

### Purpose:

Clears floats to prevent elements from wrapping around floated elements.

### Values:

| Value   | Description                           |
| ------- | ------------------------------------- |
| `left`  | Clears left-floated elements.         |
| `right` | Clears right-floated elements.        |
| `both`  | Clears both left and right floats. ✅ |
| `none`  | Default. Allows wrapping.             |

### Example:

```css
.clearfix {
  clear: both;
}
```

**Modern clearfix hack:**

```css
.container::after {
  content: '';
  display: table;
  clear: both;
}
```

---

## ⚠️ Common Float Issues & Fixes

| Problem                               | Solution                                                 |
| ------------------------------------- | -------------------------------------------------------- |
| Floated elements not expanding parent | Use `clearfix` or `overflow: hidden` on parent container |
| Elements wrapping unexpectedly        | Use `clear` on next sibling                              |
| Layout breaks in complex structures   | Prefer `flex` or `grid` for layout (float is outdated)   |

---

## 🧪 Use Case Example:

```html
<div class="container">
  <img src="image.jpg" class="img-float" alt="Side image" />
  <p>This text wraps around the image floated to the left side.</p>
</div>
```

```css
.img-float {
  float: left;
  width: 200px;
  margin: 0 15px 15px 0;
}
```

---

## 💡 When to Use `float`

| ✅ Use Cases                   | ❌ Avoid for                     |
| ------------------------------ | -------------------------------- |
| Wrapping text around images    | Full-page layout (use Flex/Grid) |
| Old-school print-style columns | Complex modern UI                |
| Minor visual floats (badges)   | Responsive layout systems        |
