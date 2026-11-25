[Back to the study plan](../README.md)

# Step 4: Widgets and buttons

- [Widgets and their parameters](#widgets)
- [Buttons and constructor headers](#buttons)

---

<a id="widgets"></a>

## Widgets and their parameters

*Chapter 3*

Everything on the screen is a widget. `runApp()` takes **one widget** and shows it.

```dart
void main() {
  runApp(const MaterialApp(
    home: Scaffold(
      body: Center(child: Text('Hello')),
    ),
  ));
}
```

`runApp('Hello')` does not compile, because a String is not a widget. `runApp(const Text('Hello'))` does compile, because `Text` is a widget.

### Who owns which parameter?

| Widget | Its job | Parameters to know |
|---|---|---|
| `MaterialApp` | The whole app | `home:`, `title:`, `theme:` |
| `Scaffold` | One page | `appBar:`, `body:`, `floatingActionButton:` |
| `AppBar` | The bar at the top | `title:` |
| `Center` | Centres one widget | `child:` |
| `Container` | A box with size, colour and space | `child:`, `color:`, `padding:`, `margin:`, `width:`, `height:` |
| `Padding` | Space around one widget | `padding:`, `child:` |
| `Row` | Side by side | `children:`, `mainAxisAlignment:` |
| `Column` | Top to bottom | `children:`, `mainAxisAlignment:` |
| `Text` | Shows text | the text comes first |
| `TextField` | The user types here | `controller:`, `decoration:` |

### child or children?

- **`child:`** takes **one** widget: `Center`, `Container`, `Padding`, buttons.
- **`children:`** takes a **list** `[ ]`: `Row`, `Column`, `ListView`, `Stack`.
- Parameter names start with a small letter. `Child:` and `Color:` do not exist.

### Rows and Columns

| | Main axis | Cross axis |
|---|---|---|
| `Row` | Left to right | Top to bottom |
| `Column` | Top to bottom | Left to right |

`EdgeInsets.all(16)` puts the same space on all four sides.

> **Trap:** `home:` belongs to `MaterialApp`. `appBar:` and `body:` belong to `Scaffold`.

### Check yourself

**1.** Fix it: `Column(child: [Text('A'), Text('B')])`

<details><summary>Answer</summary>

`Column(children: [Text('A'), Text('B')])`. A Column takes a list, so the name is `children`.

</details>

**2.** Fix it: `MaterialApp(body: Text('Hi'))`

<details><summary>Answer</summary>

`MaterialApp(home: Scaffold(body: Text('Hi')))`. `body` belongs to `Scaffold`.

</details>

**3.** You want two icons side by side in the middle of the page. Which widgets?

<details><summary>Answer</summary>

`Center(child: Row(...))` with `mainAxisAlignment: MainAxisAlignment.center` in the Row, and the two icons in its `children: [ ]`.

</details>

**4.** Does `runApp(123)` compile?

<details><summary>Answer</summary>

No. `123` is an int. `runApp` needs a widget.

</details>

---

<a id="buttons"></a>

## Buttons and constructor headers

*Chapters 3 and 4*

`FilledButton`, `ElevatedButton`, `TextButton` and `OutlinedButton` all need **both**:

- `onPressed:` is the function to run when the user taps.
- `child:` is what the button shows.

```dart
FilledButton(
  onPressed: () { print('Paid'); },
  child: const Text('Pay'),
)
```

### Read a constructor header

```dart
FilledButton({
  required void Function()? onPressed,
  void Function()? onLongPress,
  void Function(bool)? onHover,
  required Widget? child,
})
```

| You see | It means |
|---|---|
| `{ }` around everything | All parameters are **named**. Any order is fine |
| `required` | The call must include it |
| `?` after the type | You may pass `null` |
| `void Function()?` | Give a function with **no** input: `() {}` |
| `void Function(bool)?` | Give a function with **one** input: `(isOver) {}` |

| Call | OK? | Why |
|---|---|---|
| `FilledButton(child: Text('Pay'), onPressed: () {})` | Yes | Order does not matter |
| `FilledButton(onPressed: null, child: Text('Pay'))` | Yes | Shows a greyed-out button |
| `FilledButton(child: Text('Pay'))` | No | `onPressed` is missing |
| `FilledButton(onPressed: () {})` | No | `child` is missing |
| `FilledButton(onPressed: () {}, onHover: () {}, child: Text('Pay'))` | No | `onHover` needs one input |

> **Trap:** `required` with `?` means you must write the parameter, and its value is allowed to be null.

### Check yourself

**1.** Does `TextButton(onLongPress: () {}, child: Text('Help'))` compile?

<details><summary>Answer</summary>

No. `onPressed` is required. `onLongPress` does not replace it.

</details>

**2.** How do you show a disabled `ElevatedButton`?

<details><summary>Answer</summary>

Pass `onPressed: null`. You still have to write it.

</details>

**3.** What is the difference between `onPressed: _add` and `onPressed: _add()`?

<details><summary>Answer</summary>

`_add` hands the function to the button to run later. `_add()` runs it straight away, and for a `void` function that does not compile.

</details>

---

**Move on when** you can say which widgets take `child`, which take `children`, and where `home`, `appBar` and `body` belong.

[Next: Step 5](5-state-textfield.md) | [Back to the study plan](../README.md)
