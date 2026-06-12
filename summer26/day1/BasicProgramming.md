# Day 1: Basic Programming & Python

Monday, 15 June 2026 — 111 Lampe Dr #200

**Part 1 (10:00 – 10:45 AM):** Basic Programming Concepts <br>
**Part 2 (2:45 – 4:00 PM):** Introduction to Python + Quiz

> Format: short explanation → **you try it** → discuss. Almost every section has something for YOU to do. No experience needed!

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

# Part 1: Basic Programming Concepts (45 min)

## 🗳️ Warm-up Poll (3 min)

Raise your hand:

*  Who has written a program before (any language)?
*  Who has used ChatGPT or another AI to write code?
*  Who has played Minecraft with command blocks / redstone? (That's programming!)

**Turn to your neighbor (30 seconds):** What do you think a "program" actually is?

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 🤖 Activity: The Human Robot (10 min)

One instructor becomes a **robot**. The robot only does EXACTLY what you say — nothing more.

**Your mission:** As a class, give the robot step-by-step instructions to walk to the door and open it.

Rules:

*  One instruction at a time ("take a step" — how big? which direction?)
*  The robot takes everything *literally*
*  If an instruction is ambiguous, the robot does the *worst* possible interpretation 😈

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

**Debrief — what did we just learn?**

*  Computers require steps of instructions, or **algorithms**, that are very specific.
*  Computers do not understand natural languages (such as English) — they need instructions with **zero ambiguity**.
*  Order matters. Detail matters. ("open door" before "walk to door" = crash)

This is 90% of what programming is: breaking a problem into tiny, exact, ordered steps.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Problem → Algorithm → Program

| | What it is | Example |
|---|---|---|
| **Problem** | What we need to solve | "I want the computer to greet me" |
| **Algorithm** | Step-by-step plan (in English/pseudocode) | 1. Get name → 2. Print "Hello, name!" |
| **Program** | The algorithm written in a programming language | `print("Hello, " + name)` |

The software is **not** the problem — the software is **solving** a problem.

<br>

Algorithm format (pseudocode):

```
Algorithm greeting
Input  : a person's name
Output : a textual greeting

ask for the name
print "Hello, " followed by the name
```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

### ✍️ Your Turn: Write an Algorithm (7 min)

**In pairs**, write pseudocode for ONE of these (pick the one you like):

1. Decide whether to bring an umbrella today
2. Find the largest of 3 numbers
3. Make a peanut butter & jelly sandwich (robot-proof version!)

```
Algorithm ____________
Input  : ____________
Output : ____________

step 1: ...
step 2: ...
```

We'll ask 2–3 pairs to read theirs out loud — and the class tries to break it by finding ambiguity. 🔍

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## How Do Computers Understand Us?

*  **Machine language**: 0s and 1s — what the processor actually runs. Very hard for humans.
*  **Programming languages** (Python, C++, Java...): mostly English + math. Humans write these.
*  Something has to **translate** between the two:

| | Compiled (C/C++, Java) | Interpreted (Python) |
|---|---|---|
| Translation | All at once, **before** running → creates an executable | Line-by-line, **while** running |
| If you change code | Must re-compile | Just run again |
| Speed | Usually faster | Usually slower, but easier to experiment |
| This week | C/C++ session (next!), ns-3 is C++ | This afternoon + Colab |

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

### 🗳️ Quick Check (vote A / B / C / D)

**Q: What is the difference between an interpreted and a compiled programming language?**

A. An interpreted language has each line converted to native instructions as it is run. Compiled languages convert everything to an executable at once.

B. Interpreted languages are used for web-based applications. Compiled languages are for apps like iOS, Android, and Windows.

C. Interpreted languages are a previous generation of languages before the creation of compiled languages.

D. Interpreted languages are based on transformations of values. Compiled languages are created using step-by-step algorithms.

<details>
<summary>Answer</summary>

**A** — that's the core difference. (B is a common misconception!)

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Variables: Boxes with Labels 📦

*  A **variable** = a named box in the computer's memory that stores a value.
*  Every variable has a **name** (you choose it) and a **type** (what kind of data is inside).

Common types in (almost) every language:

| Type | Holds | Example |
|---|---|---|
| integer | whole numbers | `42`, `-7` |
| float / double | decimals | `3.14` |
| boolean | true / false | `True` |
| string | text | `"hello"` |

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

### ✍️ Your Turn: Label the Boxes (3 min)

Shout out the **type** for each:

1. Your age → ______
2. Your name → ______
3. The price of boba tea → ______
4. "Is it raining?" → ______
5. Number of students in this room → ______
6. Your phone number 🤔 → ______

<details>
<summary>Discussion: #6 is sneaky!</summary>

A phone number is usually stored as a **string**! You never do math with it, and it can start with 0 or contain `+` and `-`.

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Part 1 Wrap-up

*  Algorithm = exact, ordered steps. Program = algorithm in a real language.
*  Compiled vs. interpreted = *when* translation happens.
*  Variables = labeled boxes with types.

**Next up (10:45):** C/C++ — see these ideas in a compiled language.
**This afternoon (2:45):** We make all of this REAL with Python. 🐍

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

# Part 2: Introduction to Python (75 min)

## Setup: Google Colab (5 min)

No installation needed — Python runs in your browser:

1. Go to [https://colab.google/](https://colab.google/)
2. Click **New Notebook** (sign in with a Google account)
3. Type into the cell and press **Shift + Enter** to run:

```python
print("Hello, Summer Camp!")
```

✋ Raise your hand when you see the output. Help your neighbor if you're done!

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Why Python? 🐍

*  Created by Guido van Rossum (1991). Goal: easy to read, powerful, beginner-friendly.
*  Used by Google, Netflix, NASA — and for AI, data science, and **network simulation (ns-3 has Python bindings — Wednesday!)**.
*  Same idea, different languages:

```python
# Python
user_age = 25
user_name = "Alice"
```

```java
// Java
int userAge = 25;
String userName = "Alice";
```

```cpp
// C++ (you saw this morning!)
int userAge = 25;
std::string userName = "Alice";
```

Python is **dynamically typed** — no need to declare the type. Python figures it out.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Variables & print (10 min)

```python
x = 5             # int
name = "Ana"      # str
pi = 3.14         # float
is_valid = True   # bool

print(x)
print("My name is", name)
print(f"{name} says pi is about {pi}")   # f-string: put variables inside text!
```

<br>

### 🔮 Predict the Output!

**Before running it**, write down what you think each line prints. *Then* run it. Score yourself!

```python
a = 7
b = 3
print(a + b)
print("a + b")
print("a" + "b")
print(f"a + b = {a + b}")
```

<details>
<summary>Answers</summary>

```
10
a + b
ab
a + b = 10
```

Quotes = text, no quotes = the variable. `+` on strings glues them together!

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Operators (10 min)

| Arithmetic | Comparison | Logical |
|---|---|---|
| `+` `-` `*` `/` | `==` equal | `and` |
| `%` remainder | `!=` not equal | `or` |
| `**` power | `>` `<` `>=` `<=` | `not` |

⚠️ `=` assigns, `==` compares. Mixing these up is the #1 beginner bug!

<br>

### ✍️ Challenge: Summer Math (5 min)

In your notebook, use Python to calculate:

1. How many **seconds** are in this 5-day camp? (5 days × 24 h × 60 min × 60 s)
2. You have 100 candies for 7 campers. How many does each get (`//`), and how many are left over (`%`)?
3. Is `2 ** 10` bigger than `10 ** 2`? Have Python print `True` or `False` *without* you doing the math.

<details>
<summary>Answers</summary>

```python
print(5 * 24 * 60 * 60)    # 432000
print(100 // 7, 100 % 7)   # 14 2
print(2 ** 10 > 10 ** 2)   # True (1024 > 100)
```

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Making Decisions: if / elif / else (12 min)

```python
having_fun = "yes"

if having_fun == "yes":
    print("Glad you're having fun!")
elif having_fun == "kind of":
    print("We'll get there!")
else:
    print("Talk to us at lunch :(")
```

*  Starts with `if` + condition + colon `:`
*  **Indentation matters!** The indented block runs only if the condition is `True` (no `{ }` like C/Java)

<br>

### 🐛 Find the Bugs! (3 min)

This code has **3 bugs**. Find them with your neighbor — first pair to find all 3 wins 🍬

```python
temperature = 95
if temperature = 90
print("It's hot! Stay hydrated")
```

<details>
<summary>Answers</summary>

1. `=` should be `==` (or `>=` — comparing, not assigning)
2. Missing colon `:` at the end of the `if` line
3. `print` must be indented

```python
temperature = 95
if temperature >= 90:
    print("It's hot! Stay hydrated")
```

</details>

<br>

### ✍️ Your Turn: Grade Calculator (5 min)

Write a program that:

1. Defines a variable `score` with a value between 0 and 100
2. Prints the grade:  90+ → `"A"`, 80–89 → `"B"`, 70–79 → `"C"`, below 70 → `"Keep practicing!"`

Bonus: get the score from the user with `score = int(input("Enter score: "))`

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Loops: Make the Computer Repeat (12 min)

```python
# for loop: repeat a known number of times
for i in range(5):
    print("Hello number", i)

# while loop: repeat as long as a condition is True
countdown = 3
while countdown > 0:
    print(countdown)
    countdown = countdown - 1
print("Liftoff! 🚀")
```

<br>

### 🔮 Predict the Output!

```python
for i in range(3):
    print(i * "🐍")
```

<details>
<summary>Answer</summary>

```

🐍
🐍🐍
```

`range(3)` gives 0, 1, 2 — and multiplying a string repeats it! (Line 1 is empty: 0 snakes.)

</details>

<br>

### ✍️ Your Turn: Pick One (5 min)

1. **Easy:** Print the numbers 1 to 10, but say `"BUZZ"` instead of any number divisible by 3 (hint: `%`)
2. **Spicy:** Print this triangle using one loop:
   ```
   *
   **
   ***
   ****
   *****
   ```

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Lists: Many Values, One Variable (5 min)

```python
campers = ["Ana", "Ben", "Cleo"]
print(campers[0])        # "Ana"  — counting starts at 0!
print(len(campers))      # 3
campers.append("Dev")    # add to the end

for person in campers:
    print(f"Welcome, {person}!")
```

Also exist (we'll meet them again this week): **tuple** (can't change), **set** (no duplicates), **dictionary** (key → value pairs).

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 🎮 Mini-Project: Number Guessing Game (15 min, in pairs)

Build it step by step — run after **every** step:

```python
import random
```

*  **Step 1:** Make the computer pick a secret number 1–20: `secret = random.randint(1, 20)`
*  **Step 2:** Ask the player for a guess: `guess = int(input("Your guess: "))`
*  **Step 3:** Use `if/elif/else` to print `"Too high!"`, `"Too low!"`, or `"You got it! 🎉"`
*  **Step 4:** Wrap it in a `while` loop so the player keeps guessing until correct
*  **Step 5 (bonus):** Count the number of guesses and print it at the end
*  **Step 6 (super bonus):** Only allow 5 guesses before "Game over"

**Pair rule:** One person types (driver), the other navigates. **Swap after each step!**

<details>
<summary>One possible solution (instructors: reveal at the end)</summary>

```python
import random

secret = random.randint(1, 20)
tries = 0
guess = 0

while guess != secret:
    guess = int(input("Your guess: "))
    tries = tries + 1
    if guess > secret:
        print("Too high!")
    elif guess < secret:
        print("Too low!")
    else:
        print(f"You got it in {tries} tries! 🎉")
```

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 📝 Quiz Time! (10 min)

Answer on your own first, then we vote and discuss each one.

**Q1.** What does this print?

```python
x = 10
y = "10"
print(x == y)
```

A. `True`  B. `False`  C. `10`  D. Error

<br><br><br><br>

**Q2.** Which one is a valid Python `if` statement?

A. `if x > 5 then print("big")`
B. `if (x > 5) { print("big") }`
C. `if x > 5: print("big")`
D. `if x > 5 print("big")`

<br><br><br><br>

**Q3.** How many times does this loop print?

```python
for i in range(2, 6):
    print("hi")
```

A. 2  B. 4  C. 5  D. 6

<br><br><br><br>

**Q4.** What is `17 % 5`?

A. 3  B. 2  C. 3.4  D. 12

<br><br><br><br>

**Q5.** What does `campers[1]` give you if `campers = ["Ana", "Ben", "Cleo"]`?

A. `"Ana"`  B. `"Ben"`  C. `"Cleo"`  D. Error

<details>
<summary>Quiz Answers</summary>

1. **B** — `10` (int) and `"10"` (string) are different types, so not equal
2. **C** — colon, no braces, no `then`
3. **B** — `range(2, 6)` gives 2, 3, 4, 5 → 4 times (end is not included!)
4. **B** — 17 ÷ 5 = 3 remainder **2**
5. **B** — counting starts at 0, so index 1 is the second item

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Wrap-up & What's Next

Today you learned the building blocks of **every** programming language:

*  Variables & types 📦
*  Operators ➕
*  Conditionals (if/elif/else) 🔀
*  Loops (for/while) 🔁
*  Lists 📋

**Tomorrow:** Hardware, simulators, digital twins, and your first look at **ns-3** — the network simulator we'll use all week. The Python you wrote today is exactly what you'll use to drive simulations!

💡 **Tonight's optional challenge:** Modify your guessing game so the *computer* guesses *your* number. Show us tomorrow! 🏆
