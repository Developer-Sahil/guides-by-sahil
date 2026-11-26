# Java Learning Guide

> A phase-by-phase guide to learning Java — from your first program to a working REST API. Built around exit criteria and proof of work, not topic lists. Written for beginners starting from zero.

---

## Table of Contents

1. [The Three Rules](#1-the-three-rules)
2. [Before You Start](#2-before-you-start)
3. [The Roadmap](#3-the-roadmap)
   - [3.1 Phase 1: Core Language Fundamentals](#31-phase-1-core-language-fundamentals)
   - [3.2 Phase 2: Object-Oriented Programming](#32-phase-2-object-oriented-programming)
   - [3.3 Phase 3: Intermediate Java](#33-phase-3-intermediate-java)
   - [3.4 Phase 4: Tools of a Real Developer](#34-phase-4-tools-of-a-real-developer)
   - [3.5 Phase 5: Databases & Backend Basics](#35-phase-5-databases--backend-basics)
   - [3.6 Phase 6: Capstone Project](#36-phase-6-capstone-project)
4. [How to Actually Study](#4-how-to-actually-study)
5. [Recommended Resources](#5-recommended-resources)
6. [Common Mistakes](#6-common-mistakes)
7. [What Comes Next](#7-what-comes-next)
8. [Progress Checklist](#8-progress-checklist)

---

## 1. The Three Rules

1. **You learn Java by writing Java.** Watching or reading is not learning. If a study session produced no code, it was entertainment.
2. **Every phase ends with something you built.** Not "I completed the course" — "I built this, and it's on GitHub."
3. **Move on when you hit the exit criteria, not when you feel ready.** You will never feel ready.

You don't need prior programming experience. You do need a laptop, consistency, and a willingness to write code every day, even for 30 minutes.

---

## 2. Before You Start

### 2.1 Why Java?

Java is strongly typed, widely used in enterprise software, banking, and large backend systems, and backed by a huge ecosystem and job market. It's also a good language for learning object-oriented programming properly, because it forces you to think about structure.

> **Honest caveat:** Java is not the only valid first language. If your goal is data science or machine learning, Python is usually the more direct path. If your goal is backend, enterprise, or software engineering roles, Java is a strong choice. Pick based on your goal, not hype.

### 2.2 Set Up Your Environment

1. Install the **JDK** — the latest LTS release is recommended (check [adoptium.net](https://adoptium.net) for the current one).
2. Choose an editor: **VS Code** with the Java Extension Pack, or **IntelliJ IDEA Community Edition**.
3. Install **Git** and create a GitHub account.

Need help with VS Code? See the [VS Code Setup Guide](./vscode-setup-guide.md), specifically [Section 8.9 (Java)](./vscode-setup-guide.md#89-java).

**Exit criteria:** You can compile and run a "Hello, World" program from both the terminal and your editor.

---

## 3. The Roadmap

Six phases, in order. Don't skip ahead — each phase builds on the last.

### 3.1 Phase 1: Core Language Fundamentals

**Learn:**
- Variables, data types, operators
- Input and output (`Scanner`, `System.out`)
- Conditionals (`if`, `switch`)
- Loops (`for`, `while`, `do-while`)
- Methods (parameters, return values)
- Arrays and `String` handling

**Practice:** Solve 30–50 small problems — FizzBuzz, palindrome check, factorial, prime numbers, reversing a string, finding the largest element in an array.

**Where to practice:**
- [CodingBat Java](https://codingbat.com/java) — short, instant-feedback warm-ups
- [Exercism Java track](https://exercism.org/tracks/java) — the early exercises, with tests included
- [HackerRank Java domain](https://www.hackerrank.com/domains/java) — the "Introduction" challenges
- [MOOC.fi Java Programming](https://java-programming.mooc.fi/) — the first few parts

**Build:** A console **number guessing game** and a **simple calculator**.

**Exit criteria:** You can solve a beginner-level problem from a blank file *without* looking up the syntax on every line.

---

### 3.2 Phase 2: Object-Oriented Programming

This is the heart of Java. Don't rush it.

**Learn:**
- Classes and objects, constructors
- Encapsulation (`private`, getters/setters)
- Inheritance and `super`
- Polymorphism (overriding vs overloading)
- Abstraction (abstract classes, interfaces)
- `static`, `final`, `this`
- Packages and access modifiers

**Practice:** Model real things as classes — a `BankAccount`, a `Library`, a `Vehicle` hierarchy.

**Where to practice:**
- [MOOC.fi](https://java-programming.mooc.fi/) — the object-oriented programming parts
- [Exercism Java track](https://exercism.org/tracks/java) — exercises that need classes and interfaces
- [HackerRank Java domain](https://www.hackerrank.com/domains/java) — the OOP challenges
- Your own code — pick a real-world object around you and model it

**Build:** A **Library Management System** or **Bank Account Simulator** using multiple classes and an interface, running in the console.

**Exit criteria:** You can explain, in your own words and with a code example, the difference between an abstract class and an interface, and when you'd use each.

---

### 3.3 Phase 3: Intermediate Java

**Learn:**
- **Collections framework** — `ArrayList`, `LinkedList`, `HashMap`, `HashSet`, `TreeMap`, and when to use which
- **Exception handling** — `try/catch/finally`, checked vs unchecked, custom exceptions
- **Generics**
- **File I/O** — reading and writing files
- **Lambdas and the Streams API**
- `Optional`, `record`, and other modern Java features
- Basic **multithreading** concepts — just the idea of threads and why concurrency is hard

**Where to practice:**
- [LeetCode](https://leetcode.com) — easy problems tagged *Array*, *Hash Table*, and *String*
- [Exercism Java track](https://exercism.org/tracks/java) — medium-level exercises
- [Codewars](https://www.codewars.com) — small katas, good for practicing streams
- [Advent of Code](https://adventofcode.com) — puzzles from past years, solved in Java

**Build:** A **Student Record Manager** or **Expense Tracker** that saves data to a file and uses collections and streams.

**Exit criteria:** You can pick the right collection for a problem and justify your choice. You can rewrite a loop as a stream and explain which is clearer.

---

### 3.4 Phase 4: Tools of a Real Developer

Writing code is half the job. The other half is the toolchain.

**Learn:**
- **Git and GitHub** — commit, branch, merge, pull request
- **Maven or Gradle** — dependencies and builds
- **JUnit** — writing unit tests
- Debugging with your IDE's debugger (not just `System.out.println`)
- Reading stack traces without panicking

**Where to practice:**
- [GitHub Skills](https://skills.github.com) — interactive Git and GitHub courses
- Your own Exercism solutions — write extra JUnit tests for them
- Your older projects — add tests and a build file to each
- Open-source issues labelled *good first issue* — once you're comfortable

**Build:** Take one earlier project, convert it to a Maven project, add unit tests, and push it with a clear README.

**Exit criteria:** A stranger can clone your repo, run one command, and see your project work.

---

### 3.5 Phase 5: Databases & Backend Basics

**Learn:**
- **SQL** fundamentals — `SELECT`, `JOIN`, `INSERT`, `UPDATE`, `DELETE`
- **JDBC** — connecting Java to a database
- **REST API** concepts — HTTP, JSON, status codes
- **Spring Boot** — controllers, services, repositories
- Basics of **Spring Data JPA**

**Where to practice:**
- [SQLBolt](https://sqlbolt.com) and [SQLZoo](https://sqlzoo.net) — SQL fundamentals
- [HackerRank SQL domain](https://www.hackerrank.com/domains/sql) — SQL practice problems
- [Spring Guides](https://spring.io/guides) — short, hands-on, official walkthroughs
- Postman or `curl` — test every endpoint you build

**Build:** A **REST API** for a to-do app or a book catalog, with a real database behind it.

**Exit criteria:** Your API supports create, read, update, and delete operations, handles errors sensibly, and has at least a few tests.

---

### 3.6 Phase 6: Capstone Project

Build **one** project that is yours — not a tutorial clone. It should:

- Solve a real problem you or someone you know actually has
- Use a database, a REST API, and tests
- Have a clean README with screenshots, setup steps, and a short explanation of your design decisions
- Be deployed, or easily runnable

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
- **Break things on purpose.** Remove a semicolon, change a type, and read the error message.
- **Explain it out loud.** If you can't explain a concept simply, you don't understand it yet.
- **Re-solve old problems.** A week later, solve the same problem again from scratch.

### 4.3 Avoiding Tutorial Hell

Tutorial hell is when you keep watching courses but can't build anything alone. Signs you're in it:

- You've finished three courses but have zero projects of your own
- You feel productive, but couldn't build anything without the video open
- You keep switching resources instead of finishing one

**The fix:** After every concept, close the tutorial and build something small with it. One course finished beats five courses started.

---

## 5. Recommended Resources

Pick **one primary resource** per phase. Don't collect them all.

**Free, structured courses**
- [MOOC.fi Java Programming](https://java-programming.mooc.fi/) (University of Helsinki) — exercise-driven and beginner-friendly
- [dev.java](https://dev.java) — the official learning site from Oracle

**Books**
- *Head First Java* — friendly and visual; great for beginners
- *Effective Java* by Joshua Bloch — read this *after* Phase 3, not before
- *Core Java* by Cay Horstmann — a thorough reference

**Reference**
- [Baeldung](https://www.baeldung.com) — practical articles on almost any Java or Spring topic
- [Spring Boot documentation](https://spring.io/projects/spring-boot)

---

## 6. Common Mistakes

1. **Skipping OOP.** Everything later depends on it.
2. **Jumping to Spring Boot too early.** Frameworks hide what's happening. Learn the language first.
3. **Memorizing syntax.** You look things up. Understanding matters more.
4. **Never reading error messages.** The error tells you exactly what's wrong. Read it first, then Google.
5. **Not using Git until "later."** Start from day one.
6. **Studying in bursts.** Daily 45 minutes beats a weekend marathon.
7. **Comparing your week 2 to someone else's year 3.**

---

## 7. What Comes Next

Once you've finished this path, you have the foundation to move toward backend development, Android, data engineering, or cloud work. Depending on your goal, explore system design basics, Docker, a cloud platform (AWS, Azure, or GCP), and data structures and algorithms in depth.

---

## 8. Progress Checklist

- [ ] Environment set up, Hello World runs (Section 2)
- [ ] Phase 1: Fundamentals + 30 practice problems + 2 small projects
- [ ] Phase 2: OOP + Library/Bank project
- [ ] Phase 3: Collections, exceptions, streams + file-based project
- [ ] Phase 4: Git, Maven, JUnit + one tested project on GitHub
- [ ] Phase 5: SQL, Spring Boot + working REST API
- [ ] Phase 6: Capstone project with README

---

*Maintained as a living document — update as tooling evolves. Found something outdated or unclear? Open an issue or a PR.*
