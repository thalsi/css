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