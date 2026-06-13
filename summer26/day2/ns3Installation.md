# Day 2 (Afternoon): ns-3 Installation & Examples

Tuesday, 16 June 2026 — 111 Lampe Dr #200 · 1:15 – 2:15 PM

> Goal: understand what **ns-3** is and why it matters, see how it's installed on Ubuntu (conceptually), then run **real ns-3 simulations in Google Colab** using yesterday's Python — and *see* networks drawn on screen.

> Companion notebook: **`ns3_colab.ipynb`** (open it in Colab — File ▸ Upload notebook).
> Format: explain → **you run / you predict / you change a number** → discuss.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 🗳️ Warm-up (3 min)

*  We can't crash the real internet to test a new idea. So how do networking researchers experiment **safely**?
*  Ever played a game with a "sandbox" or "creative mode"? How is that useful?

**Pair (30 sec):** If you wanted to test a brand-new traffic-light system for a whole city, would you change the real city first — or build a model? Why?

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## What Is ns-3? 🌐

**ns-3** is a free, open-source **network simulator** — a virtual lab where you build networks out of software and watch how data ("packets") moves through them.

*  **Discrete-event simulator:** it models a network as a sequence of events (a packet sent at time 1.0s, received at 1.003s, ...).
*  Simulates **wired and wireless** networks — Wi-Fi, LTE/5G, the internet.

**Why simulate instead of using real equipment?**

| Real testbed | ns-3 simulation |
|---|---|
| Expensive hardware | Free software |
| Hard to scale to 1000s of nodes | Type `nodes.Create(1000)` |
| Risky / safety concerns | Totally safe sandbox |
| Hard to repeat exactly | Perfectly repeatable |

> Researchers use ns-3 for **education**, **R&D of new protocols**, and **performance testing** before touching real networks.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## What Language Does ns-3 Speak? 🗣️

Remember Monday — compiled vs. interpreted?

*  **Core: C++** (compiled). ns-3 simulates millions of low-level events (packets, queues, timing). C++ is compiled to machine code = **fast**, with fine **memory control**. Python would be too slow at that scale.
*  **Also: Python bindings.** Python "talks to" the underlying C++ — easier to write and perfect for learning and quick experiments.

> 💬 **Quick check (vote):** ns-3's *core* is written in which language, and *why*?

<details>
<summary>Answer</summary>

**C++**, for **performance and memory control** — simulating thousands of nodes/packets can't afford an interpreted language's speed penalty. (Python bindings exist for convenience — that's our path today.)

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Installing ns-3 on Ubuntu — Conceptually 🔧

This is the "real researcher" install (we saw it this morning). We'll **look, not do** — because it's slow and fragile for a classroom:

```bash
# Install dependencies (a C++ compiler + Python + build tools)
sudo apt update
sudo apt install g++ python3 cmake ninja-build git

# Download the source code from GitLab
git clone https://gitlab.com/nsnam/ns-3-allinone.git
cd ns-3-allinone
python3 download.py -n ns-3.36

# Configure and BUILD (compile) — can take 20+ minutes!
./ns3 configure --enable-examples --tests
./ns3 build

# Run an example simulation
./ns3 run first
```

> 💬 **Why might this be painful in a 1-hour class with 20 laptops?**

<details>
<summary>Discussion</summary>

Different laptops, different OSes (Windows/Mac), 20-minute compiles ×20 machines, version conflicts, missing dependencies... "works on mine but not yours." This is exactly the problem **Colab** solves.

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## The Shortcut: ns-3 in Colab 🚀

This morning's reveal — **Colab is an Ubuntu machine in the cloud** — means we can install ns-3's **Python bindings** with a single command, and Google does the heavy lifting:

```python
!pip install ns3
```

No laptops to configure. No 20-minute compile. Just write Python (from yesterday!) and run simulations in your browser.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## ✍️ Hands-On: Open the Notebook (40 min)

> **Open `ns3_colab.ipynb` in Colab** (File ▸ Upload notebook, or open from the shared link). Run cells top to bottom with **Shift + Enter**.

We'll go together, but **you drive**. Help your neighbor — raise a hand if a cell errors.

### Step-by-step

| Cell | What you do | The payoff |
|---|---|---|
| **Install** | Run `!pip install ns3` (~1 min) | "ns-3 installed — no Ubuntu setup!" |
| **Import** | `from ns import ns` | The real simulator, now in Python |
| **Line topology** | Run it → **change the number to your age** → re-run | See your nodes appear as dots |
| **Star** ⭐ | Run with 10 spokes → try 5, then 25 | A hub + spokes, *with links drawn* |
| **Grid** 🔲 | Run 10×7 → try a square, then tall-and-skinny | A mesh network you designed |

### 🔮 Predict before you run

*  In the line cell, you write `nodes.Create(12)`. **How many dots will appear?**
*  In the star cell, you set **25 spokes**. **What will the picture look like?**

<details>
<summary>Answers</summary>

*  **12 dots** — one per node.
*  A central hub with **25 lines radiating out** to 25 surrounding nodes — like a Wi-Fi router with 25 devices.

</details>

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

### 🏆 Mini-Challenge — Pick One (in pairs, swap driver each try)

1. **Easy:** Make a star with the number of spokes = people at your table.
2. **Medium:** Build a **square** grid (same rows and columns).
3. **Spicy:** Build a *tall, skinny* grid (e.g. `15, 2`). What real-world network does its shape remind you of?

🗣️ **Share-out:** Each pair shows their favorite network and names a **real-life example** (home Wi-Fi? city cell towers? sensors in a farm? the internet backbone?).

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## 🐛 If a Cell Breaks (troubleshooting)

*  **`pip install` failed or import errors?** Runtime ▸ **Restart runtime**, then run the install cell again.
*  **"name 'ns' is not defined"?** You skipped the import cell — run cells **in order** from the top.
*  **Plot didn't show?** Re-run the cell; make sure the helper cell above it ran first.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>

## Wrap-up & Bridge to Wednesday

Today you:

*  Learned **ns-3** = a safe, free, repeatable virtual lab for networks 🌐
*  Saw *why* its core is **C++** (speed) but we used **Python** bindings (easy)
*  Saw the real Ubuntu install **conceptually** — then ran ns-3 for real in **Colab** with `!pip install ns3`
*  Built and *saw* **line, star, and grid** networks

**Tomorrow (Wed) with Jiayuan — the ns-3 Web Platform:**

*  You'll run **C++** ns-3 examples right in the browser (no install — like today, but the C++ path).
*  Then Python examples again in Colab.

So by end of camp you'll have run ns-3 **three ways**: Python in Colab (today), C++ on the Web Platform, and you'll *understand* the "real" Ubuntu install even if you never have to fight with it. 💪

💡 *Optional tonight:* in the notebook, find the weirdest-looking network you can make by changing numbers. Bring it tomorrow!
