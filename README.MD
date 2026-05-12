# 📦 Module 1: Core Fundamentals

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

## 3. CSS Comments

| Purpose                    | Example                             |
| -------------------------- | ----------------------------------- |
| Explain complex code       | `/* Centering the content */`       |
| Section headings           | `/* === HEADER SECTION === */`      |
| Temporarily disable a rule | `/* color: red; */`                 |
| Notes for other developers | `/* TODO: Add responsive styles */` |

---

### 4. CSS File Structure

```
/css
│
├── base/         # Reset, typography, general styles
│   └── _reset.css
│   └── _typography.css
│
├── components/   # Buttons, cards, modals, etc.
│   └── _button.css
│   └── _modal.css
│
├── layout/       # Header, footer, grid, sidebar
│   └── _header.css
│   └── _footer.css
│
├── pages/        # Page-specific styles
│   └── _home.css
│   └── _about.css
│
├── themes/       # Light/dark themes, color schemes
│   └── _dark.css
│
├── utils/        # Mixins, helpers, variables
│   └── _variables.css
│   └── _helpers.css
│
└── main.css      # Master file importing everything

```

---

# 🎯 Module 2: Selectors (Basic to Advanced)

## 1. Basic Selectors

| **Selector** | **Description**                              | **Example**                       | **Usage**                                                               |
| ------------ | -------------------------------------------- | --------------------------------- | ----------------------------------------------------------------------- |
| `*`          | Universal – selects **all elements**         | `* { box-sizing: border-box; }`   | Used for global resets or applying base rules to every element          |
| `element`    | Type selector – selects by **tag name**      | `div { margin: 1rem; }`           | Used to style all elements of a specific type like all `p`, `ul`, etc.  |
| `.class`     | Selects elements by **class**                | `.highlight { color: red; }`      | Apply common styles to multiple elements sharing the same class         |
| `#id`        | Selects a **single unique** element by ID    | `#main { padding: 20px; }`        | Target one specific element, like a main container                      |
| `A B`        | **Descendant** – selects B inside A          | `div p { color: gray; }`          | Style elements deeply nested inside containers                          |
| `A > B`      | **Direct child** – only B directly inside A  | `ul > li { list-style: square; }` | Useful when children need different styles than nested descendants      |
| `A + B`      | **Adjacent sibling** – B right after A       | `h1 + p { font-style: italic; }`  | Style paragraphs immediately following a heading                        |
| `A ~ B`      | **General sibling** – all B siblings after A | `h2 ~ p { color: red; }`          | Target all later siblings of same parent, like a group of related notes |

---

## 2. Attribute Selectors

| **Selector**     | **Description**                                      | **Example**                                  | **Usage**                                               |                                  |                                           |
| ---------------- | ---------------------------------------------------- | -------------------------------------------- | ------------------------------------------------------- | -------------------------------- | ----------------------------------------- |
| `[attr]`         | Element with the attribute, any value                | `input[required] { border: red; }`           | Highlight required fields                               |                                  |                                           |
| `[attr="value"]` | Attribute must match exactly                         | `input[type="text"] { color: blue; }`        | Style specific input types                              |                                  |                                           |
| `[attr^="val"]`  | Attribute starts with value                          | `a[href^="https"] { color: green; }`         | Target secure links                                     |                                  |                                           |
| `[attr$="val"]`  | Attribute ends with value                            | `img[src$=".jpg"] { border-radius: 8px; }`   | Style images with certain file types                    |                                  |                                           |
| `[attr*="val"]`  | Attribute contains substring                         | `div[class*="error"] { background: pink; }`  | Style all error messages, regardless of full class name |                                  |                                           |
| `[attr~="val"]`  | Attribute is a space-separated list containing value | `[title~="sale"] { font-weight: bold; }`     | Highlight products tagged with specific words           |                                  |                                           |
| \`\[attr         | ="val"]\`                                            | Attribute equals `val` or starts with `val-` | \`\[lang                                                | ="en"] { font-style: italic; }\` | Style content based on language or locale |

---

## 3. Structural Pseudo-classes

| **Selector**           | **Description**                          | **Example**                                    | **Usage**                                                      |
| ---------------------- | ---------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------- |
| `:first-child`         | First child of its parent                | `li:first-child { font-weight: bold; }`        | Style the first item in a list                                 |
| `:last-child`          | Last child of its parent                 | `li:last-child { color: red; }`                | Style the last item in a navigation or group                   |
| `:nth-child(n)`        | Select nth child (1-based index)         | `li:nth-child(2) { color: green; }`            | Zebra-striping rows or selecting specific children             |
| `:nth-last-child(n)`   | Select nth child from end                | `li:nth-last-child(1) { font-style: italic; }` | Useful when you don’t know total count but want last few items |
| `:only-child`          | Matches if it’s the only child           | `p:only-child { border: 1px solid blue; }`     | Style unique items that appear alone                           |
| `:first-of-type`       | First of specific tag among siblings     | `p:first-of-type { color: purple; }`           | When the first heading or paragraph needs emphasis             |
| `:last-of-type`        | Last of specific tag among siblings      | `p:last-of-type { font-size: 1.2em; }`         | Style last instance of repeated tag like `li` or `p`           |
| `:nth-of-type(n)`      | Nth of a specific tag                    | `div:nth-of-type(2) { background: #eee; }`     | For layout structures or column grids                          |
| `:nth-last-of-type(n)` | Nth of type from the end                 | `div:nth-last-of-type(1) { color: brown; }`    | Target last few items of same type                             |
| `:only-of-type`        | Only one of that tag type among siblings | `span:only-of-type { color: orange; }`         | Prevent duplicate styles when there's only one tag present     |
| `:empty`               | No children or content                   | `div:empty { display: none; }`                 | Hide empty wrappers or placeholders                            |

---

## 4. UI State Pseudo-classes

| **Selector**     | **Description**                        | **Example**                                          | **Usage**                                        |
| ---------------- | -------------------------------------- | ---------------------------------------------------- | ------------------------------------------------ |
| `:hover`         | When mouse hovers                      | `a:hover { color: red; }`                            | Create hover effects on links or buttons         |
| `:focus`         | Element is focused                     | `input:focus { outline: 2px solid blue; }`           | Improve keyboard accessibility and styling       |
| `:focus-within`  | Parent element with focused child      | `form:focus-within { border: 2px solid green; }`     | Highlight entire forms when any input is focused |
| `:focus-visible` | Focused by keyboard (not mouse)        | `button:focus-visible { border: 2px dashed blue; }`  | Reduce focus outlines to only keyboard users     |
| `:active`        | When element is being clicked          | `button:active { background: orange; }`              | Add button press effect                          |
| `:checked`       | Input is checked                       | `input:checked + label { font-weight: bold; }`       | Style selected checkboxes/radio buttons          |
| `:enabled`       | Input is enabled (not disabled)        | `input:enabled { background: white; }`               | Style only working input fields                  |
| `:disabled`      | Input is disabled                      | `input:disabled { background: #eee; }`               | Show disabled inputs as inactive                 |
| `:required`      | Field is required                      | `input:required { border-left: 4px solid red; }`     | Visually indicate mandatory fields               |
| `:optional`      | Field is not required                  | `input:optional { border-left: 4px solid green; }`   | Differentiate optional fields                    |
| `:read-only`     | Cannot be edited                       | `input:read-only { background: #f8f8f8; }`           | Indicate locked input fields                     |
| `:read-write`    | Can be edited                          | `textarea:read-write { background: white; }`         | Highlight editable areas                         |
| `:indeterminate` | Checkbox neither checked nor unchecked | `input:indeterminate { outline: 2px dotted black; }` | For partial selection states (JS-based)          |
| `:default`       | Default form control                   | `button:default { font-weight: bold; }`              | Highlight primary submit buttons                 |

---

## 5. Logic Selectors

| **Selector**         | **Description**                               | **Example**                                   | **Usage**                                                     |
| -------------------- | --------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------- |
| `:not(sel)`          | Select elements **not** matching selector     | `li:not(.active) { color: gray; }`            | Exclude items from style rules                                |
| `:is(sel1, sel2)`    | Matches any of listed selectors (specificity) | `:is(h1, h2) { margin: 0; }`                  | Cleaner group targeting with full specificity                 |
| `:where(sel1, sel2)` | Like `:is`, but no specificity                | `:where(section, article) { padding: 1rem; }` | Use in resets or design systems to avoid conflicts            |
| `:has(sel)`          | Select parent with matching child (modern)    | `div:has(img) { border: 1px solid red; }`     | Conditional styling when children exist (Chrome support only) |

---

## 6. Pseudo-elements

| **Selector**     | **Description**                 | **Example**                                         | **Usage**                                              |
| ---------------- | ------------------------------- | --------------------------------------------------- | ------------------------------------------------------ |
| `::before`       | Insert content before element   | `p::before { content: "→ "; }`                      | Add icons, symbols, or annotations before real content |
| `::after`        | Insert content after element    | `p::after { content: " ✓"; }`                       | Add status indicators after text                       |
| `::first-line`   | Style first line of text        | `p::first-line { font-weight: bold; }`              | Create typographic effects in paragraphs               |
| `::first-letter` | Style first letter              | `p::first-letter { font-size: 150%; }`              | Create drop caps or stylized headlines                 |
| `::selection`    | Style user-selected text        | `::selection { background: yellow; }`               | Customize highlight color                              |
| `::placeholder`  | Style input placeholder text    | `input::placeholder { color: gray; }`               | Improve placeholder visibility                         |
| `::marker`       | Style bullets or list numbers   | `li::marker { color: red; font-size: 1.5em; }`      | Custom bullets for lists                               |
| `::backdrop`     | Fullscreen background in modals | `::backdrop { background-color: rgba(0,0,0,0.8); }` | Style behind dialogs or fullscreen popups              |
| `::cue`          | Style subtitles for media       | `::cue { color: white; }`                           | Apply themes to video captions                         |

---

## 7. Other Special Selectors

| **Selector**              | **Description**                                       | **Example**                          | **Usage**                                           |
| ------------------------- | ----------------------------------------------------- | ------------------------------------ | --------------------------------------------------- |
| `:lang(lang-code)`        | Match elements by language                            | `p:lang(en) { font-style: italic; }` | Apply styles based on language locale               |
| `:dir(ltr)` / `:dir(rtl)` | Match text direction (left-to-right or right-to-left) | `:dir(rtl) { text-align: right; }`   | RTL language support                                |
| `:root`                   | Targets root element (`<html>`)                       | `:root { --main-color: #333; }`      | Define CSS custom properties (variables) globally   |
| `:scope`                  | Current context in query selector or shadow DOM       | `:scope > h2 { font-weight: bold; }` | Used in scripts or scoped styling within components |

---

# 🎨 Module 3: Colors, Units, and Values

## 1. CSS Units Guide

- CSS units define length, size, and spacing for elements. They are categorized as:
  -✅ Absolute units – Fixed size, independent of screen
  -✅ Relative units – Scales based on parent or environment

### 1. 📦 Absolute Units

| Unit | Name       | Description                       | Example            |
| ---- | ---------- | --------------------------------- | ------------------ |
| `px` | Pixel      | 1 device pixel (common base unit) | `font-size: 16px;` |
| `pt` | Point      | 1/72 of 1 inch (used in print)    | `font-size: 12pt;` |
| `cm` | Centimeter | Rare, print-oriented              | `width: 5cm;`      |
| `mm` | Millimeter | Rare, print-oriented              | `height: 10mm;`    |
| `in` | Inch       | 1in = 96px = 2.54cm               | `width: 1in;`      |
| `pc` | Pica       | 1pc = 12pt                        | `font-size: 1pc;`  |

> 📝 Note: Absolute units are best for print or highly controlled layouts.

---

### 2. 📐 Relative Units

| Unit   | Name             | Description                                            | Example               |
| ------ | ---------------- | ------------------------------------------------------ | --------------------- |
| `%`    | Percent          | Relative to parent element (width, padding, etc.)      | `width: 50%;`         |
| `em`   | Element          | Relative to the **font-size of the parent**            | `padding: 2em;`       |
| `rem`  | Root Element     | Relative to the **root font-size** (usually 16px)      | `font-size: 1.5rem;`  |
| `vw`   | Viewport Width   | 1% of the viewport’s width                             | `width: 50vw;`        |
| `vh`   | Viewport Height  | 1% of the viewport’s height                            | `height: 100vh;`      |
| `vmin` | Viewport Minimum | 1% of the smaller of vw or vh                          | `font-size: 2vmin;`   |
| `vmax` | Viewport Maximum | 1% of the larger of vw or vh                           | `margin: 5vmax;`      |
| `ch`   | Character        | Width of the “0” character of the element's font       | `width: 30ch;`        |
| `ex`   | x-height         | Height of lowercase “x” of the element's font          | `line-height: 1.2ex;` |
| `lh`   | Line Height Unit | Relative to the current element’s computed line height | `margin-top: 2lh;`    |

> 💡 Common Use: Use rem for consistent typography, vw/vh for responsive layouts, and % for fluid designs.

---

### 3. 🛠️ Special Units (Function-based)

| Unit / Function   | Description                               | Example                              |
| ----------------- | ----------------------------------------- | ------------------------------------ |
| `calc()`          | Combine units and math                    | `width: calc(100% - 60px);`          |
| `clamp()`         | Clamp between min, ideal, and max sizes   | `font-size: clamp(1rem, 2vw, 2rem);` |
| `min()` / `max()` | Choose minimum or maximum of given values | `width: min(100%, 600px);`           |

---

### 4. Best Practice Quick Tips

| Goal                  | Best Unit          |
| --------------------- | ------------------ |
| Font size             | `rem` or `clamp()` |
| Button spacing        | `em`               |
| Full screen section   | `vh` / `vw`        |
| Responsive box width  | `%` or `vw`        |
| Fixed small icon size | `px`               |

---

# Module 4: The Box Model

## 1. What is the CSS Box Model?

| **Part**  | **Description**                                                  |
| --------- | ---------------------------------------------------------------- |
| `Content` | The actual content (text, image, etc.) inside the box.           |
| `Padding` | Space **inside** the box, around the content.                    |
| `Border`  | A line surrounding the padding and content.                      |
| `Margin`  | Space **outside** the box that separates it from other elements. |

```
+----------------------------+
|        Margin              |
|  +----------------------+  |
|  |      Border          |  |
|  |  +----------------+  |  |
|  |  |   Padding      |  |  |
|  |  |  +----------+  |  |  |
|  |  |  | Content  |  |  |  |
|  |  |  +----------+  |  |  |
|  |  +----------------+  |  |
|  +----------------------+  |
+----------------------------+

```

### 1.1 Box Model Properties

| **Property** | **Usage**                         | **Example**                |
| ------------ | --------------------------------- | -------------------------- |
| `width`      | Width of the content area         | `width: 300px;`            |
| `height`     | Height of the content area        | `height: 200px;`           |
| `padding`    | Space inside the element          | `padding: 10px;`           |
| `border`     | Thickness and style of the border | `border: 1px solid black;` |
| `margin`     | Space outside the element         | `margin: 20px;`            |

---

### 1.2 Box Sizing

| **Value**     | **Effect**                                                                               |
| ------------- | ---------------------------------------------------------------------------------------- |
| `content-box` | (Default) Width/height apply **only** to content. Padding and border **add extra size**. |
| `border-box`  | Width/height **include** padding and border. Recommended for layouts.                    |

---

### 1.2 Overflow

| **Property** | **Description**                  | **Example**           |
| ------------ | -------------------------------- | --------------------- |
| `overflow`   | Sets overflow for both axes      | `overflow: auto;`     |
| `overflow-x` | Sets overflow on horizontal axis | `overflow-x: scroll;` |
| `overflow-y` | Sets overflow on vertical axis   | `overflow-y: hidden;` |

---

| **Value** | **Behavior**                                        |
| --------- | --------------------------------------------------- |
| `visible` | Content spills outside (default)                    |
| `hidden`  | Overflow is clipped and not visible                 |
| `scroll`  | Always shows scrollbars even if not needed          |
| `auto`    | Shows scrollbars **only when** content is too large |

---

### 1.3 Outline

Outline is similar to border but does not take up space and is outside the element box.

| **Property**     | **Description**                       | **Example**                 |
| ---------------- | ------------------------------------- | --------------------------- |
| `outline`        | Sets width, style, and color          | `outline: 2px dashed blue;` |
| `outline-color`  | Sets color                            | `outline-color: red;`       |
| `outline-style`  | Sets style                            | `outline-style: dotted;`    |
| `outline-width`  | Sets thickness                        | `outline-width: 3px;`       |
| `outline-offset` | Sets space between border and outline | `outline-offset: 4px;`      |

--

# Module 5: Layout Systems

| **Layout System** | **Best For**                     | **Use Case Examples**                                      |
| ----------------- | -------------------------------- | ---------------------------------------------------------- |
| **Normal Flow**   | Simple stacking                  | Blog content, paragraphs, headings, default HTML rendering |
| **Float**         | Text wrapping                    | Wrapping text around images, badges inside paragraphs      |
| **Position**      | Overlays, tooltips, sticky items | Modal windows, tooltips, sticky headers, dropdowns         |
| **Flexbox**       | Rows/columns (1D layouts)        | Navigation bars, card lists, buttons in a row              |
| **Grid**          | Complex pages, 2D control        | Dashboards, magazine layouts, multi-column card grids      |
| **Multi-Column**  | Text content                     | Articles, blog posts, eBooks, side-by-side paragraphs      |

---

## 1. What is a Layout System?

A layout system in CSS determines how elements are arranged and positioned on a webpage.

### 1.1 Normal Document Flow (Default Layout Behavior)

| Type            | Behavior                                                               |
| --------------- | ---------------------------------------------------------------------- |
| **Block-level** | Stacks vertically, takes full width (e.g., `<div>`, `<p>`)             |
| **Inline**      | Flows horizontally inside block-level elements (e.g., `<span>`, `<a>`) |

## 2. Float Layout (Legacy, but still useful)

### What is it?

- Originally meant for wrapping text around images, developers started using it to build entire layouts before Flexbox and Grid.

#### 🔸 Properties:

| Property | Description                            |
| -------- | -------------------------------------- |
| `float`  | Moves an element to the left or right  |
| `clear`  | Prevents elements from wrapping around |

---

#### ❌ Problem Example (without clearfix):

```html
<div class="container">
  <div class="box1">Box 1</div>
  <div class="box2">Box 2</div>
</div>
```

```css
.container {
  background: #eee;
}

.box1,
.box2 {
  float: left;
  width: 50%;
  height: 100px;
}
```

> 💥 The .container has no height because both children are floated. You won't see its background color or borders.

- Because floated elements are removed from normal flow, so they can cause:
  - Parent height collapse
  - Next elements overlapping

### Solution

1. Manual Clearing

```
.clear-both { clear: both; }
```

2. Clearfix technique

```
::after { content: ""; display: table; clear: both; }
```

3. overflow: hidden;
   It works — but not always ideal.

```
.container {
 overflow: hidden;
}
```

below:

```
.container::after {
  content: "";
  display: table;
  clear: both;
}

Or use the utility class:
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}

And apply it like:
<div class="container clearfix">
  ...
</div>

```

---

## 3. Positioning (Precise Control in CSS)

- Positioning is key to layout control and creating interactive or layered interfaces.

### Why Learn Positioning?

- Place tooltips, modals, and dropdowns exactly where needed.
- Layer elements on top of each other (z-index).
- Create layouts that go beyond normal flow (header overlays, sticky banners, etc).

### 1. static (Default)

- Default position.
- No top/left/right/bottom offsets work here.
- Stays in normal document flow.

```
<div class="box static-box">Static Box</div>

```

```
.static-box {
  position: static;
  background: lightgray;
  padding: 10px;
}
```

> 🧠 You don’t need to set this unless resetting from another value.

### 3. relative

- Moves the element relative to its normal position.
- Still occupies its original space in flow.

```
<div class="box relative-box">Relative Box</div>

```

```
.relative-box {
  position: relative;
  top: 20px;
  left: 40px;
  background: lightblue;
}

```

> 🧠 Useful for positioning child elements (absolute inside relative).

### 3. absolute

- Removed from normal flow.
- Positioned relative to the nearest ancestor with position: relative|absolute|fixed|sticky.
- If no ancestor is positioned, falls back to the <html>.

```
<div class="container">
  Parent
  <div class="tooltip">Absolute Child</div>
</div>

```

```
.container {
  position: relative;
  width: 200px;
  height: 200px;
  background: lightgreen;
}

.tooltip {
  position: absolute;
  top: 10px;
  right: 10px;
  background: orange;
  padding: 5px;
}

```

### 4. fixed

- Fixed relative to viewport.
- Doesn’t move when you scroll.
- Great for sticky buttons or modals.

```
<div class="fixed-box">Fixed at Bottom</div>

```

```
.fixed-box {
  position: fixed;
  bottom: 10px;
  right: 10px;
  background: crimson;
  color: white;
  padding: 10px;
}

```

> 🧠 Always visible – perfect for “Back to Top” or “Help” buttons.

### 5. sticky

- Starts off as relative, then becomes fixed when scrolling.
- Useful for sticky headers.

```
<div class="sticky-header">I stick to the top!</div>

```

```
.sticky-header {
 position: sticky;
 top: 0;
 background: gold;
 padding: 10px;
 z-index: 100;
}

```

> 🧠 Parent container should have height and not be overflow: hidden.

### 6. Position Offsets: top, left, right, bottom

- Only work with:
  - relative
  - absolute
  - fixed
  - sticky

---

## 📦 Flexbox – One-Dimensional Layout

## 🔹 Container Properties

| **Property**      | **Values**                                                                          | **Description**                                        |
| ----------------- | ----------------------------------------------------------------------------------- | ------------------------------------------------------ |
| `display`         | `flex`, `inline-flex`                                                               | Defines a flex container                               |
| `flex-direction`  | `row`, `row-reverse`, `column`, `column-reverse`                                    | Direction of items in the main axis                    |
| `flex-wrap`       | `nowrap`, `wrap`, `wrap-reverse`                                                    | Controls whether items wrap to the next line           |
| `flex-flow`       | `<flex-direction> <flex-wrap>`                                                      | Shorthand for `flex-direction` + `flex-wrap`           |
| `justify-content` | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` | Aligns items along the **main axis**                   |
| `align-items`     | `stretch`, `flex-start`, `flex-end`, `center`, `baseline`                           | Aligns items along the **cross axis**                  |
| `align-content`   | `stretch`, `flex-start`, `flex-end`, `center`, `space-between`, `space-around`      | Aligns **wrapped lines** in the flex container         |
| `gap`             | Any length (`10px`, `1rem`)                                                         | Space between items (can use `row-gap` & `column-gap`) |

---

## 🔹 Item (Child) Properties

| **Property**  | **Values / Syntax**                  | **Description**                                              |
| ------------- | ------------------------------------ | ------------------------------------------------------------ |
| `order`       | `<integer>` (`0` default)            | Controls visual order of the item                            |
| `flex-grow`   | `<number>` (`0` default)             | Defines how much item **can grow** relative to others        |
| `flex-shrink` | `<number>` (`1` default)             | Defines how much item **can shrink** when space is tight     |
| `flex-basis`  | `<length>` / `auto` (`auto` default) | Sets **initial main size** of item before grow/shrink        |
| `flex`        | `<grow> <shrink> <basis>`            | Shorthand for grow, shrink, basis (e.g., `flex: 1 0 200px;`) |
| `align-self`  | Same as `align-items` values         | Overrides `align-items` for a specific item                  |

---

## 🔁 Flex Directions

| `flex-direction` | Main Axis    | Cross Axis   |
| ---------------- | ------------ | ------------ |
| `row`            | Horizontal → | Vertical ↓   |
| `row-reverse`    | Horizontal ← | Vertical ↓   |
| `column`         | Vertical ↓   | Horizontal → |
| `column-reverse` | Vertical ↑   | Horizontal → |

---

## ✨ `justify-content` Examples

| Value           | Description                                    |
| --------------- | ---------------------------------------------- |
| `flex-start`    | Items align to start of main axis              |
| `center`        | Items centered along main axis                 |
| `flex-end`      | Items align to end of main axis                |
| `space-between` | Equal spacing between items (edges flush)      |
| `space-around`  | Equal space around items (half space on edges) |
| `space-evenly`  | Equal space between and at edges               |

---

## ✨ `align-items` Examples

| Value        | Behavior on Cross Axis                           |
| ------------ | ------------------------------------------------ |
| `stretch`    | Items stretch to fill container height (default) |
| `flex-start` | Items align to start of cross axis               |
| `flex-end`   | Items align to end of cross axis                 |
| `center`     | Items are centered vertically (or horizontally)  |
| `baseline`   | Aligns text baselines of items                   |

---

## 🔤 Flex Shorthand Example

```css
.item {
  flex: 1 1 200px;
}
/* flex-grow: 1;
   flex-shrink: 1;
   flex-basis: 200px; */
```

---

## 1. Flex: Container Properties

### 1. display: flex vs display: inline-flex

| Property               | Container Type | Child Layout         | Example Use                      |
| ---------------------- | -------------- | -------------------- | -------------------------------- |
| `display: flex`        | Block-level    | Flexbox (row/column) | Full-width sections, layout rows |
| `display: inline-flex` | Inline-level   | Flexbox (row/column) | Buttons, icons inline with text  |

---

### 2. flex-direction

#### All 4 flex-direction Values

| Value            | Direction     | Main Axis  | Cross Axis |
| ---------------- | ------------- | ---------- | ---------- |
| `row`            | Left ➡️ Right | Horizontal | Vertical   |
| `row-reverse`    | Right ➡️ Left | Horizontal | Vertical   |
| `column`         | Top ⬇️ Bottom | Vertical   | Horizontal |
| `column-reverse` | Bottom ⬆️ Top | Vertical   | Horizontal |

---

### 3.flex-wrap: wrap;

| Value          | Description                            | Use When…                                      |
| -------------- | -------------------------------------- | ---------------------------------------------- |
| `nowrap`       | All items stay in one row/column       | You want a single-line layout                  |
| `wrap`         | Items wrap to next line (normal order) | You want a responsive, multiple-row layout     |
| `wrap-reverse` | Items wrap in reverse (bottom-up)      | Rare cases (special designs like chat bubbles) |

---

### 4. flex-flow

- ✅ flex-flow = flex-direction + flex-wrap

- It combines these two properties into one line.

```
flex-flow: <flex-direction> <flex-wrap>;

```

### 5. justify-content

| Value                  | Behavior                                                             |
| ---------------------- | -------------------------------------------------------------------- |
| `flex-start` (default) | Items align to the **start (left)**                                  |
| `flex-end`             | Items align to the **end (right)**                                   |
| `center`               | Items are **centered** horizontally                                  |
| `space-between`        | Items spread out, **first at start**, **last at end**, space between |
| `space-around`         | Items have **equal space around** them                               |
| `space-evenly`         | Items have **equal space between AND around**                        |
| `start` / `end`        | Logical directions (used with writing-mode / direction)              |
| `left` / `right`       | Physical directions (LTR / RTL layout support)                       |

---

Visual Summary

[flex-start] | 1 2 3
[center] | 1 2 3
[flex-end] | 1 2 3
[space-between] | 1 2 3
[space-around] | 1 2 3
[space-evenly] | 1 2 3

---

## 6. align-items

- align-items controls how flex items align on the cross axis (usually vertical, if flex-direction is row).

| Value        | Description                               | Use Case Example                  |
| ------------ | ----------------------------------------- | --------------------------------- |
| `stretch`    | Items stretch to fill container (default) | Equal height cards, boxes         |
| `flex-start` | Align items to top (start of cross axis)  | Top-aligned labels or inputs      |
| `flex-end`   | Align items to bottom (end of cross axis) | Bottom-aligned buttons            |
| `center`     | Center items vertically                   | Centered button rows, navbars     |
| `baseline`   | Align items by text line                  | Align text-heavy content properly |

---

## 7. align-content

| Value               | Description                         | Best Use Case                           |
| ------------------- | ----------------------------------- | --------------------------------------- |
| `flex-start`        | Rows aligned to the top             | Default row stacking                    |
| `flex-end`          | Rows aligned to the bottom          | Push rows to bottom                     |
| `center`            | Rows centered vertically            | Center-align all wrapped content        |
| `space-between`     | Rows equally spaced – top to bottom | Even distribution with no outer padding |
| `space-around`      | Equal space around each row         | Balanced look                           |
| `space-evenly`      | Equal space all over                | Fully balanced layout                   |
| `stretch` (default) | Rows expand to fill the height      | Auto-stretch layout (default behavior)  |

---

## 8. gap

| Property     | Description                             | Example             |
| ------------ | --------------------------------------- | ------------------- |
| `gap`        | Sets space between **rows and columns** | `gap: 10px 20px;`   |
| `row-gap`    | Sets space **between rows**             | `row-gap: 10px;`    |
| `column-gap` | Sets space **between columns**          | `column-gap: 20px;` |

---

## 🔹 2. Item (Child) Properties

| **Property**  | **Values / Syntax**                  | **Description**                                              |
| ------------- | ------------------------------------ | ------------------------------------------------------------ |
| `order`       | `<integer>` (`0` default)            | Controls visual order of the item                            |
| `flex-grow`   | `<number>` (`0` default)             | Defines how much item **can grow** relative to others        |
| `flex-shrink` | `<number>` (`1` default)             | Defines how much item **can shrink** when space is tight     |
| `flex-basis`  | `<length>` / `auto` (`auto` default) | Sets **initial main size** of item before grow/shrink        |
| `flex`        | `<grow> <shrink> <basis>`            | Shorthand for grow, shrink, basis (e.g., `flex: 1 0 200px;`) |
| `align-self`  | Same as `align-items` values         | Overrides `align-items` for a specific item                  |

---

These properties are applied to **individual flex items** inside a flex container. They control layout behavior like order, size, growth, shrinkage, and alignment.

---

| **Property**  | **Values / Syntax**                  | **Description**                                                                             |
| ------------- | ------------------------------------ | ------------------------------------------------------------------------------------------- |
| `order`       | `<integer>` (`0` default)            | Controls the **visual order** of the item inside the container. Lower values come first.    |
| `flex-grow`   | `<number>` (`0` default)             | Defines how much an item **can grow** relative to others **when extra space is available**. |
| `flex-shrink` | `<number>` (`1` default)             | Defines how much an item **can shrink** relative to others **when space is tight**.         |
| `flex-basis`  | `<length>` / `auto` (`auto` default) | Sets the **initial size** of the item **before** growing or shrinking.                      |
| `flex`        | `<grow> <shrink> <basis>`            | Shorthand for `flex-grow`, `flex-shrink`, and `flex-basis`. Example: `flex: 1 0 200px;`     |
| `align-self`  | Same as `align-items` values         | Allows you to **override vertical alignment** (cross-axis) for a single item.               |

---

## 🔹 `order`

**Description**: Controls the **display order** of flex items without changing HTML order.

```css
.item {
  order: 2;
}
```

- Lower `order` values appear first
- Items with the same `order` follow the HTML order

---

## 🔹 `flex-grow`

**Description**: Defines how much the item **grows** relative to others **when there is space**.

```css
.item {
  flex-grow: 1;
}
```

- `0` = don’t grow
- `1+` = grow relative to other items

**Example**:

- `flex-grow: 2;` → grows **twice as much** as `flex-grow: 1`

---

## 🔹 `flex-shrink`

**Description**: Defines how much the item **shrinks** when space is too small.

```css
.item {
  flex-shrink: 1;
}
```

- `0` = do not shrink
- Higher values shrink more compared to others

**Example**:

- `flex-shrink: 2;` → shrinks **twice as much** as `flex-shrink: 1`

---

## 🔹 `flex-basis`

**Description**: Sets the **starting size** before grow/shrink kicks in.

```css
.item {
  flex-basis: 150px;
}
```

- `auto` = use content size or width/height
- `0` = no base size; grow/shrink takes full control

---

## 🔹 `flex` (shorthand)

**Description**: Combines `flex-grow`, `flex-shrink`, and `flex-basis`.

```css
.item {
  flex: 1 0 200px;
}
```

- First: grow
- Second: shrink
- Third: basis

**Common shortcuts**:

- `flex: 1;` → `1 1 0` (common responsive layout)
- `flex: 0 0 auto;` → fixed-size item
- `flex: 1 1 200px;` → grow/shrink from 200px

---

## 🔹 `align-self`

**Description**: Overrides `align-items` **for one item** to control vertical alignment on the cross axis.

```css
.item {
  align-self: center;
}
```

**Values**:

- `auto` (default)
- `flex-start`
- `flex-end`
- `center`
- `baseline`
- `stretch`

**Use Case**:

- Align a single item differently than the rest.

---

# 📘 Module 6: CSS Specificity & Cascade

Very important for real-world CSS debugging.

| Topic                   | Description                           |
| ----------------------- | ------------------------------------- |
| Cascade                 | How CSS rules override each other     |
| Specificity             | Priority of selectors                 |
| Inheritance             | Some properties inherit automatically |
| `!important`            | Highest priority override             |
| Source Order            | Later rules override earlier ones     |
| Specificity Calculation | ID > Class > Element                  |

# 📘 Module 7: CSS Display System

You mentioned normal flow, but display itself needs deep coverage.

| Value          | Description                          |
| -------------- | ------------------------------------ |
| `block`        | Full-width element                   |
| `inline`       | Inline content                       |
| `inline-block` | Inline + size control                |
| `none`         | Hidden element                       |
| `contents`     | Removes wrapper box                  |
| `flow-root`    | Creates new block formatting context |

Also include:

Formatting Contexts
BFC (Block Formatting Context)
IFC (Inline Formatting Context)

# 📘 Module 8: CSS Sizing

Very important modern topic.
| Property | Description |
| ----------------- | -------------- |
| `min-width` | Minimum width |
| `max-width` | Maximum width |
| `min-height` | Minimum height |
| `max-height` | Maximum height |
| `aspect-ratio` | Maintain ratio |
| `object-fit` | Image fitting |
| `object-position` | Position media |

# 📘 Module 9: CSS Typography

You only touched font-size indirectly.

Need full typography section.

| Topic             |
| ----------------- |
| `font-family`     |
| `font-size`       |
| `font-weight`     |
| `font-style`      |
| `line-height`     |
| `letter-spacing`  |
| `word-spacing`    |
| `text-align`      |
| `text-transform`  |
| `text-decoration` |
| `text-shadow`     |
| `white-space`     |
| `overflow-wrap`   |
| `word-break`      |
| `writing-mode`    |
| `@font-face`      |
| Web fonts         |

# 📘 Module 10: Backgrounds & Borders

Missing almost completely.

| Topic                   |
| ----------------------- |
| `background-color`      |
| `background-image`      |
| `background-size`       |
| `background-position`   |
| `background-repeat`     |
| `background-attachment` |
| Gradients               |
| Multiple backgrounds    |
| `border-radius`         |
| `border-image`          |

# 📘 Module 11: CSS Colors Deep Dive

You mentioned units but not full color systems.

| Topic                  |
| ---------------------- |
| Named colors           |
| HEX                    |
| RGB                    |
| RGBA                   |
| HSL                    |
| HSLA                   |
| `currentColor`         |
| Opacity                |
| Modern color functions |
| `color-mix()`          |

# 📘 Module 12: Shadows & Effects

| Property          |
| ----------------- |
| `box-shadow`      |
| `text-shadow`     |
| `filter`          |
| `backdrop-filter` |
| `opacity`         |
| `mix-blend-mode`  |

# 📘 Module 13: CSS Transitions

Critical modern topic.
| Topic |
| ---------------------------- |
| `transition-property` |
| `transition-duration` |
| `transition-delay` |
| `transition-timing-function` |
| easing functions |

# 📘 Module 14: CSS Transforms

| Transform          |
| ------------------ |
| `translate()`      |
| `scale()`          |
| `rotate()`         |
| `skew()`           |
| `transform-origin` |
| 3D transforms      |

# 📘 Module 15: CSS Animations

Very important professional topic.

| Topic                       |
| --------------------------- |
| `@keyframes`                |
| `animation-name`            |
| `animation-duration`        |
| `animation-delay`           |
| `animation-iteration-count` |
| `animation-direction`       |
| `animation-fill-mode`       |
| `animation-play-state`      |

# 📘 Module 16: CSS Grid (FULL)

You only listed Grid in layout systems.

You need a complete dedicated Grid module.
| Topic |
| ----------------------- |
| Grid container |
| Grid items |
| `grid-template-columns` |
| `grid-template-rows` |
| `grid-template-areas` |
| `repeat()` |
| `minmax()` |
| `fr` unit |
| implicit/explicit grid |
| auto-fit / auto-fill |
| alignment |
| grid shorthand |

# 📘 Module 17: Responsive Design

Very important.

| Topic                 |
| --------------------- |
| Media queries         |
| Breakpoints           |
| Mobile-first          |
| Container queries     |
| Responsive typography |
| Responsive images     |

# 📘 Module 18: CSS Variables (Custom Properties)

Modern CSS essential.

| Topic           |
| --------------- |
| Variable scope  |
| fallback values |
| dynamic theming |
| dark mode       |

# 📘 Module 19: Modern CSS Functions

| Function  |
| --------- |
| `var()`   |
| `calc()`  |
| `min()`   |
| `max()`   |
| `clamp()` |
| `attr()`  |

# 📘 Module 20: Advanced Selectors

You already covered many.

But still missing:

| Selector        |
| --------------- |
| `:target`       |
| `:visited`      |
| `:link`         |
| `:any-link`     |
| `:defined`      |
| `:fullscreen`   |
| `:popover-open` |
| `:autofill`     |

# 📘 Module 21: CSS Architecture

Professional-level topic.

| Methodology       |
| ----------------- |
| BEM               |
| OOCSS             |
| SMACSS            |
| ITCSS             |
| Utility-first CSS |

# 📘 Module 22: CSS Methodologies & Scalability

| Topic              |
| ------------------ |
| Design systems     |
| Tokens             |
| Component styling  |
| Reusable utilities |
| Atomic CSS         |

# 📘 Module 23: Accessibility (A11Y)

Very important professional skill.

| Topic                         |
| ----------------------------- |
| Focus states                  |
| Reduced motion                |
| Contrast                      |
| Keyboard navigation           |
| Accessible hover/focus        |
| Screen reader friendly hiding |

# 📘 Module 24: CSS Performance Optimization

Advanced topic.

| Topic                  |
| ---------------------- |
| Repaint                |
| Reflow                 |
| GPU acceleration       |
| Efficient selectors    |
| Avoid layout thrashing |
| Critical CSS           |

# 📘 Module 25: Modern CSS Features

| Topic                |
| -------------------- |
| Container Queries    |
| Nesting              |
| Cascade Layers       |
| Subgrid              |
| Scroll Snap          |
| Anchor Positioning   |
| View Transitions API |

# 📘 Module 26: Pseudo-elements Missing

| Selector                 |
| ------------------------ |
| `::file-selector-button` |
| `::part()`               |
| `::slotted()`            |
| `::target-text`          |
| `::spelling-error`       |
| `::grammar-error`        |

# 📘 Module 27: Tables Styling

| Topic             |
| ----------------- |
| `border-collapse` |
| `border-spacing`  |
| `caption-side`    |
| `table-layout`    |
| zebra striping    |

# 📘 Module 28: Lists Styling

| Topic                 |
| --------------------- |
| `list-style-type`     |
| `list-style-position` |
| `list-style-image`    |

# 📘 Module 29: Printing Styles

@media print {
}

# 📘 Module 30: CSS Debugging Tools

| Topic               |
| ------------------- |
| DevTools            |
| Inspect element     |
| Box model inspector |
| Flex/Grid overlays  |
| Computed styles     |

# 📘 Module 31: CSS Logical Properties

Modern responsive + multilingual CSS uses this heavily.

Why important?

Replaces top/right/left/bottom with writing-direction aware properties.

| Physical Property | Logical Equivalent   |
| ----------------- | -------------------- |
| margin-left       | margin-inline-start  |
| margin-right      | margin-inline-end    |
| padding-left      | padding-inline-start |
| width             | inline-size          |
| height            | block-size           |

Example
```
.box {
  margin-inline: 20px;
  padding-block: 10px;
}
```
👉 Essential for RTL (Arabic, Malayalam, etc.) + responsive design

# 📘 Module 32: Cascade Layers (@layer)

You already mentioned cascade, but not layers.

Why important?

Controls CSS priority in a structured way.

```
@layer base, components, utilities;

@layer base {
  body { margin: 0; }
}

@layer components {
  .btn { background: blue; }
}
```
👉 Solves specificity wars in large projects


# 📘 Module 33: Feature Queries (@supports)

Why important?

Checks if a CSS feature is supported.
```
@supports (display: grid) {
  .container {
    display: grid;
  }
}
```
👉 Used in production for fallback systems

# 📘 Module 34: Container Queries ⭐ Modern Responsive CSS

You covered media queries, but this is next-level.

```
@container (max-width: 500px) {
  .card {
    font-size: 14px;
  }
}
```
👉 Responsive based on parent, not screen

# 📘 Module 35: CSS Containment (contain)
Why important?

Performance optimization at rendering level.

```
.box {
  contain: layout paint;
}
```

| Value  | Meaning            |
| ------ | ------------------ |
| layout | isolates layout    |
| paint  | isolates repaint   |
| size   | fixes size context |


# 📘 Module 36: Stacking Context Deep Dive (z-index Mastery)

You mentioned z-index, but missing full model.

Key idea:

Not just numbers — stacking context rules matter

Creates new context:

position + z-index
transform
opacity < 1
filter
isolation

👉 Critical for modals, dropdown bugs

# 📘 Module 37: CSS Scroll Features (Modern UX)
Missing areas:

1. Scroll Snap
```
.container {
  scroll-snap-type: x mandatory;
}

.item {
  scroll-snap-align: center;
}
```

2. Scroll Behavior
```
html {
  scroll-behavior: smooth;
}
```

# 📘 Module 38: Scroll-driven Animations (Very Modern)

```
animation-timeline: scroll();
```
👉 Used in modern websites for:

progress bars
parallax effects
scroll reveals

# 📘 Module 39: CSS Houdini (Advanced / Future CSS)
Why important?

Lets you extend CSS engine.

Paint API
Layout API
Properties API
```
CSS.paintWorklet.addModule('paint.js');
```
👉 Used in advanced design systems

# 📘 Module 40: CSS @property (Typed Variables)

```
@property --my-color {
  syntax: "<color>";
  inherits: false;
  initial-value: red;
}
```
👉 Enables animatable CSS variables

# 📘 Module 41: Modern Media Features (Important for UI apps)

| Feature                |
| ---------------------- |
| prefers-color-scheme   |
| prefers-reduced-motion |
| prefers-contrast       |
| hover                  |
| pointer                |
| orientation            |

```
@media (prefers-reduced-motion: reduce) {
  * {
    animation: none;
  }
}
```

# 📘 Module 42: CSS Functions (More Advanced Coverage)

You already listed basics — missing:

| Function           | Use                      |
| ------------------ | ------------------------ |
| `color-contrast()` | accessibility            |
| `image-set()`      | responsive images        |
| `env()`            | safe-area (mobile notch) |
| `attr()` advanced  | dynamic content          |


# 📘 Module 43: CSS Isolation & Interaction Control

| Property         | Use                    |
| ---------------- | ---------------------- |
| `isolation`      | stacking isolation     |
| `pointer-events` | disable clicks         |
| `user-select`    | text selection control |
| `touch-action`   | mobile gesture control |


# 📘 Module 44: Modern Layout Techniques (Bonus)

You already have Grid/Flex, but missing:
  - Subgrid (partial but important)
  - Masonry layout (experimental)
  - Aspect-ratio-driven layouts
  - Intrinsic sizing (min-content, max-content, fit-content)

# 📘 Module 45: CSS Architecture Deep Advanced

You included BEM etc — but missing:
  - ITCSS deep layering model
  - Atomic design systems
  - CSS-in-JS comparison (conceptual)
  - Utility-first systems (Tailwind philosophy)
  - Design token architecture scaling