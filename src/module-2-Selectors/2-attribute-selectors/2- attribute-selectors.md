## 2. Attribute Selectors

| **Selector**       | **Description**                                                                   | **Example**                                  | **Usage**                                 |
| ------------------ | --------------------------------------------------------------------------------- | -------------------------------------------- | ----------------------------------------- |
| `[attr]`           | Selects elements that **have the attribute**                                      | `input[required] { border: 2px solid red; }` | Style all required fields                 |
| `[attr="value"]`   | Selects elements whose attribute **exactly matches** the value                    | `input[type="text"] { color: blue; }`        | Style a specific input type               |
| `[attr^="value"]`  | Selects elements whose attribute **starts with** the value                        | `a[href^="https"] { color: green; }`         | Style secure links                        |
| `[attr$="value"]`  | Selects elements whose attribute **ends with** the value                          | `img[src$=".jpg"] { border-radius: 8px; }`   | Style JPG images                          |
| `[attr*="value"]`  | Selects elements whose attribute **contains** the value                           | `div[class*="error"] { background: pink; }`  | Style classes containing `"error"`        |
| `[attr~="value"]`  | Selects elements whose attribute contains the value as a **separate word**        | `[title~="sale"] { font-weight: bold; }`     | Match one word in a space-separated list  |
| `[attr\|="value"]` | Selects elements whose attribute is exactly the value **or starts with `value-`** | `p[lang\|="en"] { font-style: italic; }`     | Match language codes like `en` or `en-US` |
