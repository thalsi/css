## Flexbox Master Course – Complete Guide

### Module 1: Introduction to Flexbox

| Topic                   | Details                                                                      |
| ----------------------- | ---------------------------------------------------------------------------- |
| What is Flexbox?        | A one-dimensional layout model for aligning items in **rows** or **columns** |
| Why Use Flexbox?        | Easy centering, flexible sizing, responsive layouts                          |
| Main Axis vs Cross Axis | Main: direction of `flex-direction`; Cross: perpendicular axis               |

---

### Module 2: Flex Container Properties

| Property          | Values                                                                              | Description                                  |
| ----------------- | ----------------------------------------------------------------------------------- | -------------------------------------------- |
| `display`         | `flex` / `inline-flex`                                                              | Activates Flexbox layout                     |
| `flex-direction`  | `row` (default), `row-reverse`, `column`, `column-reverse`                          | Main axis direction                          |
| `flex-wrap`       | `nowrap` (default), `wrap`, `wrap-reverse`                                          | Allows items to wrap to next line            |
| `flex-flow`       | `<flex-direction> <flex-wrap>`                                                      | Shorthand for direction + wrap               |
| `justify-content` | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` | Aligns items along main axis                 |
| `align-items`     | `stretch` (default), `flex-start`, `flex-end`, `center`, `baseline`                 | Aligns items on the cross axis               |
| `align-content`   | `stretch`, `flex-start`, `flex-end`, `center`, `space-between`, `space-around`      | Aligns rows on cross axis when there’s space |
| `gap`             | `row-gap column-gap`                                                                | Space between rows and/or columns            |

**Example**:

```css
.flex-container {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 10px 20px;
}
```

---

### Module 3: Flex Item Properties

| Property      | Values                             | Description                                     |
| ------------- | ---------------------------------- | ----------------------------------------------- |
| `order`       | `<integer>`                        | Controls the **visual order** of items          |
| `flex-grow`   | `<number>` (default `0`)           | Defines how much an item can grow               |
| `flex-shrink` | `<number>` (default `1`)           | Defines how much an item can shrink             |
| `flex-basis`  | `auto`, `<length>`                 | Initial size before growing or shrinking        |
| `flex`        | `flex-grow flex-shrink flex-basis` | Shorthand                                       |
| `align-self`  | Overrides `align-items` per item   | Same values: `auto`, `center`, `flex-end`, etc. |

**Example**:

```css
.item {
  flex: 1 0 200px;
  order: 2;
  align-self: center;
}
```

---

### Module 4: Use Cases & Layout Patterns

**Centering an Element**

```css
.parent {
  display: flex;
  justify-content: center;
  align-items: center;
}
```

**Navigation Bar**

```css
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
```

**Equal Height Columns**

```css
.row {
  display: flex;
}
.col {
  flex: 1;
}
```

**Responsive Grid**

```css
.container {
  display: flex;
  flex-wrap: wrap;
}
.item {
  flex: 1 1 300px;
}
```

---

### Module 5: Common Issues & Fixes

| Problem                | Solution                                       |
| ---------------------- | ---------------------------------------------- |
| Items overflow         | Use `flex-wrap: wrap`                          |
| Items don't shrink     | Check `flex-shrink` value                      |
| Centering doesn't work | Check both `justify-content` and `align-items` |
| Uneven spacing         | Use `gap` or `space-evenly`                    |

---

### Module 6: Real Projects

| Project              | Flex Usage                                             |
| -------------------- | ------------------------------------------------------ |
| **Pricing Cards**    | `flex: 1`, `align-items: stretch`                      |
| **Dashboard Layout** | Side menu + main using `flex: 0 0 250px` and `flex: 1` |
| **Photo Gallery**    | `flex-wrap` with `gap`                                 |

---

### Module 7: Advanced Topics

- Nesting Flexbox (flex inside flex)
- Combining Flexbox with CSS Grid
- Accessibility in Flex layouts
- Logical properties: `margin-inline-start`, etc.
