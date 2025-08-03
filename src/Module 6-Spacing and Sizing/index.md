# Module 6: Spacing & Sizing

## 📑 Table of Contents

1. [Margin & Padding (All Directions)](#margin--padding-all-directions)
2. [Width, Height, Max/Min](#width-height-maxmin)
3. [aspect-ratio](#aspect-ratio)
4. [Centering (Horizontally/Vertically)](#centering-horizontallyvertically)

---

## 1. Margin & Padding (All Directions)

**Margin** adds space _outside_ an element’s border.  
**Padding** adds space _inside_ an element’s border.

| Property  | Purpose     |
| --------- | ----------- |
| `margin`  | Outer space |
| `padding` | Inner space |

### ➤ Direction-based Properties

| Direction | Margin          | Padding          |
| --------- | --------------- | ---------------- |
| All       | `margin`        | `padding`        |
| Top       | `margin-top`    | `padding-top`    |
| Right     | `margin-right`  | `padding-right`  |
| Bottom    | `margin-bottom` | `padding-bottom` |
| Left      | `margin-left`   | `padding-left`   |

### ➤ Shorthand Syntax

```css
/* 1 value → all sides */
margin: 20px;

/* 2 values → top-bottom, left-right */
margin: 20px 10px;

/* 3 values → top, left-right, bottom */
margin: 10px 5px 20px;

/* 4 values → top, right, bottom, left */
margin: 5px 10px 15px 20px;

---
## 2. Width, Height, Max/Min

| Property     | Description                          |
| ------------ | ------------------------------------ |
| `width`      | Exact width                          |
| `height`     | Exact height                         |
| `min-width`  | Smallest width element can shrink to |
| `max-width`  | Largest width element can grow to    |
| `min-height` | Minimum height                       |
| `max-height` | Maximum height                       |

```

div {
width: 400px;
max-width: 100%;
height: 300px;
min-height: 200px;
}

```

3. aspect-ratio
```

.box {
aspect-ratio: 16 / 9;
width: 400px;
}

```
- Calculates height automatically → height = width ÷ (ratio)
- Common for images, videos, cards, responsive boxe

4. Centering (Horizontally/Vertically)

| Goal                          | Method / Code                                                            |
| ----------------------------- | ------------------------------------------------------------------------ |
| **Horizontally** center block | `margin: 0 auto; width: Xpx;`                                            |
| **Flexbox** center (both)     | `display:flex; justify-content:center; align-items:center;`              |
| **Absolute** center           | `position:absolute; top:50%; left:50%; transform:translate(-50%, -50%);` |
| **Grid** center               | `display:grid; place-items:center;`                                      |
---

```
