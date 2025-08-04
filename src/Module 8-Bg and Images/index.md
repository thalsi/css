# 🖼️ Module 8: Backgrounds and Images (Table Format)

## ✅ 1. Background Color

| Property           | Values                                     | Description                             | Example                        |
| ------------------ | ------------------------------------------ | --------------------------------------- | ------------------------------ |
| `background-color` | `red`, `#fff`, `rgb(0,0,0)`, `transparent` | Sets the background color of an element | `background-color: lightblue;` |

---

## ✅ 2. Background Image Properties

| Property                | Values / Syntax                               | Description                                   | Example                               |
| ----------------------- | --------------------------------------------- | --------------------------------------------- | ------------------------------------- |
| `background-image`      | `url("image.jpg")`                            | Sets one or more background images            | `background-image: url('bg.jpg');`    |
| `background-repeat`     | `repeat`, `no-repeat`, `repeat-x`, `repeat-y` | Defines if/how background image is repeated   | `background-repeat: no-repeat;`       |
| `background-size`       | `auto`, `cover`, `contain`, `100px 200px`     | Specifies background image size               | `background-size: cover;`             |
| `background-position`   | `top`, `center`, `left top`, `50% 50%`        | Sets the position of the background image     | `background-position: center center;` |
| `background-attachment` | `scroll`, `fixed`, `local`                    | Controls whether background scrolls with page | `background-attachment: fixed;`       |

---

## ✅ 3. Gradient Backgrounds

| Type            | Syntax Example                                 | Description                                  |
| --------------- | ---------------------------------------------- | -------------------------------------------- |
| Linear Gradient | `linear-gradient(to right, red, blue)`         | Gradient that transitions in a straight line |
| Radial Gradient | `radial-gradient(circle, yellow, green)`       | Gradient from a central point outward        |
| Conic Gradient  | `conic-gradient(from 0deg, red, yellow, blue)` | Gradient around a central point (modern)     |

---

## 🧪 Bonus: Direction Syntax for `linear-gradient`

| Direction Value | Meaning                 | Example                                   |
| --------------- | ----------------------- | ----------------------------------------- |
| `to right`      | Left → Right            | `linear-gradient(to right, red, blue)`    |
| `to top left`   | Bottom Right → Top Left | `linear-gradient(to top left, red, blue)` |
| `45deg`         | Clockwise from top      | `linear-gradient(45deg, red, blue)`       |

---

## ✅ 4. `object-fit` and `object-position`

| Property          | Values                                                | Description                                                | Example                        |
| ----------------- | ----------------------------------------------------- | ---------------------------------------------------------- | ------------------------------ |
| `object-fit`      | `fill`, `contain`, `cover`, `none`, `scale-down`      | Defines how replaced elements (like `<img>`) fit container | `object-fit: cover;`           |
| `object-position` | `top`, `center`, `bottom`, `left`, `right`, `50% 50%` | Aligns image inside container                              | `object-position: center top;` |

---

## 📌 object-fit: Visual Behaviors

| Value        | Description                                                                        | Stretch / Crop?                   |
| ------------ | ---------------------------------------------------------------------------------- | --------------------------------- |
| `fill`       | Fills the container entirely, **ignoring aspect ratio** (image may look stretched) | ✅ Stretch                        |
| `contain`    | Fits the image inside the box **without cropping**, maintaining aspect ratio       | ❌ No crop, may leave empty space |
| `cover`      | Fills the box while maintaining aspect ratio — may **crop** the image              | ✅ Crop edges                     |
| `none`       | Keeps image's original size — **no resize or crop**                                | ❌ No crop, no resize             |
| `scale-down` | Uses the smaller of `none` or `contain` — **shrinks if needed** but doesn't grow   | ❌ Only shrink                    |

---

## ✅ Shorthand Property: `background`

| Syntax                                                     | Description                                            |
| ---------------------------------------------------------- | ------------------------------------------------------ |
| `background: url("img.jpg") no-repeat center/cover fixed;` | Combines image, repeat, position, size, and attachment |

---

## ✅ Summary Table

| Feature              | Related Properties                                                                                         |
| -------------------- | ---------------------------------------------------------------------------------------------------------- |
| Background Color     | `background-color`                                                                                         |
| Background Image     | `background-image`, `background-repeat`, `background-size`, `background-position`, `background-attachment` |
| Gradient Backgrounds | `linear-gradient`, `radial-gradient`, `conic-gradient`                                                     |
| Media Fitting        | `object-fit`, `object-position`                                                                            |
| Shorthand            | `background`                                                                                               |
