[Back to the study plan](../README.md)

# Step 1: Flutter, variables and strings

- [Flutter and Dart](#flutter-dart)
- [main(), variables and types](#variables)
- [Strings and numbers](#strings-numbers)

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

**Move on when** you can say the difference between `var`, `final` and `const`, and between `int.parse` and `double.parse`.

[Next: Step 2](2-collections-loops.md) | [Back to the study plan](../README.md)
