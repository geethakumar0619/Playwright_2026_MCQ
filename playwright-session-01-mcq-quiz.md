# Playwright — Session 1 MCQ Quiz

**Topic:** Introduction to Playwright + JavaScript vs TypeScript
**Questions:** 32 · **Time:** ~20 minutes · **Pass mark:** 24/32 (75%)

**Instructions**
- One correct answer per question unless stated otherwise.
- Fill in the **Answer Sheet** at the bottom, then check `playwright-session-01-mcq-answer-key.md`.
- Do not open the answer key first. Guessing and then reading the explanation is worth more than reading the answer and nodding along.

---

## Section A — Recall (Q1–Q14)

**Q1.** Who developed Playwright?
- A. Google
- B. Microsoft
- C. Meta
- D. ThoughtWorks

**Q2.** In which year was Playwright released?
- A. 2016
- B. 2018
- C. 2020
- D. 2022

**Q3.** Playwright is built on which runtime?
- A. Java JVM
- B. Python interpreter
- C. Node.js
- D. .NET CLR

**Q4.** Which is **NOT** a browser engine supported by Playwright?
- A. Chromium
- B. Firefox
- C. WebKit
- D. Trident

**Q5.** WebKit is the engine behind which browser?
- A. Chrome
- B. Edge
- C. Safari
- D. Firefox

**Q6.** Which language is **NOT** supported for writing Playwright tests?
- A. TypeScript
- B. Ruby
- C. Python
- D. C#

**Q7.** Which pair correctly describes Playwright's mobile web support?
- A. Chrome on iOS and Safari on Android
- B. Chrome on Android and Safari on iOS
- C. Firefox on Android and Edge on iOS
- D. Native Android and native iOS apps

**Q8.** Which Playwright tool records your actions and converts them into test scripts?
- A. Inspector
- B. Trace Viewer
- C. Codegen
- D. Reporter

**Q9.** Which tool captures screenshots, video, and step logs so you can investigate a test failure after the run?
- A. Inspector
- B. Trace Viewer
- C. Codegen
- D. Allure

**Q10.** Which tool helps you debug in real time by showing click points and verifying locators?
- A. Inspector
- B. Trace Viewer
- C. Codegen
- D. JUnit reporter

**Q11.** Which is **NOT** one of Playwright's built-in report formats?
- A. HTML
- B. JSON
- C. JUnit
- D. PDF

**Q12.** Allure is:
- A. A Playwright built-in reporter
- B. A third-party reporting tool Playwright supports
- C. A browser engine
- D. A Node.js waiting library

**Q13.** Node.js is best described as:
- A. A web browser
- B. A JavaScript testing framework
- C. A cross-platform runtime that executes JavaScript outside a browser
- D. A TypeScript compiler

**Q14.** ECMAScript (ES) is:
- A. A Microsoft-owned JavaScript dialect
- B. The standard all JavaScript code must comply with
- C. Another name for TypeScript
- D. A browser rendering engine

---

## Section B — Conceptual (Q15–Q24)

**Q15.** "Auto-waiting" in Playwright means:
- A. Every action pauses for a fixed 30 seconds
- B. Playwright waits for an element to be ready/actionable before interacting with it
- C. The whole test is automatically retried on failure
- D. Playwright waits only for the initial page load event

**Q16.** The main practical benefit of auto-waiting is that it:
- A. Makes tests run on more browsers
- B. Removes the need for hardcoded sleeps, reducing flakiness
- C. Generates test code automatically
- D. Compiles TypeScript faster

**Q17.** A **flaky** test is one that:
- A. Always fails
- B. Runs slower than the rest of the suite
- C. Passes and fails intermittently on the same unchanged code
- D. Has no assertions

**Q18.** Shadow DOM is:
- A. A hidden browser cache
- B. An encapsulated DOM subtree isolated from the main document tree
- C. A Playwright debugging mode
- D. The DOM state captured in a trace

**Q19.** For parallel execution to work reliably, tests must primarily be:
- A. Written in TypeScript
- B. Run in headless mode
- C. Independent of each other and not sharing mutable state
- D. Under 30 seconds each

**Q20.** Trace Viewer is *most* valuable when:
- A. You are writing a brand-new locator
- B. A test fails in CI and you cannot reproduce it locally
- C. You want to convert clicks into code
- D. You need to publish an HTML report

**Q21.** The biggest limitation of Codegen-recorded scripts in a real project is that they:
- A. Only work in Chromium
- B. Cannot be run headlessly
- C. Produce flat, unstructured code with brittle locators and no meaningful assertions
- D. Cannot be saved to a file

**Q22.** A key reason to have API testing built into the same framework as UI testing is:
- A. It replaces the need for UI tests entirely
- B. You can set up test data fast via API and verify persistence via API after a UI action
- C. API tests can drive the browser
- D. It is the only way to get HTML reports

**Q23.** For a large suite, the most sensible cross-browser strategy is usually:
- A. Run every test on all three engines on every commit
- B. Run everything on WebKit only
- C. Run the full suite on Chromium, and a critical-path subset on Firefox and WebKit
- D. Never test on more than one browser

**Q24.** Which statement about Playwright is correct?
- A. It can only be used with its own test runner
- B. It can be used as a plain automation library without any test runner
- C. It requires TypeScript
- D. It only works for testing, never for scraping or screenshots

---

## Section C — JavaScript vs TypeScript (Q25–Q32)

**Q25.** JavaScript is a ____ typed language.
- A. Statically
- B. Dynamically
- C. Strongly, at compile time
- D. Untyped in every sense

**Q26.** TypeScript is a ____ typed language.
- A. Statically
- B. Dynamically
- C. Weakly
- D. Loosely

**Q27.** In JavaScript, what happens with `let age = 30; age = "thirty";`?
- A. Compile-time error
- B. Runtime crash
- C. No error — `age` becomes a string
- D. `age` becomes `NaN`

**Q28.** In TypeScript, what happens with `let age: number = 30; age = "thirty";`?
- A. No error
- B. Compile-time error: type `'string'` is not assignable to type `'number'`
- C. Runtime error only
- D. `age` is silently converted to `0`

**Q29.** "TypeScript is a superset of JavaScript" means:
- A. TypeScript replaces JavaScript entirely
- B. Every valid JavaScript file is also valid TypeScript
- C. TypeScript runs natively in browsers
- D. JavaScript is a subset only of older TypeScript versions

**Q30.** Browsers cannot run TypeScript directly, so TypeScript is:
- A. Interpreted by a browser plugin
- B. Compiled/transpiled into ECMAScript-compliant JavaScript
- C. Executed by Node.js as-is with no conversion
- D. Converted into WebAssembly

**Q31.** At runtime, TypeScript's type annotations are:
- A. Checked on every variable assignment
- B. Erased — they exist only at compile time
- C. Stored in a hidden metadata object
- D. Sent to the browser for validation

**Q32.** Why can Microsoft add features freely to TypeScript but not to JavaScript?
- A. Microsoft owns the JavaScript standard
- B. Because as long as the *generated* JavaScript is ECMAScript-compliant, TypeScript itself is unconstrained
- C. Because TypeScript does not compile
- D. Because browsers ship a TypeScript engine

---

## Answer Sheet

Fill in your choice (A/B/C/D), then grade against the answer key.

| Q | My answer | Q | My answer | Q | My answer | Q | My answer |
|---|---|---|---|---|---|---|---|
| 1 |  | 9 |  | 17 |  | 25 |  |
| 2 |  | 10 |  | 18 |  | 26 |  |
| 3 |  | 11 |  | 19 |  | 27 |  |
| 4 |  | 12 |  | 20 |  | 28 |  |
| 5 |  | 13 |  | 21 |  | 29 |  |
| 6 |  | 14 |  | 22 |  | 30 |  |
| 7 |  | 15 |  | 23 |  | 31 |  |
| 8 |  | 16 |  | 24 |  | 32 |  |

**Score: ____ / 32**

| Band | Meaning |
|---|---|
| 29–32 | Excellent — move on to Session 2 |
| 24–28 | Pass — review the questions you missed |
| 18–23 | Shaky — re-read the notes for the weak section |
| under 18 | Re-watch the session recording |
