# 🎯 CSS `position` Full Course

Learn how to control element positioning using the CSS `position` property. From basics to advanced layouts.

---

## 🔢 All `position` Values

| Value      | Description                                                            |
| ---------- | ---------------------------------------------------------------------- |
| `static`   | Default. Element follows normal document flow.                         |
| `relative` | Positioned relative to its normal position.                            |
| `absolute` | Positioned relative to the nearest positioned ancestor.                |
| `fixed`    | Positioned relative to the viewport (remains on screen during scroll). |
| `sticky`   | Switches between `relative` and `fixed` depending on scroll position.  |

---

## 1. `position: static;` ✅

```css
.box {
  position: static;
}
```

- Default for all elements.
- Top/Left/Right/Bottom: not applied.
- No special positioning behavior.

---

## 2. `position: relative;` 🧭

```css
.box {
  position: relative;
  top: 10px;
  left: 15px;
}
```

- Moves element **relative to its original location**.
- Original space is **preserved**.
- Used to create a **reference context** for absolute children.

---

## 3. `position: absolute;` 🚀

```css
.parent {
  position: relative;
}
.child {
  position: absolute;
  top: 0;
  right: 10px;
}
```

- Removed from normal flow.
- Positioned relative to **nearest positioned ancestor**.
- If none, it uses `<html>` (page).

---

## 4. `position: fixed;` 📌

```css
.box {
  position: fixed;
  top: 0;
  left: 0;
}
```

- Positioned **relative to the viewport**.
- **Stays in place on scroll**.
- Use case: sticky navbar, floating buttons.

---

## 5. `position: sticky;` 🧷

```css
.box {
  position: sticky;
  top: 0;
}
```

- Hybrid: behaves like `relative` until scroll crosses a threshold → then `fixed`.
- Must be inside a scrollable container.
- Use case: headers that stay visible during section scroll.

---

## 🔂 Top / Right / Bottom / Left

These only affect elements with:

- `relative`
- `absolute`
- `fixed`
- `sticky`

```css
.box {
  position: relative;
  top: 20px;
  left: 30px;
}
```

---

## 🔝 `z-index` and Stacking

```css
.box {
  position: absolute;
  z-index: 10;
}
```

- Only applies to **positioned** elements.
- Controls stacking order (foreground/background).

---

## 🧰 Common Layout Patterns

### ✅ Center Element (Absolute)

```css
.box {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
```

### ✅ Tooltip with Absolute

```html
<div class="relative-parent">
  Hover me
  <div class="tooltip">I’m a tooltip</div>
</div>
```

```css
.relative-parent {
  position: relative;
}
.tooltip {
  position: absolute;
  top: 100%;
  left: 0;
}
```

### ✅ Sticky Navbar

```css
.navbar {
  position: sticky;
  top: 0;
  z-index: 1000;
  background: white;
}
```

---

## 🧠 Summary Table

| Value      | Removed From Flow? | Positioned Relative To      | Scrolls? | Use Cases                     |
| ---------- | ------------------ | --------------------------- | -------- | ----------------------------- |
| `static`   | ❌ No              | Document flow               | ✅ Yes   | Default layout                |
| `relative` | ❌ No              | Its own original position   | ✅ Yes   | Slight movement, absolute ref |
| `absolute` | ✅ Yes             | Nearest positioned ancestor | ❌ No    | Modals, tooltips, dropdowns   |
| `fixed`    | ✅ Yes             | Viewport                    | ❌ No    | Navbar, sticky buttons        |
| `sticky`   | ❌/✅ Depends      | Scroll trigger (viewport)   | ✅/❌    | Table headers, subnav bars    |

---

## 🧪 Practice Exercise

1. Create a sticky sidebar.
2. Make a tooltip appear on hover using `absolute`.
3. Try centering a modal with `absolute` and `transform`.

---

## 📎 Extra Tip: Debug with DevTools

Use browser DevTools to:

- Inspect offsets
- Find containing blocks
- Check stacking context

---
