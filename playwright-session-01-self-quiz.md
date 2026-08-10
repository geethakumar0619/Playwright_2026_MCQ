# Playwright — Session 1 Self-Quiz

**Topic:** Introduction to Playwright + JavaScript vs TypeScript
**Source:** Class notes (pavanonlinetrainings / @sdetpavan)

**How to use:** Answer out loud or in a scratch file *before* expanding the answer. Each expandable block is one point unless noted.

| Section | Questions | Points |
|---|---|---|
| A. Quick recall | 10 | 10 |
| B. Conceptual | 10 | 20 (2 each) |
| C. JS vs TS | 7 | 14 (2 each) |
| D. Stretch | 4 | 8 (2 each) |
| **Total** | **31** | **52** |

Scoring guide: **44+** solid · **33–43** review the weak section · **under 33** re-watch the recording before the next class.

---

## Section A — Quick recall (1 point each)

**A1.** Who developed Playwright, and in what year was it released?

<details><summary>Answer</summary>

Microsoft, released in **2020**. It is open-source.
</details>

**A2.** Playwright is built on top of which runtime? What is that runtime?

<details><summary>Answer</summary>

**Node.js** — an open-source, cross-platform JavaScript runtime that executes JavaScript code *outside* of a web browser.
</details>

**A3.** Name the three browser engines Playwright supports, with one real browser for each.

<details><summary>Answer</summary>

- **Chromium** → Chrome, Edge
- **Firefox** → Firefox
- **WebKit** → Safari
</details>

**A4.** Which operating systems does Playwright run on?

<details><summary>Answer</summary>

Windows, macOS, Linux.
</details>

**A5.** List the five languages you can write Playwright tests in.

<details><summary>Answer</summary>

JavaScript, TypeScript, Java, Python, C#.
</details>

**A6.** Which two mobile browser scenarios does Playwright support?

<details><summary>Answer</summary>

Chrome on **Android** and Safari on **iOS** (mobile web testing).
</details>

**A7.** Name three built-in report formats Playwright provides.

<details><summary>Answer</summary>

HTML, JSON, JUnit (and more).
</details>

**A8.** Which third-party reporting tool was mentioned in class?

<details><summary>Answer</summary>

**Allure**.
</details>

**A9.** Name the three Playwright tools covered, with one line each.

<details><summary>Answer</summary>

1. **Inspector** — debug tests live; shows click points and lets you verify locators in real time.
2. **Codegen** (Code Generation) — records your actions and converts them into test scripts in any supported language.
3. **Trace Viewer** (Tracing) — captures screenshots, records video, logs every step; used to investigate a test failure after the fact.
</details>

**A10.** What is ECMAScript?

<details><summary>Answer</summary>

**ECMAScript (ES)** is the standard/specification that all JavaScript code must comply with. Versions include ES3, ES4, ES5, ES6.
</details>

---

## Section B — Conceptual (2 points each)

**B1.** Playwright is described as both a browser automation tool *and* an E2E testing framework. What's the difference?

<details><summary>Answer</summary>

**Automation** = the ability to drive a browser programmatically (click, type, navigate, screenshot). That's the engine.
**E2E testing framework** = the layer on top that gives you test structure, assertions, fixtures, parallel runners, retries, and reporting.

Playwright ships both: you can use it purely as an automation library (scraping, screenshots, PDF generation) with no test runner at all, or use `@playwright/test` as a full framework. It also exposes a dedicated **API** for testing/interacting with web APIs.
</details>

**B2.** What is auto-waiting, and what problem does it solve?

<details><summary>Answer</summary>

Before performing an action, Playwright automatically waits for the element to be **ready** — attached to the DOM, visible, stable (not animating), enabled, and able to receive events.

It solves the need for manual `sleep`/`Thread.sleep` calls, which are the classic source of flakiness: a fixed 3-second wait is simultaneously too slow when the app is fast and too short when the app is slow.
</details>

**B3.** What is test flakiness? Name two causes.

<details><summary>Answer</summary>

A **flaky** test passes and fails intermittently on the *same* code — so its result carries no information.

Common causes: timing/race conditions (asserting before the UI has updated), shared or dirty test data between tests, network or third-party service variability, animations, test-order dependency, and environment differences (local vs CI).
</details>

**B4.** What is the Shadow DOM, and why is it hard for traditional tools?

<details><summary>Answer</summary>

Shadow DOM lets a component encapsulate its own isolated DOM subtree (used heavily by web components and design-system libraries). The internal nodes are hidden from the main document tree.

Traditional tools' CSS/XPath queries don't cross the shadow boundary, so you have to manually pierce each shadow root. Playwright's locators pierce open shadow roots automatically.
</details>

**B5.** How does parallel execution reduce run time, and what's the trade-off?

<details><summary>Answer</summary>

Playwright runs multiple browser instances/workers at once, so wall-clock time approaches *total time ÷ number of workers* instead of the sum of all tests.

Trade-offs: tests must be **independent** and must not share mutable state or test data (two workers editing the same user record will collide); you need more CPU/memory; and failures get harder to reproduce if there's hidden coupling.
</details>

**B6.** Why have API testing and UI testing in the *same* framework?

<details><summary>Answer</summary>

- **Setup/teardown via API is fast and reliable** — create the test user or seed data with an API call, then do only the actual assertion through the UI.
- **Verification from both sides** — click "Save" in the UI, then confirm via API that the record actually persisted.
- One toolchain, one language, one report, one CI job — no context-switching between Postman/RestAssured and a separate UI tool.
</details>

**B7.** Node.js "executes JavaScript outside of a web browser." Why does Playwright need that?

<details><summary>Answer</summary>

Your test code has to run *outside* the browser it is controlling. Node.js is the process that runs your test script, launches browser processes, and communicates with them over a websocket/protocol connection to send commands and receive events. Code running *inside* the page is sandboxed and can't launch or drive browsers.
</details>

**B8.** When would you use Trace Viewer instead of just re-running the test?

<details><summary>Answer</summary>

When re-running is expensive or won't reproduce the failure — above all **CI failures** and **flaky tests**. The trace is a recording of the run that actually failed: DOM snapshot at every step, screenshots, network calls, console logs, and the action timeline. Re-running locally often just passes and tells you nothing.
</details>

**B9.** Codegen records your actions. What are the limitations of recorded scripts in a real project?

<details><summary>Answer</summary>

- Generated locators can be brittle or auto-generated in ways that break on the next UI change.
- No structure — no Page Objects, no reuse, no helper functions; it produces one long flat script.
- No meaningful assertions; you get actions, not verification of business rules.
- No data handling, loops, or conditionals.

Best used as a **starting point** / locator-discovery aid, then refactored by hand.
</details>

**B10.** Is running every test on all three engines a good idea?

<details><summary>Answer</summary>

Usually no. It roughly triples run time and CI cost for a low defect yield, since most bugs are application-logic bugs that reproduce everywhere.

A common strategy: run the **full suite** on Chromium on every commit, and run a **smaller cross-browser smoke/critical-path subset** on Firefox and WebKit nightly or pre-release. Weight it by your real user browser mix.
</details>

---

## Section C — JavaScript vs TypeScript (2 points each)

**C1.** Classify JS and TS as statically or dynamically typed, and define both terms.

<details><summary>Answer</summary>

- **JavaScript — dynamically typed:** types are checked at **runtime**; a variable's type can change during execution.
- **TypeScript — statically typed:** types are declared and checked at **compile time**, before the code ever runs.
</details>

**C2.** `let age = 30; age = "thirty";` — what happens in JS vs TS?

<details><summary>Answer</summary>

**JavaScript:** no error. `age` simply becomes a string.

**TypeScript:** with `let age: number = 30;`, the reassignment is a compile-time **error** — `Type 'string' is not assignable to type 'number'`.
(Even without the annotation, TS *infers* `number` from the initial value and still errors.)
</details>

**C3.** What does "TypeScript is a superset of JavaScript" mean concretely?

<details><summary>Answer</summary>

Every valid JavaScript file is already valid TypeScript. TS = JS + extra syntax on top (type annotations, interfaces, enums, generics, access modifiers). You can rename a `.js` file to `.ts` and it still works, then add types incrementally.
</details>

**C4.** Browsers don't run TypeScript. So what happens before it runs?

<details><summary>Answer</summary>

It's **compiled (transpiled)** to plain ECMAScript-compliant JavaScript — by `tsc` or a bundler/transpiler. All type information is **erased**; types exist only at development/compile time and have zero runtime presence.
</details>

**C5.** Why can Microsoft add features freely to TypeScript but not to JavaScript?

<details><summary>Answer</summary>

A vendor can't unilaterally add features to JavaScript without breaking **ECMAScript compliance** — the standard is governed collectively.

With TypeScript, Microsoft can add whatever it likes as long as the **generated output** is ECMAScript-compliant. That freedom is what lets TypeScript be as feature-rich as any other language.
</details>

**C6.** Two concrete benefits of TS *for a test automation codebase specifically*.

<details><summary>Answer</summary>

- **IntelliSense/autocomplete on the Playwright API** — you discover methods and their options without leaving the editor, and typos are caught immediately.
- **Errors surface at compile time, not mid-run** — a wrong property on a Page Object or a bad test-data shape fails instantly instead of 8 minutes into a suite.
- **Safer refactoring** — rename a Page Object method and every call site is flagged.
- **Typed test data / API response models** — you know the shape of the payload you're asserting on.
</details>

**C7.** Any downside to TypeScript?

<details><summary>Answer</summary>

A compile/transpile step and config (`tsconfig.json`) to maintain, slightly slower feedback on very large projects, more verbose code, and a learning curve for team members coming from plain JS. In practice, for test code the trade is almost always worth it.
</details>

---

## Section D — Stretch / interview-style (2 points each)

**D1.** Playwright vs Selenium vs Cypress — one distinguishing point each.

<details><summary>Answer</summary>

- **Selenium** — the long-standing W3C WebDriver standard; the widest browser/language/grid ecosystem, but no built-in auto-waiting, assertions, or reporting; you assemble the stack yourself.
- **Cypress** — runs *inside* the browser, excellent developer experience, but that architecture historically limits multi-tab/multi-origin work and it's JS/TS only.
- **Playwright** — out-of-process control over Chromium/Firefox/WebKit, auto-waiting, tracing, parallelism, API testing, and multi-language support in one package.
</details>

**D2.** If auto-waiting exists, why would you ever still need an explicit wait?

<details><summary>Answer</summary>

Auto-waiting waits for the *element* to be actionable — it can't know about application state that isn't reflected in that element. You still wait explicitly for things like: a network response to complete, a spinner/toast to disappear, a chart to finish rendering, a download to land, or a value to settle after debounce.

The correct tool is a condition-based wait (wait for a response, a state, or an assertion to become true) — **not** a fixed sleep.
</details>

**D3.** Test passes locally, fails in CI. First move?

<details><summary>Answer</summary>

Open the **trace** from the CI run — don't guess. It shows the DOM snapshot, screenshot, network, and console at the failing step.

Then check the usual environment deltas: headless vs headed, viewport/screen size, timezone and locale, slower CI machine (timeouts), missing or different test data, auth/session state, and parallel workers colliding on shared data.
</details>

**D4.** How do you decide whether a check belongs in an API test or a UI test?

<details><summary>Answer</summary>

Ask *what is actually under test*. Business rules, calculations, validation, permissions, and data integrity → **API test**: faster, more stable, and pinpoints the failure.

Rendering, layout, user flows, navigation, and "can a person actually complete this journey" → **UI test**.

Rule of thumb: don't verify the same business rule at both levels. Use the API to set up state and to verify persistence; use the UI to verify the experience.
</details>

---

## Section E — Ask the instructor (not scored)

Bring these to the last-15-minutes Q&A:

1. Will demos be in JavaScript or TypeScript — and can we submit practice work in either?
2. Exact setup needed before the next class: Node version, VS Code extensions, install command?
3. Where do recorded videos and class scripts land on Google Drive, and how soon after each session?
4. For the 1–2 hours of daily practice — is there a recommended practice site/app, or do we use our own?
5. Will we cover CI integration (GitHub Actions / Jenkins) and Allure reporting, or only local runs?
6. Will we cover the Page Object Model and fixtures, or stay on the core API?

---

## My score

| Section | Score | Notes / what to review |
|---|---|---|
| A |  /10 |  |
| B |  /20 |  |
| C |  /14 |  |
| D |  /8 |  |
| **Total** | **/52** |  |
