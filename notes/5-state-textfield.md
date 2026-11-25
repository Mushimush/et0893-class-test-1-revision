[Back to the study plan](../README.md)

# Step 5: State and TextField

- [Stateless, Stateful and setState](#state)
- [TextField and its controller](#textfield)

---

<a id="state"></a>

## Stateless, Stateful and setState

*Chapters 3 and 4*

Ask one question: **does anything on this screen change while the app is running?**

| | `StatelessWidget` | `StatefulWidget` |
|---|---|---|
| Keeps data that can change? | No | Yes, in its `State` object |
| Number of classes | One | Two |
| Where is `build()`? | In the widget class | In the **State** class |
| Flutter's own examples | `Text`, `Icon`, `Container` | `TextField`, `Checkbox`, `Slider` |

```dart
class Counter extends StatefulWidget {
  const Counter({super.key});
  @override
  State<Counter> createState() => _CounterState();   // no build() here
}

class _CounterState extends State<Counter> {
  int _plates = 0;

  @override
  Widget build(BuildContext context) {               // build() is here
    return TextButton(
      onPressed: () {
        setState(() {
          _plates++;
        });
      },
      child: Text('Plates: $_plates'),
    );
  }
}
```

**`setState()`** does two jobs: it runs your change, then it tells Flutter to call `build()` again. Without it the variable changes but the screen stays the same.

> **Trap:** the `StatefulWidget` class has `createState()`. The class that extends `State` has `build()`.

### Check yourself

**1.** A page shows your school's address and logo. Stateless or Stateful?

<details><summary>Answer</summary>

Stateless. Nothing on it changes while the app runs.

</details>

**2.** A page shows the number of items in a cart as you tap. Which, and which method redraws it?

<details><summary>Answer</summary>

Stateful. Change the number inside `setState()`.

</details>

**3.** The code runs `_plates++` without `setState`. The user taps three times. What does the screen show?

<details><summary>Answer</summary>

Still `Plates: 0`. The variable is 3, but Flutter was never told to rebuild.

</details>

**4.** For a `StatelessWidget`, in which class do you write `build()`?

<details><summary>Answer</summary>

In the class that extends `StatelessWidget`. There is no State class.

</details>

---

<a id="textfield"></a>

## TextField and its controller

*Chapter 4*

A `TextField` lets the user type. A `TextEditingController` lets your code read and change what is in it.

```dart
final _postalCtrl = TextEditingController();      // 1. make it

TextField(controller: _postalCtrl)                // 2. connect it

print(_postalCtrl.text);                          // 3. read it

_postalCtrl.text = '';                            // 4. clear it
_postalCtrl.clear();                              //    or this
```

- **`.text` is always a String**, even if the user typed digits. Use `int.tryParse` or `double.tryParse` to get a number.
- The controller also has a `.value`, but that is a bigger object (text, cursor and selection). For the typed text, use `.text`.
- `.text` cannot be set to a number or to `null`. Use an empty String `''`.
- `Text` only **shows** text. `TextField` lets the user **type**.

### The calculator pattern

```dart
void _calculate() {
  final kg = double.tryParse(_kgCtrl.text);
  if (kg == null) {
    ScaffoldMessenger.of(context).showSnackBar(
        const SnackBar(content: Text('Please type a number')));
    return;
  }
  setState(() => _result = (kg * 2).toStringAsFixed(2));
}
```

> **Trap:** `'12' + '3'` joins two Strings and gives `123`. Parse first, then add.

### Check yourself

**1.** The user typed `20`. What does `_ageCtrl.text + '1'` give?

<details><summary>Answer</summary>

`201`. Both are Strings, so `+` joins them.

</details>

**2.** Which object do you pass to a TextField's `controller:`?

<details><summary>Answer</summary>

A `TextEditingController`.

</details>

**3.** Does `_ageCtrl.text = 0;` clear the box?

<details><summary>Answer</summary>

No, it does not compile. `.text` is a String. Use `_ageCtrl.text = '';` or `_ageCtrl.clear();`.

</details>

---

**Move on when** you can say where `build()` goes, what `setState` does, and how to read and clear a TextField.

[Next: the mock test](../MOCK_TEST.md) | [Back to the study plan](../README.md)
