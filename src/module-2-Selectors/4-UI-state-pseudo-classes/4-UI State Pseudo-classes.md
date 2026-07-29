
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
