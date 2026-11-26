# Python Learning Guide

> A phase-by-phase guide to learning Python — from your first script to a working project in the track you choose (data & AI, backend, or automation). Built around exit criteria and proof of work, not topic lists. Written for beginners starting from zero.

---

## Table of Contents

1. [The Three Rules](#1-the-three-rules)
2. [Before You Start](#2-before-you-start)
3. [The Roadmap](#3-the-roadmap)
   - [3.1 Phase 1: Core Language Fundamentals](#31-phase-1-core-language-fundamentals)
   - [3.2 Phase 2: Data Structures & Pythonic Code](#32-phase-2-data-structures--pythonic-code)
   - [3.3 Phase 3: OOP & Intermediate Python](#33-phase-3-oop--intermediate-python)
   - [3.4 Phase 4: Tools of a Real Developer](#34-phase-4-tools-of-a-real-developer)
   - [3.5 Phase 5: Choose Your Track](#35-phase-5-choose-your-track)
   - [3.6 Phase 6: Capstone Project](#36-phase-6-capstone-project)
4. [How to Actually Study](#4-how-to-actually-study)
5. [Recommended Resources](#5-recommended-resources)
6. [Common Mistakes](#6-common-mistakes)
7. [What Comes Next](#7-what-comes-next)
8. [Progress Checklist](#8-progress-checklist)

---

## 1. The Three Rules

1. **You learn Python by writing Python.** Watching or reading is not learning. If a study session produced no code, it was entertainment.
2. **Every phase ends with something you built.** Not "I completed the course" — "I built this, and it's on GitHub."
3. **Move on when you hit the exit criteria, not when you feel ready.** You will never feel ready.

You don't need prior programming experience. You do need a laptop, consistency, and a willingness to write code every day, even for 30 minutes.

---

## 2. Before You Start

### 2.1 Why Python?

Python reads close to plain English, has a huge ecosystem, and is the dominant language in data science, machine learning, AI, automation, and scripting. It's also widely used for backend web development. You can be productive in it quickly, which makes it one of the best first languages.

> **Honest caveat:** Python being easy to start is also its trap — it lets you write bad code that still works. This guide pushes you toward clean structure, testing, and tooling early. Also, Python is not the right tool for everything: mobile apps and performance-critical systems usually call for other languages. Pick based on your goal, not hype.

### 2.2 Set Up Your Environment

1. Install the latest stable **Python 3** from [python.org](https://www.python.org/downloads/). Confirm with `python --version` (or `python3 --version` on macOS/Linux).
2. Choose an editor: **VS Code** with the Python extension, or **PyCharm Community Edition**.
3. Learn to create a **virtual environment** — one per project, from day one:
   ```bash
   python -m venv venv
   source venv/bin/activate   # macOS/Linux
   venv\Scripts\activate      # Windows
   ```
4. Install **Git** and create a GitHub account.

Need help with VS Code? See the [VS Code Setup Guide](./vscode-setup-guide.md), specifically [Section 8.2 (Python / Data Science)](./vscode-setup-guide.md#82-python--data-science).

**Exit criteria:** You can create a virtual environment, activate it, and run a "Hello, World" script from both the terminal and your editor.

---

## 3. The Roadmap

Six phases, in order. Phases 1–4 are the same for everyone. In Phase 5 you pick a track. Don't skip ahead — each phase builds on the last.

### 3.1 Phase 1: Core Language Fundamentals

**Learn:**
- Variables, data types (`int`, `float`, `str`, `bool`), operators
- Input and output (`input()`, `print()`, f-strings)
- Conditionals (`if`, `elif`, `else`)
- Loops (`for`, `while`, `break`, `continue`, `range()`)
- Functions (parameters, return values, default arguments)
- Basic lists, tuples, and dictionaries
- Reading error messages and tracebacks

**Practice:** Solve 30–50 small problems — FizzBuzz, palindrome check, factorial, prime numbers, reversing a string, counting word frequency.

**Where to practice:**
- [CodingBat Python](https://codingbat.com/python) — short, instant-feedback warm-ups
- [Exercism Python track](https://exercism.org/tracks/python) — the early exercises, with tests included
- [HackerRank Python domain](https://www.hackerrank.com/domains/python) — the "Introduction" challenges
- [Python Tutor](https://pythontutor.com) — visualize your code line by line when it confuses you
- [MOOC.fi Python Programming](https://programming-25.mooc.fi/) — the first few parts

**Build:** A **number guessing game** and a **command-line calculator**.

**Exit criteria:** You can solve a beginner-level problem from a blank file *without* looking up the syntax on every line.

---

### 3.2 Phase 2: Data Structures & Pythonic Code

**Learn:**
- Lists, dictionaries, sets, tuples — and when to use which
- Slicing, sorting, and string methods
- **List/dict/set comprehensions**
- Functions in depth (`*args`, `**kwargs`, scope, lambda)
- Modules and imports, writing your own module
- **File handling** (`open`, `with`, `pathlib`) — text, CSV, JSON
- **Exception handling** (`try/except/finally`, raising your own exceptions)
- A tour of the standard library: `collections`, `datetime`, `random`, `os`, `json`, `csv`

**Where to practice:**
- [Exercism Python track](https://exercism.org/tracks/python) — medium-level exercises
- [LeetCode](https://leetcode.com) — easy problems tagged *Array*, *Hash Table*, and *String*
- [Codewars](https://www.codewars.com) — small katas, good for learning Pythonic idioms
- [Advent of Code](https://adventofcode.com) — puzzles from past years, solved in Python

**Build:** An **Expense Tracker** or **Contact Book** that saves data to a JSON or CSV file and handles bad input gracefully.

**Exit criteria:** You can pick the right data structure for a problem and justify your choice. You can rewrite a loop as a comprehension and explain which is clearer.

---

### 3.3 Phase 3: OOP & Intermediate Python

**Learn:**
- Classes and objects, `__init__`, `self`
- Encapsulation and properties
- Inheritance and `super()`
- Magic/dunder methods (`__str__`, `__repr__`, `__eq__`, `__len__`)
- **Dataclasses**
- **Type hints**
- Iterators and **generators** (`yield`)
- **Decorators** and **context managers**
- Basic concurrency concepts — threads, processes, and `asyncio` at an idea level only

**Where to practice:**
- [MOOC.fi](https://programming-25.mooc.fi/) — the object-oriented programming parts
- [Exercism Python track](https://exercism.org/tracks/python) — exercises that need classes
- [HackerRank Python domain](https://www.hackerrank.com/domains/python) — the OOP and decorator challenges
- Your own code — pick a real-world object around you and model it

**Build:** A **Library Management System** or **Inventory Manager** using multiple classes, type hints, and file persistence.

**Exit criteria:** You can explain, in your own words and with a code example, what a decorator does and why you'd use a generator instead of a list.

---

### 3.4 Phase 4: Tools of a Real Developer

Writing code is half the job. The other half is the toolchain.

**Learn:**
- **Virtual environments and dependency management** — `pip`, `requirements.txt`, `pyproject.toml` (and optionally `uv`)
- **Git and GitHub** — commit, branch, merge, pull request
- **Testing with `pytest`** — writing and running unit tests
- Debugging with your IDE's debugger or `pdb` (not just `print()`)
- **Logging** with the `logging` module
- **Formatting and linting** — `ruff` or `black`
- Project structure — packages, `__init__.py`, a clean repo layout

**Where to practice:**
- [GitHub Skills](https://skills.github.com) — interactive Git and GitHub courses
- Your own Exercism solutions — write extra `pytest` tests for them
- Your older projects — add tests, a `requirements.txt`, and a formatter to each
- Open-source issues labelled *good first issue* — once you're comfortable

**Build:** Take one earlier project, restructure it as a proper package, add `pytest` tests, and push it with a clear README.

**Exit criteria:** A stranger can clone your repo, create a virtual environment, install dependencies, run the tests, and see your project work.

---

### 3.5 Phase 5: Choose Your Track

Pick **one** track. Finish it before touching another.

#### Track A: Data & AI

**Learn:**
- **Jupyter notebooks**
- **NumPy** and **pandas** — loading, cleaning, grouping, merging data
- **Matplotlib** and/or **Seaborn** — visualization
- **SQL** fundamentals — `SELECT`, `JOIN`, `GROUP BY`
- Intro to **scikit-learn** — train/test split, a basic model, evaluation

**Where to practice:**
- [Kaggle Learn](https://www.kaggle.com/learn) — short, hands-on micro-courses
- [Kaggle datasets](https://www.kaggle.com/datasets) — find real data and explore it
- [SQLBolt](https://sqlbolt.com) and [SQLZoo](https://sqlzoo.net) — SQL fundamentals
- [pandas documentation](https://pandas.pydata.org/docs/) — start with the "10 minutes to pandas" guide

**Build:** An **end-to-end data analysis** — pick a real dataset, clean it, analyze it, visualize it, and write up your findings in a notebook with a clear conclusion.

#### Track B: Backend & Web

**Learn:**
- **HTTP and REST** concepts — methods, JSON, status codes
- **FastAPI** or **Flask** — routes, request validation, error handling
- **SQL** and an ORM (**SQLAlchemy**)
- Authentication basics
- Intro to **Docker**

**Where to practice:**
- [FastAPI tutorial](https://fastapi.tiangolo.com/tutorial/) — official, step-by-step
- [Flask documentation](https://flask.palletsprojects.com) — its quickstart and tutorial
- [SQLBolt](https://sqlbolt.com) and [SQLZoo](https://sqlzoo.net) — SQL fundamentals
- Postman or `curl` — test every endpoint you build

**Build:** A **REST API** for a to-do app or book catalog, with a real database, tests, and auto-generated docs.

#### Track C: Automation & Scripting

**Learn:**
- Working with files, folders, and the OS (`pathlib`, `shutil`, `subprocess`)
- **APIs with `requests`** — fetching and processing JSON
- Web scraping (`BeautifulSoup`) — **check a site's terms of service and `robots.txt` first**
- Browser automation (Playwright or Selenium)
- Scheduling scripts (cron, Task Scheduler)
- Sending emails and working with spreadsheets/PDFs

**Where to practice:**
- [Automate the Boring Stuff with Python](https://automatetheboringstuff.com) — free to read online; project-based
- Your own routine — automate something you actually do every week
- Public APIs — pick one and build a small tool on top of it

**Build:** A **tool that saves you real time** — an automated report, a file organizer, a price tracker, or a bulk renamer — that you actually use.

**Exit criteria (all tracks):** Your project works end to end on real data or real input, handles errors sensibly, has at least a few tests, and has a README explaining how to run it.

---

### 3.6 Phase 6: Capstone Project

Build **one** project that is yours — not a tutorial clone. It should:

- Solve a real problem you or someone you know actually has
- Use the skills from your chosen track, plus tests and a clean project structure
- Have a clean README with screenshots or output examples, setup steps, and a short explanation of your design decisions
- Be deployed, published, or easily runnable

**Where to practice:**
- Your own life — build for a real problem you or someone you know has
- Hackathons and build challenges — a deadline forces you to finish
- Open-source contributions — read real code, then improve it
- GitHub and LinkedIn — share the project and ask for feedback

**Exit criteria:** You can walk someone through the project and explain *why* you made each major decision.

---

## 4. How to Actually Study

### 4.1 Daily Structure (About 90 Minutes)

| Time | Activity |
|---|---|
| 15 min | Review yesterday's code — can you still explain it? |
| 30 min | Learn one new concept (read or watch, with the code open) |
| 40 min | Write code applying that concept, *without* copy-pasting |
| 5 min | Commit to GitHub and write one line about what you learned |

If you only have 30 minutes, skip the learning and just write code.

> **Build your own structure:** This is a starting point, not a rule. If it doesn't fit your schedule, energy, or learning style, design your own. Keep the loop — review, learn, build, record — and change everything else: the timings, the order, the total length. A routine you'll actually follow beats a perfect one you'll abandon.

### 4.2 Techniques That Actually Work

- **Type it, don't paste it.** Typing builds muscle memory and forces you to read every line.
- **Predict, then run.** Before executing code, guess the output. Wrong guesses are where learning happens.
- **Use the REPL.** Open a Python shell and test small ideas instantly — it's the fastest feedback loop you have.
- **Break things on purpose.** Remove a colon, change a type, and read the traceback.
- **Explain it out loud.** If you can't explain a concept simply, you don't understand it yet.
- **Re-solve old problems.** A week later, solve the same problem again from scratch.

### 4.3 Avoiding Tutorial Hell

Tutorial hell is when you keep watching courses but can't build anything alone. Signs you're in it:

- You've finished three courses but have zero projects of your own
- You feel productive, but couldn't build anything without the video open
- You keep switching resources instead of finishing one

**The fix:** After every concept, close the tutorial and build something small with it. One course finished beats five courses started.

> **A note on AI assistants:** Tools like ChatGPT, Copilot, and Claude are useful for explaining errors and concepts. But if you let them write your solutions, you're skipping the exact struggle that builds skill. Try the problem first. Use AI to understand, not to avoid understanding.

---

## 5. Recommended Resources

Pick **one primary resource** per phase. Don't collect them all.

**Free, structured courses**
- [MOOC.fi Python Programming](https://programming-25.mooc.fi/) (University of Helsinki) — exercise-driven and beginner-friendly. The edition year in the URL changes, so check [mooc.fi](https://www.mooc.fi) for the latest.
- [CS50's Introduction to Programming with Python](https://cs50.harvard.edu/python/) (Harvard) — lectures, notes, and problem sets, free
- [The official Python tutorial](https://docs.python.org/3/tutorial/) — the canonical reference, best after Phase 1

**Books**
- *Automate the Boring Stuff with Python* by Al Sweigart — practical and beginner-friendly
- *Python Crash Course* by Eric Matthes — projects-first
- *Fluent Python* by Luciano Ramalho — read this *after* Phase 3, not before

**Reference**
- [Real Python](https://realpython.com) — practical articles on almost any Python topic
- [Python documentation](https://docs.python.org/3/)

---

## 6. Common Mistakes

1. **Not using virtual environments.** Installing everything globally leads to version conflicts you'll spend hours debugging. Use `venv` per project, from day one.
2. **Learning libraries before the language.** If you jump to pandas or Django without solid Python, you'll copy code you can't debug.
3. **Following outdated tutorials.** Python 2 reached end of life in 2020. If a tutorial uses `print "hello"` without parentheses, close it.
4. **Only ever using notebooks.** Jupyter is great for exploration, but learn to write real `.py` scripts and modules too.
5. **Never reading tracebacks.** The error tells you exactly where and what went wrong. Read it from the bottom up, then Google.
6. **Not using Git until "later."** Start from day one.
7. **Letting AI write your solutions.** You'll finish exercises and learn nothing.
8. **Studying in bursts.** Daily 45 minutes beats a weekend marathon.
9. **Comparing your week 2 to someone else's year 3.**

---

## 7. What Comes Next

Once you've finished this path, you have the foundation to go deeper in your track. Depending on your goal, explore data structures and algorithms in depth, system design basics, Docker and cloud platforms (AWS, Azure, or GCP), data engineering tools (Airflow, Spark, dbt), or machine learning and LLM engineering.

---

## 8. Progress Checklist

- [ ] Environment set up, virtual environment works, Hello World runs (Section 2)
- [ ] Phase 1: Fundamentals + 30 practice problems + 2 small projects
- [ ] Phase 2: Data structures, file handling, exceptions + file-based project
- [ ] Phase 3: OOP, decorators, generators + multi-class project
- [ ] Phase 4: Git, `pytest`, project structure + one tested project on GitHub
- [ ] Phase 5: Track chosen and a working track project built
- [ ] Phase 6: Capstone project with README

---

*Maintained as a living document — update as tooling evolves. Found something outdated or unclear? Open an issue or a PR.*
