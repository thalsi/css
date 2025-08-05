### 🕹️ Module 11: Transitions, Transforms & Animations

---

## 🚦 1. Transitions

Transitions allow CSS properties to change smoothly over a duration instead of instantly.

| Property                     | Description                            | Example Value                   |
| ---------------------------- | -------------------------------------- | ------------------------------- |
| `transition-property`        | Which property to animate              | `width`, `opacity`, `all`       |
| `transition-duration`        | How long the transition runs           | `0.5s`, `300ms`                 |
| `transition-timing-function` | Easing (speed curve) of the transition | `ease`, `linear`, `ease-in-out` |
| `transition-delay`           | Delay before the transition starts     | `0.3s`                          |
| `transition` (shorthand)     | Combines all four of the above         | `width 0.5s ease 0.2s`          |

| Function                        | What it does                   | Example                 |
| ------------------------------- | ------------------------------ | ----------------------- |
| `translate(x, y)`               | Move horizontally/vertically   | `translate(50px, 20px)` |
| `translateX()` / `translateY()` | Move on one axis               | `translateY(40px)`      |
| `scale(x, y)`                   | Resize                         | `scale(1.5, 1.5)`       |
| `scaleX()` / `scaleY()`         | Stretch in one direction       | `scaleX(2)`             |
| `rotate(angle)`                 | Rotate clockwise               | `rotate(45deg)`         |
| `skew(x-angle, y-angle)`        | Slant/tilt                     | `skew(20deg, 10deg)`    |
| `matrix()`                      | Combine multiple 2D transforms | Advanced usage          |

---

## 2. Transforms

Transforms visually manipulate an element in 2D or 3D space (move, rotate, scale).

### 🔧 2D Transform Functions

| Function                        | What it does                   | Example                 |
| ------------------------------- | ------------------------------ | ----------------------- |
| `translate(x, y)`               | Move horizontally/vertically   | `translate(50px, 20px)` |
| `translateX()` / `translateY()` | Move on one axis               | `translateY(40px)`      |
| `scale(x, y)`                   | Resize                         | `scale(1.5, 1.5)`       |
| `scaleX()` / `scaleY()`         | Stretch in one direction       | `scaleX(2)`             |
| `rotate(angle)`                 | Rotate clockwise               | `rotate(45deg)`         |
| `skew(x-angle, y-angle)`        | Slant/tilt                     | `skew(20deg, 10deg)`    |
| `matrix()`                      | Combine multiple 2D transforms | Advanced usage          |

---

### 🔧 3D Transform Functions

| Function        | Example              |
| --------------- | -------------------- |
| `rotateX()`     | `rotateX(45deg)`     |
| `rotateY()`     | `rotateY(60deg)`     |
| `translateZ()`  | `translateZ(50px)`   |
| `perspective()` | `perspective(500px)` |

---

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
