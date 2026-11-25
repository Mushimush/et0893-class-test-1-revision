[Back to the study plan](../README.md)

# Step 3: Functions, null safety and classes

- [Functions and parameters](#functions)
- [Null safety](#null-safety)
- [Classes in one page](#classes)

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

**Move on when** you can say which values need a name in a function call.

[Next: Step 4](4-widgets-buttons.md) | [Back to the study plan](../README.md)
