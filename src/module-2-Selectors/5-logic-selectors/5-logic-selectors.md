## 5. Logic Selectors

| **Selector**         | **Description**                               | **Example**                                   | **Usage**                                                     |
| -------------------- | --------------------------------------------- | --------------------------------------------- | ------------------------------------------------------------- |
| `:not(sel)`          | Select elements **not** matching selector     | `li:not(.active) { color: gray; }`            | Exclude items from style rules                                |
| `:is(sel1, sel2)`    | Matches any of listed selectors (specificity) | `:is(h1, h2) { margin: 0; }`                  | Cleaner group targeting with full specificity                 |
| `:where(sel1, sel2)` | Like `:is`, but no specificity                | `:where(section, article) { padding: 1rem; }` | Use in resets or design systems to avoid conflicts            |
| `:has(sel)`          | Select parent with matching child (modern)    | `div:has(img) { border: 1px solid red; }`     | Conditional styling when children exist (Chrome support only) |
    