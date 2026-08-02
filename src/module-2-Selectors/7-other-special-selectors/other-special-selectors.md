
## 7. Other Special Selectors

| **Selector**              | **Description**                                       | **Example**                          | **Usage**                                           |
| ------------------------- | ----------------------------------------------------- | ------------------------------------ | --------------------------------------------------- |
| `:lang(lang-code)`        | Match elements by language                            | `p:lang(en) { font-style: italic; }` | Apply styles based on language locale               |
| `:dir(ltr)` / `:dir(rtl)` | Match text direction (left-to-right or right-to-left) | `:dir(rtl) { text-align: right; }`   | RTL language support                                |
| `:root`                   | Targets root element (`<html>`)                       | `:root { --main-color: #333; }`      | Define CSS custom properties (variables) globally   |
| `:scope`                  | Current context in query selector or shadow DOM       | `:scope > h2 { font-weight: bold; }` | Used in scripts or scoped styling within components |