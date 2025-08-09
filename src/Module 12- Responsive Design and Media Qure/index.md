# 🧪 Module 12: Responsive Design & Media Queries

## 1️⃣ Responsive Principles (Mobile-First)

**Definition:**  
Responsive design ensures that your website looks and works well on all devices (mobile, tablet, desktop).

**Core Principles:**

- **Fluid Layouts:** Use relative units (`%`, `em`, `rem`, `vw`, `vh`) instead of fixed `px`.
  | Unit | Relative To | Common Use |
  | ------ | ----------------------- | ------------------------------------ |
  | `%` | Parent size | Fluid container sizes |
  | `em` | Parent font size | Text spacing inside a container |
  | `rem` | Root font size | Consistent typography & spacing |
  | `vw` | Viewport width | Full-width layouts, responsive fonts |
  | `vh` | Viewport height | Full-screen sections |
  | `vmin` | Smaller of width/height | Fit within smaller dimension |
  | `vmax` | Larger of width/height | Fill bigger dimension |
  | `ch` | Width of "0" | Text blocks with character limits |
  | `ex` | Height of "x" | Rarely used font-based sizing |

#### 1. Viewport = Your Browser Window

Think of the viewport as the visible browser screen.
It has:

- Width (left to right) → vw
- Height (top to bottom) → vh

#### 2. What is vmin?

vmin means “viewport minimum” → it looks at the smaller side of the screen and uses that for calculation.

Example:
📱 Phone in portrait mode:

- Width = 400px → 1vw = 4px
- Height = 800px → 1vh = 8px
- 1vmin = 4px (smaller side is width)

💻 Desktop in landscape mode:

- Width = 1200px → 1vw = 12px
- Height = 800px → 1vh = 8px
- 1vmin = 8px (smaller side is height)

Use vmin when you want something to always fit inside the smallest side of the screen (no overflow).

- **Flexible Images & Media:** Use `max-width: 100%; height: auto;`.
- **Breakpoints:** Adjust design at certain viewport widths.
- **Content Prioritization:** Show the most important information first on small screens.

**Mobile-First Approach:**

- Start designing for **small screens first**, then scale up.
- Use `min-width` in media queries to progressively add styles for larger devices.

```
.square {
  width: 50vmin;
  height: 50vmin;
}
```

> ✅ The square stays perfectly inside the screen, even if the screen is rotated.

#### 3. What is vmax?

vmax means “viewport maximum” → it looks at the bigger side of the screen and uses that for calculation.

Example:
📱 Portrait:

Width = 400px → 1vw = 4px
Height = 800px → 1vh = 8px
1vmax = 8px (bigger side is height)

💻 Landscape:

Width = 1200px → 1vw = 12px
Height = 800px → 1vh = 8px
1vmax = 12px (bigger side is width)

Use vmax when you want something to scale with the larger side of the screen (always big).

Example:

```
.big-text {
  font-size: 5vmax; /* Gets bigger on wider screens */
}

```

```css
/* Base: Mobile first */
body {
  font-size: 16px;
}

/* Larger screens */
@media (min-width: 768px) {
  body {
    font-size: 18px;
  }
}
---

## 2️⃣ Viewport Meta Tag
Why:
Tells the browser how to scale and display your website on different devices.

Basic Mobile-Friendly Setup:

```

<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Parameters:

- width=device-width → Match screen width.
- initial-scale=1.0 → Default zoom.
- maximum-scale=1.0, user-scalable=no → Prevent zoom (use carefully for accessibility).

---

## 3️⃣ Media Queries

Definition:
CSS rules that apply only when certain conditions (width, height, orientation, etc.) are met.

Common Types:

- min-width → Styles apply when screen is wider than given value.
- max-width → Styles apply when screen is narrower than given value.
- orientation → Portrait or landscape mode.
- aspect-ratio → Screen ratio.

Examples:

```
/* min-width (Desktop First) */
@media (min-width: 1024px) {
  .sidebar { display: block; }
}

/* max-width (Mobile First) */
@media (max-width: 600px) {
  .sidebar { display: none; }
}

/* Orientation */
@media (orientation: landscape) {
  body { background-color: lightblue; }
}
```

---

## 4️⃣ Breakpoints Strategy

Definition:
Specific viewport widths where layout changes to improve user experience.

Common Industry Breakpoints:
| Device | min-width | max-width |
| ------------- | --------- | --------- |
| Small Mobile | — | 480px |
| Large Mobile | 481px | 767px |
| Tablet | 768px | 1023px |
| Small Laptop | 1024px | 1279px |
| Desktop | 1280px | 1439px |
| Large Desktop | 1440px+ | — |

Example Strategy:

- Use content-based breakpoints, not device-specific.
- Start small → Add breakpoints when design breaks visually.

---

### 1. % (Percentage)

Relative to:

For width/height → size of the parent container.

For padding/margin → size of the parent container’s width (even for vertical spacing).

```
.box {
  width: 50%; /* Takes up half the width of its parent */
  height: 80%; /* Takes 80% of parent's height */
}
```

## 5️⃣ Container Queries (New!)

Definition:
Apply styles based on container size, not viewport size (CSS level 4 feature).

Why:
Perfect for modular components in responsive layouts.

Example:

```
/* Container Query Setup */
.card {
  container-type: inline-size;
}

/* Style changes when container is >= 500px wide */
@container (min-width: 500px) {
  .card {
    flex-direction: row;
  }
}
```

Benefits:

- More modular and reusable components.
- Avoids messy viewport breakpoints for every component.

---
