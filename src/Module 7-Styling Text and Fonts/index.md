# Module 7: Styling Text and Fonts

| **Property / Topic**    | **Syntax / Values**                               | **Description**                                       | **Example**                                                  |
| ----------------------- | ------------------------------------------------- | ----------------------------------------------------- | ------------------------------------------------------------ |
| `font-family`           | `"Roboto", "Arial", sans-serif`                   | Sets the typeface (font). Always give fallback fonts. | `font-family: "Poppins", sans-serif;`                        |
| `font-size`             | `<length>` \| `<keyword>`                         | Controls the size of the text.                        | `font-size: 18px;`                                           |
| `font-weight`           | `normal`, `bold`, `100–900`                       | Thickness of characters.                              | `font-weight: 600;`                                          |
| `font-style`            | `normal`, `italic`, `oblique`                     | Slanted or normal style.                              | `font-style: italic;`                                        |
| `font-variant`          | `small-caps`, etc.                                | Displays small capital letters.                       | `font-variant: small-caps;`                                  |
| `font`                  | _shorthand_                                       | Sets multiple font properties in one line.            | `font: italic small-caps 700 16px/1.2 "Roboto", sans-serif;` |
| `text-align`            | `left`, `right`, `center`, `justify`              | Horizontal alignment of text in block-level elements. | `text-align: center;`                                        |
| `text-transform`        | `uppercase`, `lowercase`, `capitalize`            | Changes the case of text.                             | `text-transform: uppercase;`                                 |
| `text-decoration`       | `underline`, `overline`, `line-through`           | Adds decorative lines to text.                        | `text-decoration: underline;`                                |
| `text-decoration-color` | `<color>`                                         | Color of the decoration.                              | `text-decoration-color: red;`                                |
| `text-decoration-style` | `solid`, `double`, `dotted`, `dashed`, `wavy`     | Type of decorative line.                              | `text-decoration-style: wavy;`                               |
| `letter-spacing`        | `<length>`                                        | Space between characters.                             | `letter-spacing: 2px;`                                       |
| `word-spacing`          | `<length>`                                        | Space between words.                                  | `word-spacing: 6px;`                                         |
| `line-height`           | `<number>` \| `<length>` \| `<%>`                 | Distance between baselines of 2 lines of text.        | `line-height: 1.5;`                                          |
| `text-indent`           | `<length>`                                        | Indents the first line of text in a block.            | `text-indent: 50px;`                                         |
| `text-shadow`           | `h-offset v-offset blur color`                    | Adds drop shadow to text.                             | `text-shadow: 2px 2px 4px rgba(0,0,0,0.4);`                  |
| `white-space`           | `normal`, `nowrap`, `pre`, `pre-wrap`, `pre-line` | How white space is handled inside an element.         | `white-space: nowrap;`                                       |
| `overflow-wrap`         | `normal`, `break-word`                            | Forces long words to break and wrap onto next line.   | `overflow-wrap: break-word;`                                 |
| `direction`             | `ltr`, `rtl`                                      | Text direction (left-to-right or right-to-left).      | `direction: rtl;`                                            |
| `unicode-bidi`          | `normal`, `bidi-override`                         | Used with `direction` for complex scripts.            | —                                                            |
| `writing-mode`          | `horizontal-tb`, `vertical-rl`, `vertical-lr`     | Direction in which lines of text are stacked.         | `writing-mode: vertical-rl;`                                 |

---

## ✅ Google Fonts

> Used to import fonts from Google’s free online library.

Step 1 – Import in <head>

```
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">

```

Step 2 – Use in CSS

```
body {
  font-family: "Poppins", sans-serif;
}

```

## ✅ Web-Safe Fonts (Common Built-In System Fonts)

These fonts are available on almost all devices — safer fallbacks:
| Category | Fonts |
| ----------------- | ------------------------------------------------------- |
| Serif | Times New Roman, Georgia, Garamond, Baskerville |
| Sans-Serif | Arial, Helvetica, Verdana, Tahoma, Trebuchet MS |
| Monospace | Courier New, Consolas, Lucida Console, Monaco |
| Cursive / Fantasy | Comic Sans MS 🙈, Brush Script MT, Papyrus, Copperplate |

Usage Example:

```
font-family: "Helvetica", "Arial", sans-serif;

```
