# Module 5: Layout Systems

| **Layout System** | **Best For**                     | **Use Case Examples**                                      |
| ----------------- | -------------------------------- | ---------------------------------------------------------- |
| **Normal Flow**   | Simple stacking                  | Blog content, paragraphs, headings, default HTML rendering |
| **Float**         | Text wrapping                    | Wrapping text around images, badges inside paragraphs      |
| **Position**      | Overlays, tooltips, sticky items | Modal windows, tooltips, sticky headers, dropdowns         |
| **Flexbox**       | Rows/columns (1D layouts)        | Navigation bars, card lists, buttons in a row              |
| **Grid**          | Complex pages, 2D control        | Dashboards, magazine layouts, multi-column card grids      |
| **Multi-Column**  | Text content                     | Articles, blog posts, eBooks, side-by-side paragraphs      |


1. Flex Container Properties

First, make an element a flex container:
| **Property**      | **Values**                                                                                     | **Purpose**                       |
| ----------------- | ---------------------------------------------------------------------------------------------- | --------------------------------- |
| `display`         | `flex`, `inline-flex`                                                                          | Enable Flexbox                    |
| `flex-direction`  | `row`, `row-reverse`, `column`, `column-reverse`                                               | Main axis direction               |
| `flex-wrap`       | `nowrap`, `wrap`, `wrap-reverse`                                                               | Allow items to wrap               |
| `flex-flow`       | `row wrap`                                                                                     | Shorthand for direction + wrap    |
| `justify-content` | `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly`            | Align items on the **main axis**  |
| `align-items`     | `stretch`, `flex-start`, `center`, `flex-end`, `baseline`                                      | Align items on the **cross axis** |
| `align-content`   | `stretch`, `flex-start`, `center`, `flex-end`, `space-between`, `space-around`, `space-evenly` | Align multiple rows/columns       |
| `gap`             | `10px`, `1rem`                                                                                 | Space between items               |
| `row-gap`         | `10px`                                                                                         | Space between rows                |
| `column-gap`      | `20px`                                                                                         | Space between columns             |


2. Flex Item Properties

Applied to individual flex items.
| **Property**  | **Purpose**                         |
| ------------- | ----------------------------------- |
| `order`       | Change display order                |
| `flex-grow`   | Allow item to grow                  |
| `flex-shrink` | Allow item to shrink                |
| `flex-basis`  | Initial size                        |
| `flex`        | Shorthand (`grow shrink basis`)     |
| `align-self`  | Override `align-items` for one item |
