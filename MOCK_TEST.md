[Back to the study plan](README.md)

# Mock test

35 questions, no notes. Answer each question first, then click **Answer** to check it.

---

###### 1. True or False: Flutter apps are written in the Dart language.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

Dart is the language and Flutter is the toolkit.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 2. True or False: A Flutter project made for Android has to be rewritten from scratch before it can run on an iPhone.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

The same codebase can be built for iOS.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 3. True or False: Building a Flutter app means dragging ready-made blocks around, with hardly any typing.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

Flutter is not low-code. You write Dart code.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 4. True or False: You can try out a Flutter button in a web browser without installing anything.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

DartPad runs Flutter as well as plain Dart.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 5. True or False: Anyone can read the source code of the Flutter framework and of the Dart language.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

Both projects are open source.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 6. True or False: In Dart, a whole number such as `8` is an object and has its own methods.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

Numbers are objects too, so `8.toString()` works.

Read again: [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart)

</p>
</details>

---

###### 7. True or False: This code compiles inside `main()`.

```dart
int pax = 4;
double people = pax;
```

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

An `int` variable is not a `double`. Use `pax.toDouble()`.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 8. True or False: `double price = 6;` compiles.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

The literal `6` is treated as `6.0` here.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 9. True or False: This code compiles inside `main()`.

```dart
final String hall;
hall = 'FC5';
print(hall);
```

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

A local `final` can be set once on a later line.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 10. True or False: This code compiles inside `main()`.

```dart
const maxSeats;
maxSeats = 30;
```

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

A `const` needs its value on the declaration line.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 11. True or False: `{'S1': 'Ang', 'S2': 'Bala'}` is a Set.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

It has `key: value` pairs, so it is a Map.

Read again: [List, Set and Map](notes/2-collections-loops.md#collections)

</p>
</details>

---

###### 12. True or False: A named parameter with a default value may be left out of the call.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

The default value is used.

Read again: [Functions and parameters](notes/3-functions-null-classes.md#functions)

</p>
</details>

---

###### 13. True or False: `Icon` is a `StatelessWidget`.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

It only draws what it is given.

Read again: [Stateless, Stateful and setState](notes/5-state-textfield.md#state)

</p>
</details>

---

###### 14. True or False: `Checkbox` is a `StatefulWidget`.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

In Flutter's source, `Checkbox` extends `StatefulWidget`.

Read again: [Stateless, Stateful and setState](notes/5-state-textfield.md#state)

</p>
</details>

---

###### 15. True or False: You may leave `onPressed` out of an `ElevatedButton`. The button just looks disabled.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

`onPressed` is required. Pass `null` to disable the button.

Read again: [Buttons and constructor headers](notes/4-widgets-buttons.md#buttons)

</p>
</details>

---

###### 16. True or False: A class that extends `StatefulWidget` has its `createState()` method in the same class.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A (True)

`createState()` is in the widget class. `build()` is in the State class.

Read again: [Stateless, Stateful and setState](notes/5-state-textfield.md#state)

</p>
</details>

---

###### 17. True or False: If you change a variable in the State class without calling `setState()`, the screen updates anyway.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

Flutter is not told to rebuild, so the screen stays the same.

Read again: [Stateless, Stateful and setState](notes/5-state-textfield.md#state)

</p>
</details>

---

###### 18. True or False: `Center` can hold several widgets through its `children` parameter.

- A: True
- B: False

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B (False)

`Center` has `child` and holds one widget.

Read again: [Widgets and their parameters](notes/4-widgets-buttons.md#widgets)

</p>
</details>

---

###### 19. Where does this program start running?

```dart
void setup() { print('A'); }
void Main() { print('B'); }
void main() { print('C'); }
```

- A: `setup()`
- B: `Main()`
- C: `main()`
- D: The first function in the file

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

Dart starts at `main()`, all in small letters.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 20. What is printed?

```dart
var km = double.parse('3.25');   // line 1
var trips = int.parse('2');      // line 2
print('Total: ${km * trips}');   // line 3
```

- A: Total: 6.5
- B: Total: ${km * trips}
- C: Nothing: error on line 2
- D: Nothing: error on line 3

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A

3.25 × 2 = 6.5, and `${ }` prints the result.

Read again: [Strings and numbers](notes/1-flutter-variables-strings.md#strings-numbers)

</p>
</details>

---

###### 21. What happens?

```dart
var w = int.parse('62.4');   // line 1
print('Weight: $w');         // line 2
```

- A: Weight: 62
- B: Weight: 62.4
- C: Weight: null
- D: Nothing prints: error on line 1

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

`int.parse` accepts whole numbers only.

Read again: [Strings and numbers](notes/1-flutter-variables-strings.md#strings-numbers)

</p>
</details>

---

###### 22. Which line compiles?

- A: `bool isOpen = 'yes';`
- B: `bool isOpen = 9 = 10;`
- C: `bool isOpen = 9 > 10;`
- D: `Bool isOpen = true;`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

A comparison gives a bool. The value is `false`, which is fine.

Read again: [main(), variables and types](notes/1-flutter-variables-strings.md#variables)

</p>
</details>

---

###### 23. What is printed?

```dart
var seats = {'A1', 'A2', 'A1'};
print(seats.length);
```

- A: 1
- B: 2
- C: 3
- D: Compile error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

This is a Set, so the second 'A1' is dropped.

Read again: [List, Set and Map](notes/2-collections-loops.md#collections)

</p>
</details>

---

###### 24. What is printed?

```dart
var stock = {'Milo': 4, 'Teh': 0};
print(stock['Kopi']);
```

- A: 0
- B: null
- C: Kopi
- D: Compile error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

Reading a key that does not exist gives `null`.

Read again: [List, Set and Map](notes/2-collections-loops.md#collections)

</p>
</details>

---

###### 25. What is printed?

```dart
String? remark;
print(remark ?? 'No remark');
```

- A: null
- B: remark
- C: No remark
- D: Compile error

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

`remark` is null, so `??` uses the right side.

Read again: [Null safety](notes/3-functions-null-classes.md#null-safety)

</p>
</details>

---

###### 26. What happens?

```dart
void main() {
  String owner;
  print(owner);
}
```

- A: It prints null
- B: It prints an empty line
- C: It prints owner
- D: It does not compile

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

A plain `String` cannot be null and has no value yet.

Read again: [Null safety](notes/3-functions-null-classes.md#null-safety)

</p>
</details>

---

###### 27. Which call compiles?

```dart
void ride(double km, int pax, {double tip = 0}) {}
```

- A: `ride(4.5, 2, 1.0);`
- B: `ride(4.5, tip: 1.0);`
- C: `ride(4.5, 2, tip: 1.0);`
- D: `ride(4.5, 2, tip = 1.0);`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

Two positional values, then the named one with a colon.

Read again: [Functions and parameters](notes/3-functions-null-classes.md#functions)

</p>
</details>

---

###### 28. Which call does **NOT** compile?

```dart
String tag(String food, {int qty = 1, bool spicy = false}) =>
    '$food $qty $spicy';
```

- A: `tag('Mee');`
- B: `tag('Mee', spicy: true);`
- C: `tag('Mee', spicy: true, qty: 3);`
- D: `tag('Mee', 3, spicy: true);`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

`qty` is named, so a bare `3` is not allowed.

Read again: [Functions and parameters](notes/3-functions-null-classes.md#functions)

</p>
</details>

---

###### 29. A button has this header. Which call is correct?

```dart
TextButton({
  required void Function()? onPressed,
  void Function()? onLongPress,
  void Function(bool)? onHover,
  required Widget child,
})
```

- A: `TextButton(child: Text('Map'))`
- B: `TextButton(onLongPress: () {}, child: Text('Map'))`
- C: `TextButton(onPressed: () {}, onHover: () {}, child: Text('Map'))`
- D: `TextButton(child: Text('Map'), onPressed: null)`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: D

Both required parameters are there, and `onPressed` may be null.

Read again: [Buttons and constructor headers](notes/4-widgets-buttons.md#buttons)

</p>
</details>

---

###### 30. Which line compiles?

- A: `runApp('Welcome');`
- B: `runApp([Text('Welcome')]);`
- C: `runApp(Center(child: Text('Welcome')));`
- D: `runApp(true);`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: C

`runApp` takes one widget.

Read again: [Widgets and their parameters](notes/4-widgets-buttons.md#widgets)

</p>
</details>

---

###### 31. A `TextField` uses `_blockCtrl` as its controller. Which expression gives the typed text as a String?

- A: `_blockCtrl.input`
- B: `_blockCtrl.text`
- C: `_blockCtrl.content`
- D: `_blockCtrl.toString()`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`.text` holds what the user typed.

Read again: [TextField and its controller](notes/5-state-textfield.md#textfield)

</p>
</details>

---

###### 32. Which code makes the new total appear on the screen?

- A: `_total = 9;`
- B: `setState(() { _total = 9; });`
- C: `rebuild(() { _total = 9; });`
- D: `build(_total = 9);`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: B

`setState` makes the change and asks Flutter to rebuild.

Read again: [Stateless, Stateful and setState](notes/5-state-textfield.md#state)

</p>
</details>

---

###### 33. Which widgets have a `child` parameter? Choose **all** that apply.

- A: `Container`
- B: `Column`
- C: `Padding`
- D: `Row`
- E: `OutlinedButton`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A, C, E

`Row` and `Column` take `children`.

Read again: [Widgets and their parameters](notes/4-widgets-buttons.md#widgets)

</p>
</details>

---

###### 34. Which are parameters of `Scaffold`? Choose **all** that apply.

- A: `appBar`
- B: `home`
- C: `body`
- D: `floatingActionButton`
- E: `children`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A, C, D

`home` belongs to `MaterialApp`. `children` belongs to Row and Column.

Read again: [Widgets and their parameters](notes/4-widgets-buttons.md#widgets)

</p>
</details>

---

###### 35. Which lines empty the box controlled by `_nameCtrl`? Choose **all** that apply.

- A: `_nameCtrl.text = '';`
- B: `_nameCtrl.clear();`
- C: `_nameCtrl.text = null;`
- D: `_nameCtrl.text = 0;`

<details><summary><b>Answer</b></summary>
<p>

#### Answer: A, B

`.text` must be a String, so `null` and `0` do not compile.

Read again: [TextField and its controller](notes/5-state-textfield.md#textfield)

</p>
</details>

---

**Finished?** Go to [Common traps](notes/common-traps.md) or [back to the study plan](README.md).
