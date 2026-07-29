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
