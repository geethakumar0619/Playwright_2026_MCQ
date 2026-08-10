# Playwright — Session 1 MCQ Answer Key & Evaluation

Companion to `playwright-session-01-mcq-quiz.md`. **Grade first, then read the explanations for everything you missed.**

## Quick key

| Q | Ans | Q | Ans | Q | Ans | Q | Ans |
|---|---|---|---|---|---|---|---|
| 1 | B | 9 | B | 17 | C | 25 | B |
| 2 | C | 10 | A | 18 | B | 26 | A |
| 3 | C | 11 | D | 19 | C | 27 | C |
| 4 | D | 12 | B | 20 | B | 28 | B |
| 5 | C | 13 | C | 21 | C | 29 | B |
| 6 | B | 14 | B | 22 | B | 30 | B |
| 7 | B | 15 | B | 23 | C | 31 | B |
| 8 | C | 16 | B | 24 | B | 32 | B |

---

## Section A — Recall (Q1–Q14)

**Q1 — B. Microsoft.** Open-source, but Microsoft-developed and maintained.

**Q2 — C. 2020.**

**Q3 — C. Node.js.** Playwright is a Node.js library at its core. The Java/Python/C# bindings talk to the same underlying driver.

**Q4 — D. Trident.** Trident was Internet Explorer's engine — long dead and never supported. The three engines are Chromium, Firefox, WebKit.

**Q5 — C. Safari.** Chrome and Edge → Chromium. Firefox → its own Gecko-based engine, which Playwright patches.

**Q6 — B. Ruby.** Officially supported: JavaScript, TypeScript, Java, Python, C#. (Community Ruby ports exist but aren't official.)

**Q7 — B. Chrome on Android and Safari on iOS.** Note this is **mobile web** — emulated viewports, user agents, and touch. Playwright does **not** test native mobile apps (that's Appium's territory). If you picked D, that's the distinction to remember.

**Q8 — C. Codegen.**

**Q9 — B. Trace Viewer.** The word "investigate a failure *after* the run" is the giveaway — traces are a post-mortem artifact.

**Q10 — A. Inspector.** "Real time," "click points," "verify locators" = Inspector. The easy confusion is Inspector vs Trace Viewer: **Inspector is live while you debug; Trace Viewer is a recording you open afterwards.**

**Q11 — D. PDF.** Built-in: HTML, JSON, JUnit (plus list, dot, line, blob). No PDF reporter.

**Q12 — B. Third-party.** Allure needs a separate package; it isn't bundled.

**Q13 — C.** A cross-platform runtime that executes JavaScript outside a browser. This matters because your test code must run in a process *outside* the browser it is controlling.

**Q14 — B.** The standard all JavaScript must comply with (ES3, ES5, ES6, …). Not a Microsoft asset — that's the whole point of Q32.

---

## Section B — Conceptual (Q15–Q24)

**Q15 — B.** Playwright waits for the element to be attached, visible, stable, enabled, and able to receive events before acting.
*Why not C:* retrying the whole test is a separate feature (`retries`), not auto-waiting.

**Q16 — B.** Kills hardcoded sleeps. A fixed sleep is wrong in both directions: wasteful when the app is fast, insufficient when it's slow.

**Q17 — C.** Intermittent pass/fail on unchanged code. A test that always fails isn't flaky — it's just failing, and that's far more useful.

**Q18 — B.** An encapsulated, isolated DOM subtree used by web components. Ordinary CSS/XPath queries don't cross the boundary; Playwright locators pierce open shadow roots automatically.

**Q19 — C.** Independence. Two workers mutating the same user record or test data is the number-one cause of parallel-run failures.
*Why not B:* headless is faster but not a correctness requirement.

**Q20 — B.** CI failures you can't reproduce locally. That's exactly the case where re-running teaches you nothing and the trace is the only record of what actually happened.
*Why not A:* writing a fresh locator is Inspector's job.

**Q21 — C.** Flat, unstructured code with brittle locators and no meaningful assertions. Codegen is a scaffolding and locator-discovery aid, not a source of production tests.

**Q22 — B.** Fast, reliable setup via API + verification of persistence after a UI action. One toolchain, one report, one CI job.
*Why not A:* API tests don't replace UI tests — they can't tell you whether a human can complete the journey.

**Q23 — C.** Full suite on Chromium, critical-path subset on Firefox and WebKit. Option A roughly triples cost and runtime for a low defect yield, since most bugs are application-logic bugs that reproduce everywhere.
*This one is judgement, not a fact from the slides — the notes present cross-browser as a feature; the strategy question is what you'll actually face on a real team.*

**Q24 — B.** Playwright can be used as a plain automation library (scraping, screenshots, PDFs) with no test runner at all. `@playwright/test` is the optional framework layer on top.

---

## Section C — JavaScript vs TypeScript (Q25–Q32)

**Q25 — B. Dynamically typed.** Types resolved at runtime; a variable's type can change.

**Q26 — A. Statically typed.** Types declared and checked at compile time.

**Q27 — C. No error.** `age` simply becomes a string. This is legal JavaScript, which is precisely the problem TypeScript solves.

**Q28 — B. Compile-time error** — `Type 'string' is not assignable to type 'number'`. Note the emphasis on *compile-time*: it fails before the code ever runs. Even without the `: number` annotation, TS infers `number` from `30` and still errors.

**Q29 — B.** Every valid JS file is also valid TS. You can rename `.js` → `.ts` and add types incrementally.

**Q30 — B.** Compiled/transpiled to ECMAScript-compliant JavaScript.

**Q31 — B. Erased.** Types have zero runtime presence — they're a development-time safety net only. This trips people up: you cannot check a TypeScript type at runtime.

**Q32 — B.** Microsoft can't unilaterally change JavaScript without breaking ECMAScript compliance, but it can add anything to TypeScript so long as the **generated output** is compliant. That freedom is why TypeScript can be as feature-rich as any other language.

---

## Evaluating your result

**Score by section — this tells you what to fix, more than the total does.**

| Section | Max | Your score | If you scored low |
|---|---|---|---|
| A. Recall (Q1–14) | 14 |  | Pure memorisation — re-read the notes for 15 minutes. Easiest gap to close. |
| B. Conceptual (Q15–24) | 10 |  | The one that matters for interviews and real work. Re-read explanations and say each answer out loud in your own words. |
| C. JS vs TS (Q25–32) | 8 |  | Write the four code snippets yourself in VS Code and watch the red squiggles appear. |

**Most commonly missed:** Q7 (mobile *web*, not native apps), Q10 vs Q9 (Inspector = live / Trace Viewer = recording), Q24 (Playwright works without a test runner), Q31 (types are erased at runtime).

**Total ____ / 32**

| Band | Verdict |
|---|---|
| 29–32 | Excellent — move on to Session 2 |
| 24–28 | Pass — review your misses |
| 18–23 | Shaky — re-read the notes for the weak section |
| under 18 | Re-watch the session recording |
