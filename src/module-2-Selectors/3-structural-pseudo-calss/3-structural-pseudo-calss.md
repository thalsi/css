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


| Selector               | Counts What?              | Example Match  |
| ---------------------- | ------------------------- | -------------- |
| `:first-child`         | First child               | 1st child      |
| `:last-child`          | Last child                | Last child     |
| `:nth-child(3)`        | Every child               | 3rd child      |
| `:nth-last-child(2)`   | Every child from end      | 2nd from last  |
| `:only-child`          | Only child                | Single child   |
| `:first-of-type`       | Same tag only             | First `<p>`    |
| `:last-of-type`        | Same tag only             | Last `<p>`     |
| `:nth-of-type(2)`      | Same tag only             | 2nd `<p>`      |
| `:nth-last-of-type(2)` | Same tag from end         | 2nd last `<p>` |
| `:only-of-type`        | Only one tag of that type | Only `<span>`  |
| `:empty`               | No children or text       | Empty `<div>`  |
