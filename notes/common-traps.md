[Back to the study plan](../README.md)

# Common traps

| Watch out for | Remember |
|---|---|
| `=` or `==` | One stores. Two compare. |
| `int` and `double` | Two different types. Neither is also the other. |
| `final` or `const` | A local `final` may be set once later. `const` needs its value at once. |
| `{ }` | Colon inside means Map. Plain values mean Set. In a parameter list it means named. |
| `??` | Look at the declaration first: `int?` and `var` start as null, plain `int` does not compile. |
| `int.parse` | Whole numbers only. A decimal point is an error. |
| Named parameters | Always `name: value`, with a colon. |
| `child` or `children` | One widget, or a list. |
| `home`, `appBar`, `body` | MaterialApp has `home`. Scaffold has `appBar` and `body`. |
| Buttons | `onPressed` and `child` are both required. |
| `build()` | Stateful: in the State class. Stateless: in the widget class. |
| `setState()` | No `setState`, no redraw. |
| `.text` | Read with `.text`. Clear with `.text = ''` or `.clear()`. |
| only, NOT | Circle these words in your head before you answer. |
