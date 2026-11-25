# Class Test 1 Revision Guide

ET0893 Mobile Applications Development. Chapters 1 to 4.

1. Read one topic.
2. Answer its **Check yourself** questions, then open the answers.
3. Do [MOCK_TEST.md](MOCK_TEST.md) in 70 minutes with no notes.

These are practice questions. The real test has different ones.

## Topics

- [Flutter and Dart](#flutter-dart)
- [main(), variables and types](#variables)
- [Strings and numbers](#strings-numbers)
- [List, Set and Map](#collections)
- [Choices and loops](#control)
- [Functions and parameters](#functions)
- [Null safety](#null-safety)
- [Classes in one page](#classes)
- [Widgets and their parameters](#widgets)
- [Buttons and constructor headers](#buttons)
- [Stateless, Stateful and setState](#state)
- [TextField and its controller](#textfield)
- [Common traps](#traps)

---

<a id="flutter-dart"></a>

## Flutter and Dart

*Chapter 1*

**Dart is the programming language. Flutter is the UI toolkit (framework) you use from Dart.** You write Dart code, and that code uses Flutter's widgets to draw the screen.

| | Dart | Flutter |
|---|---|---|
| What is it? | A programming language | A UI toolkit, also called a UI framework |
| Who started it? | Google | Google |
| Open source? | Yes | Yes |
| Where can you try it? | DartPad, VS Code | DartPad, VS Code |

- **One codebase, many platforms:** Android, iOS, web, Windows, macOS and Linux.
- **Real code:** Flutter is not a low-code or drag-and-drop tool. You type Dart.
- **Fast apps:** on phones, your Dart code is compiled to native code for that phone.
- **Open source** means anyone can read the code and contribute to it. Google leads both projects, and the community helps.
- **Everything you can store in a Dart variable is an object**, even a number. That is why `5.toString()` works.
- **Hot reload** shows a changed `build()` in about a second. **Hot restart** starts the app again from the beginning.

> **Trap:** the words *only* and *not* in a True/False statement. Read the sentence twice, then check every part of it. One wrong word makes the whole statement False.

### Check yourself

**1.** Your friend says "I program in Flutter, and Dart is the framework." What is wrong?

<details><summary>Answer</summary>

It is the other way round. Dart is the language. Flutter is the framework (UI toolkit).

</details>

**2.** Can you run a Flutter `Text` widget on a computer with nothing installed?

<details><summary>Answer</summary>

Yes. Open **dartpad.dev** in a browser. It runs plain Dart programs and Flutter apps.

</details>

**3.** You have finished an Android app in Flutter. Must you rewrite it in Swift for iPhone?

<details><summary>Answer</summary>

No. The same Dart codebase can be built for iOS as well.

</details>


---

<a id="variables"></a>

## main(), variables and types

*Chapter 2*

Every Dart program starts at `main()`. Dart is **case-sensitive**, so every letter must match.

```dart
void main() {
  print('Hello');
}
```

### Four basic types

| Type | Holds | Example |
|---|---|---|
| `int` | Whole numbers | `int seats = 40;` |
| `double` | Numbers with decimals | `double fare = 1.75;` |
| `String` | Text in `'single'` or `"double"` quotes | `String stall = "Ah Hock";` |
| `bool` | Only `true` or `false` | `bool isOpen = true;` |

`int` and `double` are **two different types**. An `int` variable is not also a `double`, and a `double` variable is not also an `int`.

```dart
double a = 4;        // OK: Dart writes the literal 4 as 4.0
int seats = 40;
double b = seats;    // ERROR: an int variable is not a double
int c = 4.0;         // ERROR: a double is not an int
double d = seats.toDouble();   // OK: you converted it
```

### What counts as a bool?

A comparison gives you a `bool`. One `=` **stores** a value. Two `==` **compare** two values.

```dart
bool p = 7 > 3;        // OK: true
bool q = 7 == 3;       // OK: false
bool r = 7 = 3;        // ERROR: one = cannot compare
bool s = 'true';       // ERROR: this is a String
bool t = 0;            // ERROR: this is an int
```

The type is spelled `bool`. The words `boolean` and `Bool` do not exist in Dart.

### var, final, const

| Keyword | Can you change it later? | Must it have a value on the same line? |
|---|---|---|
| `var` | Yes, but only to the same type once Dart has worked out the type | No |
| `final` | No. Set it **once** | No for a variable inside a function. You may set it on a later line |
| `const` | No | **Yes**, and the value must be known before the program runs |

```dart
void main() {
  final String shop;
  shop = 'Bee Hoon King';   // OK: the first and only time
  shop = 'Mee King';        // ERROR: already set once

  const gst;                // ERROR: const needs its value here
  const rate = 0.09;        // OK
}
```

> **Trap:** "`final` must have a value on the same line" is not true for a variable inside a function. For `const` it is always true.

### Check yourself

**1.** Does this compile inside `main()`?

```dart
final int table;
table = 12;
print(table);
```

<details><summary>Answer</summary>

Yes, and it prints `12`. A `final` variable inside a function can be set once on a later line.

</details>

**2.** Does `const maxPax; maxPax = 6;` compile?

<details><summary>Answer</summary>

No. A `const` must get its value on the line where you declare it.

</details>

**3.** What is the type of `isFull` in `var isFull = 30 >= 30;`?

<details><summary>Answer</summary>

`bool`. A comparison gives `true` or `false`. Here it is `true`.

</details>

**4.** Which is wrong: `double w = 60;` or `int w = 60.0;`?

<details><summary>Answer</summary>

`int w = 60.0;` is wrong. A `double` value cannot go into an `int`. The first line is fine.

</details>


---

<a id="strings-numbers"></a>

## Strings and numbers

*Chapter 2*

### String interpolation

| You write | Dart prints |
|---|---|
| `'$name'` | The value of one variable |
| `'${a + b}'` | The result of a calculation |
| `'${name.length}'` | A property of the variable |

```dart
var drink = 'Teh';
var cups = 3;
print('$drink x $cups');          // Teh x 3
print('Next: ${cups + 1}');       // Next: 4
print('$drink.length');           // Teh.length
print('${drink.length}');         // 3
```

Triple quotes `'''text'''` also make a String. Interpolation works in them too.

### Turning text into numbers

| Code | Result |
|---|---|
| `int.parse('15')` | `15` |
| `double.parse('2.75')` | `2.75` |
| `int.parse('2.75')` | **Error when it runs**: not a whole number |
| `int.parse('abc')` | **Error when it runs** |
| `int.tryParse('abc')` | `null`, no error |

An `int` and a `double` can be used in the same sum. The answer is a `double`.

```dart
var price = double.parse('2.25');
var qty = int.parse('2');
print('Pay ${price * qty}');      // Pay 4.5
```

### Three kinds of division

`7 / 2` gives `3.5`. `7 ~/ 2` gives `3`. `7 % 2` gives `1`, the remainder.

> **Trap:** `int.parse` accepts whole numbers only. Text with a decimal point stops the program on that line, so nothing after it prints.

### Check yourself

**1.** What does this print?

```dart
var t = 6;
print('${t - 8}');
```

<details><summary>Answer</summary>

`-2`. The expression in `${ }` is worked out first.

</details>

**2.** Which line stops the program?

```dart
var a = double.parse('9');   // line 1
var b = int.parse('9.5');    // line 2
print(a + b);                // line 3
```

<details><summary>Answer</summary>

Line 2. `int.parse` refuses `'9.5'`. Line 1 is fine, because `double.parse` accepts a whole number.

</details>

**3.** What does `print('$t + 1');` show when `t` is 6?

<details><summary>Answer</summary>

`6 + 1`. Only `$t` is replaced. To calculate, write `'${t + 1}'`.

</details>


---

<a id="collections"></a>

## List, Set and Map

*Chapter 2*

Look at the **brackets**, then look for a **colon**.

| You see | It is a | Duplicates? | Example |
|---|---|---|---|
| `[ ]` | `List` | Kept | `['Bedok', 'Tampines']` |
| `{ }` with plain values | `Set` | Removed | `{'EW', 'NS'}` |
| `{ }` with `key: value` | `Map` | Each key once | `{'Kopi': 1.4, 'Teh': 1.3}` |
| `' '` or `" "` | `String` | | `'Bedok'` |

```dart
var stops = ['Bedok', 'Simei', 'Bedok'];
print(stops.length);       // 3
print(stops[0]);           // Bedok

var lines = {'EW', 'NS', 'EW'};
print(lines.length);       // 2

var menu = {'Kopi': 1.4, 'Teh': 1.3};
print(menu['Teh']);        // 1.3
print(menu['Milo']);       // null: there is no such key
```

A List may mix types: `['Kopi', 2, true]` is still a List.

> **Trap:** `{'Bedok'}` looks like text but it is a **Set** holding one String. Only quotes on the outside make a String.

### Check yourself

**1.** List, Set or Map?

`var a = {3: 'Clementi', 4: 'Dover'};`

<details><summary>Answer</summary>

Map. Each item is a `key: value` pair.

</details>

**2.** List, Set or Map?

`var b = {'Clementi', 'Dover'};`

<details><summary>Answer</summary>

Set. Curly braces with plain values.

</details>

**3.** What does `print({5, 6, 5, 6}.length);` show?

<details><summary>Answer</summary>

`2`. A Set keeps each value once.

</details>


---

<a id="control"></a>

## Choices and loops

*Chapter 2*

The short if-else is called the **conditional operator**: `condition ? ifTrue : ifFalse`.

```dart
var temp = 31;
print(temp > 30 ? 'Hot' : 'OK');   // Hot
```

| Loop | Use it when |
|---|---|
| `for (var i = 0; i < 3; i++)` | You know how many times |
| `for (var x in list)` | You want every item |
| `while (condition)` | Check first, then run. May run zero times |
| `do { } while (condition);` | Run first, then check. Runs at least once |

`break` leaves the loop. `continue` skips to the next round.

```dart
var marks = [55, 40, 81];
var pass = 0;
for (var m in marks) {
  if (m >= 50) pass++;
}
print(pass);   // 2
```

In a `switch`, Dart runs the matching `case` only. It does not fall through to the next one.

> **Trap:** trace loops on paper. Write down the value of each variable after every round.

### Check yourself

**1.** What does this print?

```dart
var n = 1;
while (n < 10) {
  n = n * 3;
}
print(n);
```

<details><summary>Answer</summary>

`27`. n goes 1, 3, 9, 27. The loop stops when `n < 10` is false.

</details>

**2.** What does this print?

```dart
var hot = 0, cool = 0;
for (var t in [33, 28, 35]) {
  (t >= 30) ? hot++ : cool++;
}
print(hot);
```

<details><summary>Answer</summary>

`2`. 33 and 35 add one to `hot`. 28 adds one to `cool`.

</details>


---

<a id="functions"></a>

## Functions and parameters

*Chapter 2*

| Kind | In the function | In the call | Can you leave it out? |
|---|---|---|---|
| Positional | `int a` | `5` in the right place | No |
| Named, with a default | `{int b = 1}` | `b: 5` | Yes |
| Named, required | `{required int c}` | `c: 5` | No |
| Optional positional | `[int? d]` | `5` in the right place | Yes |

```dart
String bill(String food, double price, {int qty = 1}) {
  return '$food: ${price * qty}';
}

bill('Laksa', 5.5);               // OK: qty is 1
bill('Laksa', 5.5, qty: 2);       // OK
bill('Laksa', 5.5, 2);            // ERROR: qty needs its name
bill('Laksa', 5.5, qty = 2);      // ERROR: use a colon
bill('Laksa', qty: 2);            // ERROR: price is missing
bill(5.5, 'Laksa');               // ERROR: wrong order
```

### Check any call in three steps

1. **Count the positional values.** Are they all there, in the right order, with the right types?
2. **Look at the named ones.** Does each have `name:` in front?
3. **Look for `required`.** Is every required named parameter in the call?

Curly braces `{ }` in the parameter list mean **named**. They are not a Set here.

> **Trap:** a default value does not let you skip the name. `{int qty = 1}` must be given as `qty: 2`, never as a bare `2`.

### Check yourself

**1.** Given `int area(int w, int h, {int floors = 1}) => w * h * floors;`

What does `area(4, 5)` return?

<details><summary>Answer</summary>

`20`. `floors` uses its default value, 1.

</details>

**2.** Same function. Does `area(4, 5, 3)` compile?

<details><summary>Answer</summary>

No. `floors` is named, so write `area(4, 5, floors: 3)`, which returns 60.

</details>

**3.** Same function. Does `area(4, floors: 3)` compile?

<details><summary>Answer</summary>

No. `h` is positional and it is missing.

</details>

**4.** Given `void book({required String room, int pax = 2}) {}`

Does `book(pax: 4)` compile?

<details><summary>Answer</summary>

No. `room` is required. `book(room: 'T2031')` is fine, because `pax` has a default.

</details>


---

<a id="null-safety"></a>

## Null safety

*Chapter 2*

`null` means "no value". A normal type can never be null. Add `?` to allow it.

| Code | Meaning |
|---|---|
| `String? note;` | `note` may be null. It starts as `null` |
| `note ?? 'None'` | Use `note`. If it is null, use `'None'` |
| `note?.length` | Get the length. If `note` is null, give null |
| `note!` | "I promise it is not null." Stops with an error if it is |

### Three ways to declare with no value

| Declaration | What happens when you read it |
|---|---|
| `String? a;` | It is `null`. Fine |
| `var b;` | It is `null`. Fine, because Dart gives it no fixed type |
| `String c;` | **Does not compile.** It must be given a value before you use it |

```dart
double? discount;
print(discount ?? 0.5);    // 0.5

var tip;
print(tip ?? 'no tip');    // no tip

int pax;
print(pax);                // ERROR: pax has no value yet
```

> **Trap:** look at the declaration first. A `?` or a plain `var` gives null. A plain type such as `int` with no value gives a compile error.

### Check yourself

**1.** What prints?

```dart
String? table;
print(table ?? 'Counter');
```

<details><summary>Answer</summary>

`Counter`. `table` is null, so `??` uses the right side.

</details>

**2.** What prints?

```dart
String? table = 'B4';
print(table ?? 'Counter');
```

<details><summary>Answer</summary>

`B4`. The left side is not null, so it is used.

</details>

**3.** Does this compile?

```dart
double weight;
print(weight);
```

<details><summary>Answer</summary>

No. `double` cannot be null and `weight` has not been given a value.

</details>


---

<a id="classes"></a>

## Classes in one page

*Chapter 2*

A **class** is the blueprint. An **object** is one thing made from it.

```dart
class Stall {
  String name;
  Stall(this.name);              // constructor
  String label() => 'Stall: $name';
}

class HalalStall extends Stall {       // child class
  HalalStall(super.name);
  @override
  String label() => '${super.label()} (halal)';
}

void main() {
  print(HalalStall('Adam').label());   // Stall: Adam (halal)
}
```

| Word | Meaning |
|---|---|
| `extends` | Make a child class |
| `@override` | Replace the parent's method with your own |
| `super` | The parent |
| `abstract` | A blueprint you cannot make objects from |
| `_name` | Private to this file |

This is why Flutter code looks the way it does: `class MyApp extends StatelessWidget` is a child class, and `build()` is marked `@override`.

### Check yourself

**1.** In `class MyApp extends StatelessWidget`, which class is the parent?

<details><summary>Answer</summary>

`StatelessWidget`.

</details>

**2.** Why does `build()` have `@override` above it?

<details><summary>Answer</summary>

The parent class already declares `build()`. Your class is giving its own version.

</details>


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

<a id="traps"></a>

## Common traps

| Look out for | Remember |
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
