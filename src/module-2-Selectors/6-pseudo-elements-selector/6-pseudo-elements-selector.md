
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
