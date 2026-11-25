[Back to the study plan](../README.md)

# Step 2: Collections and loops

- [List, Set and Map](#collections)
- [Choices and loops](#control)

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

**Move on when** you can say how to tell a List, a Set and a Map apart by their brackets.

[Next: Step 3](3-functions-null-classes.md) | [Back to the study plan](../README.md)
