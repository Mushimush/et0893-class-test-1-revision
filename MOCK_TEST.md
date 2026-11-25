[Back to the study plan](README.md)

# Mock test

35 questions, no notes. Write your answers on paper, then [check them](#answers).

**1.** *(True or False)* Flutter apps are written in the Dart language.

- True
- False

**2.** *(True or False)* A Flutter project made for Android has to be rewritten from scratch before it can run on an iPhone.

- True
- False

**3.** *(True or False)* Building a Flutter app means dragging ready-made blocks around, with hardly any typing.

- True
- False

**4.** *(True or False)* You can try out a Flutter button in a web browser without installing anything.

- True
- False

**5.** *(True or False)* Anyone can read the source code of the Flutter framework and of the Dart language.

- True
- False

**6.** *(True or False)* In Dart, a whole number such as `8` is an object and has its own methods.

- True
- False

**7.** *(True or False)* This code compiles inside `main()`.

```dart
int pax = 4;
double people = pax;
```

- True
- False

**8.** *(True or False)* `double price = 6;` compiles.

- True
- False

**9.** *(True or False)* This code compiles inside `main()`.

```dart
final String hall;
hall = 'FC5';
print(hall);
```

- True
- False

**10.** *(True or False)* This code compiles inside `main()`.

```dart
const maxSeats;
maxSeats = 30;
```

- True
- False

**11.** *(True or False)* `{'S1': 'Ang', 'S2': 'Bala'}` is a Set.

- True
- False

**12.** *(True or False)* A named parameter with a default value may be left out of the call.

- True
- False

**13.** *(True or False)* `Icon` is a `StatelessWidget`.

- True
- False

**14.** *(True or False)* `Checkbox` is a `StatefulWidget`.

- True
- False

**15.** *(True or False)* You may leave `onPressed` out of an `ElevatedButton`. The button just looks disabled.

- True
- False

**16.** *(True or False)* A class that extends `StatefulWidget` has its `createState()` method in the same class.

- True
- False

**17.** *(True or False)* If you change a variable in the State class without calling `setState()`, the screen updates anyway.

- True
- False

**18.** *(True or False)* `Center` can hold several widgets through its `children` parameter.

- True
- False

**19.** *(Choose one)* Where does this program start running?

```dart
void setup() { print('A'); }
void Main() { print('B'); }
void main() { print('C'); }
```

- A. `setup()`
- B. `Main()`
- C. `main()`
- D. The first function in the file

**20.** *(Choose one)* What is printed?

```dart
var km = double.parse('3.25');   // line 1
var trips = int.parse('2');      // line 2
print('Total: ${km * trips}');   // line 3
```

- A. Total: 6.5
- B. Total: ${km * trips}
- C. Nothing: error on line 2
- D. Nothing: error on line 3

**21.** *(Choose one)* What happens?

```dart
var w = int.parse('62.4');   // line 1
print('Weight: $w');         // line 2
```

- A. Weight: 62
- B. Weight: 62.4
- C. Weight: null
- D. Nothing prints: error on line 1

**22.** *(Choose one)* Which line compiles?

- A. `bool isOpen = 'yes';`
- B. `bool isOpen = 9 = 10;`
- C. `bool isOpen = 9 > 10;`
- D. `Bool isOpen = true;`

**23.** *(Choose one)* What is printed?

```dart
var seats = {'A1', 'A2', 'A1'};
print(seats.length);
```

- A. 1
- B. 2
- C. 3
- D. Compile error

**24.** *(Choose one)* What is printed?

```dart
var stock = {'Milo': 4, 'Teh': 0};
print(stock['Kopi']);
```

- A. 0
- B. null
- C. Kopi
- D. Compile error

**25.** *(Choose one)* What is printed?

```dart
String? remark;
print(remark ?? 'No remark');
```

- A. null
- B. remark
- C. No remark
- D. Compile error

**26.** *(Choose one)* What happens?

```dart
void main() {
  String owner;
  print(owner);
}
```

- A. It prints null
- B. It prints an empty line
- C. It prints owner
- D. It does not compile

**27.** *(Choose one)* Which call compiles?

```dart
void ride(double km, int pax, {double tip = 0}) {}
```

- A. `ride(4.5, 2, 1.0);`
- B. `ride(4.5, tip: 1.0);`
- C. `ride(4.5, 2, tip: 1.0);`
- D. `ride(4.5, 2, tip = 1.0);`

**28.** *(Choose one)* Which call does **NOT** compile?

```dart
String tag(String food, {int qty = 1, bool spicy = false}) =>
    '$food $qty $spicy';
```

- A. `tag('Mee');`
- B. `tag('Mee', spicy: true);`
- C. `tag('Mee', spicy: true, qty: 3);`
- D. `tag('Mee', 3, spicy: true);`

**29.** *(Choose one)* A button has this header. Which call is correct?

```dart
TextButton({
  required void Function()? onPressed,
  void Function()? onLongPress,
  void Function(bool)? onHover,
  required Widget child,
})
```

- A. `TextButton(child: Text('Map'))`
- B. `TextButton(onLongPress: () {}, child: Text('Map'))`
- C. `TextButton(onPressed: () {}, onHover: () {}, child: Text('Map'))`
- D. `TextButton(child: Text('Map'), onPressed: null)`

**30.** *(Choose one)* Which line compiles?

- A. `runApp('Welcome');`
- B. `runApp([Text('Welcome')]);`
- C. `runApp(Center(child: Text('Welcome')));`
- D. `runApp(true);`

**31.** *(Choose one)* A `TextField` uses `_blockCtrl` as its controller. Which expression gives the typed text as a String?

- A. `_blockCtrl.input`
- B. `_blockCtrl.text`
- C. `_blockCtrl.content`
- D. `_blockCtrl.toString()`

**32.** *(Choose one)* Which code makes the new total appear on the screen?

- A. `_total = 9;`
- B. `setState(() { _total = 9; });`
- C. `rebuild(() { _total = 9; });`
- D. `build(_total = 9);`

**33.** *(Choose all that apply)* Which widgets have a `child` parameter? Choose **all** that apply.

- A. `Container`
- B. `Column`
- C. `Padding`
- D. `Row`
- E. `OutlinedButton`

**34.** *(Choose all that apply)* Which are parameters of `Scaffold`? Choose **all** that apply.

- A. `appBar`
- B. `home`
- C. `body`
- D. `floatingActionButton`
- E. `children`

**35.** *(Choose all that apply)* Which lines empty the box controlled by `_nameCtrl`? Choose **all** that apply.

- A. `_nameCtrl.text = '';`
- B. `_nameCtrl.clear();`
- C. `_nameCtrl.text = null;`
- D. `_nameCtrl.text = 0;`

---

<a id="answers"></a>

## Answers

For every wrong answer, open the topic in the last column and read it again.

| # | Answer | Why | Read again |
|---|---|---|---|
| 1 | True | Dart is the language and Flutter is the toolkit. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 2 | False | The same codebase can be built for iOS. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 3 | False | Flutter is not low-code. You write Dart code. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 4 | True | DartPad runs Flutter as well as plain Dart. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 5 | True | Both projects are open source. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 6 | True | Numbers are objects too, so `8.toString()` works. | [Flutter and Dart](notes/1-flutter-variables-strings.md#flutter-dart) |
| 7 | False | An `int` variable is not a `double`. Use `pax.toDouble()`. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 8 | True | The literal `6` is treated as `6.0` here. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 9 | True | A local `final` can be set once on a later line. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 10 | False | A `const` needs its value on the declaration line. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 11 | False | It has `key: value` pairs, so it is a Map. | [List, Set and Map](notes/2-collections-loops.md#collections) |
| 12 | True | The default value is used. | [Functions and parameters](notes/3-functions-null-classes.md#functions) |
| 13 | True | It only draws what it is given. | [Stateless, Stateful and setState](notes/5-state-textfield.md#state) |
| 14 | True | In Flutter's source, `Checkbox` extends `StatefulWidget`. | [Stateless, Stateful and setState](notes/5-state-textfield.md#state) |
| 15 | False | `onPressed` is required. Pass `null` to disable the button. | [Buttons and constructor headers](notes/4-widgets-buttons.md#buttons) |
| 16 | True | `createState()` is in the widget class. `build()` is in the State class. | [Stateless, Stateful and setState](notes/5-state-textfield.md#state) |
| 17 | False | Flutter is not told to rebuild, so the screen stays the same. | [Stateless, Stateful and setState](notes/5-state-textfield.md#state) |
| 18 | False | `Center` has `child` and holds one widget. | [Widgets and their parameters](notes/4-widgets-buttons.md#widgets) |
| 19 | C | Dart starts at `main()`, all in small letters. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 20 | A | 3.25 × 2 = 6.5, and `${ }` prints the result. | [Strings and numbers](notes/1-flutter-variables-strings.md#strings-numbers) |
| 21 | D | `int.parse` accepts whole numbers only. | [Strings and numbers](notes/1-flutter-variables-strings.md#strings-numbers) |
| 22 | C | A comparison gives a bool. The value is `false`, which is fine. | [main(), variables and types](notes/1-flutter-variables-strings.md#variables) |
| 23 | B | This is a Set, so the second 'A1' is dropped. | [List, Set and Map](notes/2-collections-loops.md#collections) |
| 24 | B | Reading a key that does not exist gives `null`. | [List, Set and Map](notes/2-collections-loops.md#collections) |
| 25 | C | `remark` is null, so `??` uses the right side. | [Null safety](notes/3-functions-null-classes.md#null-safety) |
| 26 | D | A plain `String` cannot be null and has no value yet. | [Null safety](notes/3-functions-null-classes.md#null-safety) |
| 27 | C | Two positional values, then the named one with a colon. | [Functions and parameters](notes/3-functions-null-classes.md#functions) |
| 28 | D | `qty` is named, so a bare `3` is not allowed. | [Functions and parameters](notes/3-functions-null-classes.md#functions) |
| 29 | D | Both required parameters are there, and `onPressed` may be null. | [Buttons and constructor headers](notes/4-widgets-buttons.md#buttons) |
| 30 | C | `runApp` takes one widget. | [Widgets and their parameters](notes/4-widgets-buttons.md#widgets) |
| 31 | B | `.text` holds what the user typed. | [TextField and its controller](notes/5-state-textfield.md#textfield) |
| 32 | B | `setState` makes the change and asks Flutter to rebuild. | [Stateless, Stateful and setState](notes/5-state-textfield.md#state) |
| 33 | A, C, E | `Row` and `Column` take `children`. | [Widgets and their parameters](notes/4-widgets-buttons.md#widgets) |
| 34 | A, C, D | `home` belongs to `MaterialApp`. `children` belongs to Row and Column. | [Widgets and their parameters](notes/4-widgets-buttons.md#widgets) |
| 35 | A, B | `.text` must be a String, so `null` and `0` do not compile. | [TextField and its controller](notes/5-state-textfield.md#textfield) |
