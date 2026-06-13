# Day 2 (Morning): Introduction to Ubuntu & Google Colab

Tuesday, 16 June 2026 — 111 Lampe Dr #200 · 10:45 – 11:45 AM

> Goal: understand what an operating system is, why researchers run ns-3 on **Ubuntu/Linux**, meet the **terminal**, and discover that **Google Colab is secretly an Ubuntu machine** — which is how we'll run real ns-3 this afternoon without installing anything.

> Format: short explanation → **you try / you predict** → discuss.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 🗳️ Warm-up (3 min)

Raise your hand:

*  Who has used **Windows**? **macOS**? Ever heard of **Linux**?
*  Who has seen a "black screen with text" where people type commands (in a movie or in real life)?

**Turn to your neighbor (30 sec):** What is an *operating system*? What does it actually do?

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## What Is an Operating System? 🧠

The **operating system (OS)** is the software that runs your whole computer — it manages the hardware (CPU, memory, disk, network) and lets your programs run.

| OS | You've probably seen it on... |
|---|---|
| **Windows** | Most laptops/PCs |
| **macOS** | MacBooks, iMacs |
| **Linux** | Servers, supercomputers, Android phones, *and research computers* |

**Ubuntu** is the most popular **flavor of Linux** — free, open-source, and the standard choice for science and networking research.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Why Do Researchers Use Ubuntu/Linux? 🐧

*  **Free & open** — no license cost, you can see and change everything.
*  **Powerful terminal** — automate anything by typing commands.
*  **It's what the tools expect** — ns-3, AI libraries, and most research software are built and tested on Linux first.
*  **It runs the world** — the majority of internet servers and the top supercomputers run Linux.

> 💬 **Think:** Why might a "type-the-commands" interface be *more* powerful than clicking buttons, even though it looks harder?

<details>
<summary>Discussion</summary>

Typed commands can be **saved, repeated, and shared**. You can run 1000 steps with one script, send the exact commands to a teammate, or re-run last month's experiment perfectly. Clicking buttons can't be automated or reproduced as easily.

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## The Terminal: Talking to the Computer with Words ⌨️

The **terminal** (or "command line") is where you type commands instead of clicking. Remember yesterday's *Human Robot* — exact, ordered instructions? Same idea here.

These are the everyday Ubuntu commands. We'll **read them together** now, and you'll **actually run them in Colab** in a few minutes.

| Command | What it does | Example |
|---|---|---|
| `pwd` | **p**rint **w**orking **d**irectory (where am I?) | `pwd` |
| `ls` | **l**i**s**t files in this folder | `ls` |
| `cd` | **c**hange **d**irectory (move into a folder) | `cd workspace` |
| `mkdir` | **m**a**k**e a new **dir**ectory | `mkdir camp` |
| `sudo apt install` | install a program (the **s**uper-**u**ser **do** "admin" command) | `sudo apt install git` |

> ⚠️ `sudo` = "do this as administrator." It's powerful — like having the master key. Researchers use it to install software for everyone on the machine.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

### 🔮 Predict the Command (3 min)

For each goal, what command would you type? Shout it out.

1. Find out which folder you're currently in → ______
2. See what files are here → ______
3. Make a folder called `mycamp` → ______
4. Go into that folder → ______

<details>
<summary>Answers</summary>

1. `pwd`  2. `ls`  3. `mkdir mycamp`  4. `cd mycamp`

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## How ns-3 Gets Installed on Ubuntu (the researcher's way) 🔧

This is what the *real* install looks like — the steps researchers run on an Ubuntu machine. We'll look at this **conceptually** (you don't have to do it):

```bash
# 1. Install all the tools ns-3 needs
sudo apt update
sudo apt install g++ python3 cmake ninja-build git

# 2. Download ns-3's source code
git clone https://gitlab.com/nsnam/ns-3-allinone.git

# 3. Configure and build (compile) it — this can take 20+ minutes!
./ns3 configure --enable-examples
./ns3 build
```

> 💬 **Notice:** Step 1 installs a **C++ compiler** (`g++`) *and* **Python**. Why both? (Hint: remember Monday — what languages does ns-3 speak?)

<details>
<summary>Answer</summary>

ns-3's core is **C++** (needs `g++` to compile), but it also offers **Python bindings**. That's exactly why yesterday we learned both languages! This afternoon we'll use the **Python** path.

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## So... Do We Have to Install All That? Nope. 😎

That full install is powerful but **slow and fragile** for a classroom — long compile times, version conflicts, "works on my laptop but not yours."

### 💡 The reveal: **Google Colab IS an Ubuntu machine**

Every Colab notebook runs on a real **Ubuntu computer in Google's cloud**. When you put a `!` in front of a command in a Colab cell, it runs that **exact Ubuntu command** — the same ones we just learned.

```python
!pwd            # where are we? (on Google's Ubuntu machine)
!ls             # what files are here?
!pip install ns3   # install ns-3 — Google does the hard part!
```

So we get all the power of Ubuntu, with **zero install on your laptop**.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## ✍️ Hands-On: Your First Ubuntu Commands in Colab (10 min)

1. Go to [https://colab.google/](https://colab.google/) → **New Notebook** (sign in with a Google account)
2. In a cell, type and run (**Shift + Enter**) each of these — one per cell:

```python
!pwd
```
```python
!ls
```
```python
!mkdir mycamp
!ls
```

**🔮 Predict before running the third one:** what will `!ls` show *after* you make the folder?

<details>
<summary>Answer</summary>

You'll see `mycamp` appear in the list! You just created an Ubuntu folder on Google's machine — the same `mkdir` + `ls` from our table, now real.

</details>

3. **Bonus:** try `!cat /etc/os-release` — it literally prints "Ubuntu"! Proof of where you are. 🐧

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Wrap-up & Bridge to This Afternoon

*  An **OS** runs your computer; **Ubuntu** is the Linux flavor researchers use.
*  The **terminal** = giving the computer exact typed instructions (`pwd`, `ls`, `cd`, `mkdir`, `sudo apt install`).
*  Installing ns-3 "for real" on Ubuntu works but is slow/fragile.
*  **Colab is Ubuntu in the cloud** → `!pip install ns3` does the hard part for us.

**Next session (1:15 PM — ns-3 Installation & Examples):** we open a ready-made Colab notebook, run `!pip install ns3`, and build *real* networks with the Python you learned yesterday — and *see* them drawn on screen. 🌐
