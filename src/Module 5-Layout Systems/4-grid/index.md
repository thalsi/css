# 📐 CSS Grid – Two-Dimensional Layout Guide

CSS Grid Layout is a **powerful layout system** designed for building two-dimensional layouts—rows and columns—with full control over alignment, spacing, and responsive structure.

---

## 📦 Key Concepts

| Term               | Description                                      |
| ------------------ | ------------------------------------------------ |
| **Grid Container** | The parent element that uses `display: grid`.    |
| **Grid Items**     | The direct children of the grid container.       |
| **Grid Lines**     | The dividing lines between rows and columns.     |
| **Grid Tracks**    | Rows and columns (space between two grid lines). |
| **Grid Cells**     | Single space formed by one row and one column.   |
| **Grid Area**      | A rectangular area made of multiple cells.       |

---

## ✅ 1. Grid Container Properties

These are applied to the **grid container** (parent).

| **Property**            | **Values / Syntax**                                                                 | **Description**                                                                         |
| ----------------------- | ----------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| `display`               | `grid` \| `inline-grid`                                                             | Turns an element into a grid container.                                                 |
| `grid-template-columns` | `auto`, `px`, `%`, `fr`, `repeat()`, `minmax()`                                     | Defines column tracks (widths).                                                         |
| `grid-template-rows`    | Same as above                                                                       | Defines row tracks (heights).                                                           |
| `grid-template-areas`   | String-based template                                                               | Creates named layout zones.                                                             |
| `grid-template`         | `rows / columns` or includes `areas`                                                | Shorthand for `grid-template-rows`, `grid-template-columns`, and `grid-template-areas`. |
| `grid-auto-columns`     | `<length>` or `auto`                                                                | Size for implicitly created columns.                                                    |
| `grid-auto-rows`        | `<length>` or `auto`                                                                | Size for implicitly created rows.                                                       |
| `grid-auto-flow`        | `row` \| `column` \| `row dense` \| `column dense`                                  | Direction of auto-placement.                                                            |
| `grid`                  | Shorthand: layout, flow, auto tracks                                                | Combines `grid-template`, `grid-auto-flow`, `grid-auto-rows/columns`.                   |
| `column-gap`            | `<length>`                                                                          | Spacing between **columns**.                                                            |
| `row-gap`               | `<length>`                                                                          | Spacing between **rows**.                                                               |
| `gap`                   | Shorthand: `row-gap column-gap`                                                     | Space between **tracks**.                                                               |
| `justify-items`         | `start` \| `end` \| `center` \| `stretch`                                           | Aligns items **horizontally** in cells.                                                 |
| `align-items`           | `start` \| `end` \| `center` \| `stretch`                                           | Aligns items **vertically** in cells.                                                   |
| `place-items`           | Shorthand: `align-items justify-items`                                              | Aligns in both directions.                                                              |
| `justify-content`       | `start` \| `end` \| `center` \| `space-between` \| `space-around` \| `space-evenly` | Aligns the **whole grid** horizontally.                                                 |
| `align-content`         | Same as above                                                                       | Aligns the **whole grid** vertically.                                                   |
| `place-content`         | Shorthand: `align-content justify-content`                                          | Aligns full grid in both directions.                                                    |

---

## ✅ 2. Grid Item Properties

Applied to **grid items** (children of a grid container).

| **Property**        | **Values / Syntax**                                           | **Description**                       |
| ------------------- | ------------------------------------------------------------- | ------------------------------------- |
| `grid-column-start` | `<number>` \| `name` \| `span <n>` \| `auto`                  | Start line of the column.             |
| `grid-column-end`   | Same as above                                                 | End line of the column.               |
| `grid-column`       | `start / end`                                                 | Shorthand.                            |
| `grid-row-start`    | `<number>` \| `name` \| `span <n>` \| `auto`                  | Start line of the row.                |
| `grid-row-end`      | Same as above                                                 | End line of the row.                  |
| `grid-row`          | `start / end`                                                 | Shorthand.                            |
| `grid-area`         | `row-start / column-start / row-end / column-end` \| `<name>` | Shorthand for placement.              |
| `justify-self`      | `start` \| `end` \| `center` \| `stretch`                     | Aligns item horizontally in its cell. |
| `align-self`        | `start` \| `end` \| `center` \| `stretch`                     | Aligns item vertically in its cell.   |
| `place-self`        | `align-self justify-self`                                     | Shorthand for individual alignment.   |

---

## ✅ 3. Grid Functions and Units

| **Function / Unit** | **Description**                                     |
| ------------------- | --------------------------------------------------- |
| `fr`                | Fraction of remaining space. (`1fr`, `2fr`, etc.)   |
| `auto`              | Size based on content.                              |
| `min-content`       | Minimum size without overflow.                      |
| `max-content`       | Maximum size before wrapping.                       |
| `minmax(min, max)`  | Sets size range (e.g., `minmax(100px, 1fr)`).       |
| `repeat(n, value)`  | Repeats a pattern (e.g., `repeat(3, 1fr)`).         |
| `auto-fill`         | Fills rows/columns with as many tracks as will fit. |
| `auto-fit`          | Like `auto-fill`, but collapses empty tracks.       |
| `subgrid` (exp)     | Inherits parent grid tracks in nested layouts.      |

---

## ✅ 4. Named Grid Lines

```css
grid-template-columns: [start] 1fr [middle] 1fr [end];
.item {
  grid-column: start / end;
}
```

Use custom line names to place items more intuitively.

---

## ✅ 5. Named Grid Areas

```css
.container {
  display: grid;
  grid-template-areas:
    'header header'
    'sidebar main'
    'footer footer';
}

.header {
  grid-area: header;
}
.sidebar {
  grid-area: sidebar;
}
.main {
  grid-area: main;
}
.footer {
  grid-area: footer;
}
```

Improves readability in layout planning.

---

## ✅ 6. Visual Debug Tip

```css
.container {
  display: grid;
  outline: 1px solid red;
}
.item {
  outline: 1px dashed blue;
}
```

This helps visualize the grid structure during development.

---

## ✅ 7. Real-World Example

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto auto;
  gap: 20px;
}

.item1 {
  grid-column: 1 / 3;
  grid-row: 1;
}
```

Creates a two-column layout with spacing and an item spanning both columns.

---
