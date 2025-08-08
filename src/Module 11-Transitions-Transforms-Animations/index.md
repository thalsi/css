### 🕹️ Module 11: Transitions, Transforms & Animations

---

## 🚦 1. Transitions

Transitions allow CSS properties to change smoothly over a duration instead of instantly.

| Property                     | Description                                                                                                                    | Example Value                   |
| ---------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------- |
| `transition-property`        | Which property to animate                                                                                                      | `width`, `opacity`, `all`       |
| `transition-duration`        | How long the transition runs                                                                                                   | `0.5s`, `300ms`                 |
| `transition-timing-function` | Easing (speed curve) of the transition                                                                                         | `ease`, `linear`, `ease-in-out` |
| `transition-delay`           | Delay before the transition starts                                                                                             | `0.3s`                          |
| `transition` (shorthand)     | Combines all four of the above -> transition: property duration timing-function delay,property duration timing-function delay; | `width 0.5s ease 0.2s`          |

---

## 2. Transforms

Transforms visually manipulate an element in 2D or 3D space (move, rotate, scale).

### 🔧 2D Transform Functions

| Function                        | What it does                    | Example                                                                               |
| ------------------------------- | ------------------------------- | ------------------------------------------------------------------------------------- |
| `translate(x, y)`               | Move horizontally/vertically    | `transform: translate(50px, 20px)`                                                    |
| `translateX()` / `translateY()` | Move on one axis                | `transform: translateY(40px)`                                                         |
| `scale(x, y)`                   | Resize (1 defult)               | `transform: scale(1.5, 1.5)`                                                          |
| `scaleX()` / `scaleY()`         | Stretch in one direction        | `transform: scaleX(2)`                                                                |
| `rotate(angle)`                 | Rotate clockwise (deg,rad,turn) | `transform: rotate(45deg)` deg → degrees, rad → radians, turn → full circle = 1turn   |
| `skew(x-angle, y-angle)`        | Slant/tilt                      | `transform: skew(20deg, 10deg)`                                                       |
| `matrix()`                      | Combine multiple 2D transforms  | `transform: matrix(scaleX(), skewY(), skewX(), scaleY(), translateX(), translateY())` |

---

### 🔧 3D Transform Functions

```
transform: Functions;
```

| Function         | Description                                                              | Example                         |
| ---------------- | ------------------------------------------------------------------------ | ------------------------------- |
| `rotateX()`      | Rotates around **X-axis** (horizontal flip)                              | `transform: rotateX(45deg);`    |
| `rotateY()`      | Rotates around **Y-axis** (vertical flip)                                | `transform: rotateY(45deg);`    |
| `rotateZ()`      | Rotates around **Z-axis** (like normal rotate)                           | `transform: rotateZ(45deg);`    |
| `translateZ()`   | Moves element **closer/farther** (depth)                                 | `transform: translateZ(100px);` |
| `scaleZ()`       | Scales element in **depth** .Not visually impactful without perspective. | `transform: scaleZ(2);`         |
| `scale3d(x,y,z)` | Scales element on all 3 axes independently                               | `transform: scale3d(1, 1, 2);`  |
| `perspective()`  | Adds camera **depth effect**                                             | `perspective: 800px;`           |

---

1. perspective

What it does:

- It controls how deep or flat the 3D effect looks.
- Adds a camera view to the scene (like looking from a distance).

Applied on: Parent

```
.parent {
  perspective: 800px; /* 👈 Controls the 3D view depth */
}
```

Example:

```html
<div class="parent">
  <div class="box">3D</div>
</div>
```

```css
.parent {
  perspective: 800px;
}

.box {
  transform: rotateX(45deg);
}
```

Real-Life Analogy:

- perspective = your camera lens
- Smaller value (e.g., 200px) = more zoomed in, strong 3D
- Larger value (e.g., 1000px) = farther away, softer 3D

---

2.  transform-style

---

What it does:

- Decides how child elements behave in 3D.
- Enables child elements to keep their own 3D depth.

```Value:
transform-style: preserve-3d;

```

```Applied on: Parent
.parent {
  transform-style: preserve-3d;
}

```

> Without preserve-3d: Children will look flattened (merged into 2D).

## 🎞️ 3. Animations

Animations use @keyframes to describe multiple steps of change over time.

| Property                    | Description                                      |
| --------------------------- | ------------------------------------------------ |
| `@keyframes`                | Defines animation steps (from…to…)               |
| `animation-name`            | The keyframes block to use                       |
| `animation-duration`        | How long one animation cycle runs                |
| `animation-timing-function` | Speed curve                                      |
| `animation-delay`           | Wait time before animation starts                |
| `animation-iteration-count` | Number of times to repeat (`1`, `infinite`)      |
| `animation-direction`       | Direction (`normal`, `reverse`, `alternate`)     |
| `animation-fill-mode`       | Apply styles before/after animation (`forwards`) |
| `animation` (shorthand)     | Combines all in one                              |

---

✅ Quick Comparison

| Feature    | Trigger Needed                        | Repeats?     | Best Use For…               |
| ---------- | ------------------------------------- | ------------ | --------------------------- |
| Transition | State change (hover, click)           | No           | Simple UI property changes  |
| Transform  | Immediate or combined with transition | N/A          | Moving/rotating elements    |
| Animation  | Automatic                             | Yes (if set) | Complex motion like loaders |

---

---

---

# 🚦 1. Transitions

## 1. transition-property

```
transition-property: property-name | none | all | property-name, property-name;

```

---

## 2. transition-property

```
transition-duration: time;

```

- Accepts seconds (s) or milliseconds (ms)
- Default value is 0s (meaning no animation)
- You can set multiple durations for multiple properties (comma-separated)

---

## 3. transition-timing-function

```
transition-timing-function: ease;

```

✅ Common values:
| Value | Description | Behavior |
| ----------------------- | --------------------------------------------- | ------------------------- |
| `ease` | Starts slow → speeds up → ends slow (default) | Smooth and natural |
| `linear` | Same speed from start to end | Constant speed |
| `ease-in` | Starts slow → then speeds up | Accelerating |
| `ease-out` | Starts fast → then slows down | Decelerating |
| `ease-in-out` | Starts slow → speeds up → slows down | Slow → fast → slow |
| `cubic-bezier(n,n,n,n)` | Custom control curve | Fully customizable timing |

---

### 4 .transition-delay

```
transition-delay: time;

```

- Accepts seconds (s) or milliseconds (ms)
- Can also accept multiple comma-separated delays (if animating multiple properties)

```
  transition-delay: 0s, 2s;
```

### 5. transition (Shorthand )

```
transition: <property> <duration> <timing-function> <delay>;

```

1️⃣ Basic:

```
transition: width 0.5s;

```

2️⃣ Full format:

```
transition: background-color 2s linear 1s;

```

3️⃣ Multiple transitions:

```
transition: width 1s ease, height 2s ease-in 0.5s;

```

# 🎨 CSS Animation Properties – Full Guide

CSS animations let you create smooth, multi-step style changes over time.  
They are defined with `@keyframes` and applied using animation properties.

---

## 1. `@keyframes`

Defines the animation steps at various points in time.

```css
@keyframes fadeIn {
  from {
    opacity: 0;
  } /* Start transparent */
  to {
    opacity: 1;
  } /* End fully visible */
}
```

## 2. animation-name

Links the element to the @keyframes.

```
.box {
  animation-name: fadeIn; /* Uses the @keyframes fadeIn */
}

```

## 3. animation-duration

Specifies how long one animation cycle lasts.

```
.box {
  animation-name: fadeIn;
  animation-duration: 2s; /* 2 seconds per cycle */
}
```

## 4. animation-timing-function

Defines the speed curve of the animation.

Common values:

- linear → constant speed
- ease → starts slow, speeds up, ends slow (default)
- ease-in → starts slow
- ease-out → ends slow
- ease-in-out → slow → fast → slow
- cubic-bezier(x1, y1, x2, y2) → custom curve

```
.box {
  animation: fadeIn 2s ease-in;
}

```

## 5. animation-delay

Adds a wait time before the animation starts.

```
.box {
  animation: fadeIn 2s ease-in 1s; /* Starts after 1 second */
}

```

## 6. animation-iteration-count

Number of times the animation repeats.

Values:

- Number (1, 2, 5)
- infinite → loops forever

```
.box {
  animation: fadeIn 2s linear infinite;
}

```

## 7. animation-direction

Controls the playback direction.

Values:

- normal → plays forward (default)
- reverse → plays backward
- alternate → forward then backward
- alternate-reverse → backward then forward

```
@keyframes slide {
  from { transform: translateX(0); }
  to   { transform: translateX(100px); }
}

.box {
  animation: slide 2s linear infinite alternate;
}

```

## 8. animation-fill-mode

Defines what styles apply before/after the animation.

Values:

- none → no styles retained (default)
- forwards → keeps final keyframe styles
- backwards → applies first keyframe styles during delay
- both → applies both forwards and backwards

```
.box {
  animation: fadeIn 2s ease forwards;
}

```

9. animation (shorthand)
   Combines all animation properties into one line.

Order:

```
animation: name duration timing-function delay iteration-count direction fill-mode;

```

Example:

```
.box {
  animation: fadeIn 2s ease-in 1s infinite alternate forwards;
}

```
