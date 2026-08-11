# Getting Started with TypeScript — MCQ Quiz

**Topic:** Introduction to TypeScript, Setup, First Program
**Total Questions:** 30
**Marks:** 30 (1 mark each)
**Suggested Time:** 30 minutes

---

## Section 1: Introduction to TypeScript

**Q1. What is TypeScript?**
- A) A replacement for JavaScript that runs on its own engine
- B) A superset of JavaScript that adds extra features to it
- C) A subset of JavaScript with fewer features
- D) A JavaScript testing framework

**Q2. What file extension do TypeScript files use?**
- A) `.js`
- B) `.tsx` only
- C) `.ts`
- D) `.tscript`

**Q3. What happens to TypeScript code before it runs in a browser?**
- A) It runs directly in the browser without any change
- B) It is compiled (converted) into regular JavaScript
- C) It is converted into machine code
- D) It is interpreted by the TypeScript engine in the browser

**Q4. Arrange the correct order of how TypeScript works:**
- A) Write `.js` → compile → `.ts` → run
- B) Write `.ts` → compiler converts to `.js` → JS runs in browser/Node.js
- C) Write `.ts` → run directly in browser → compile to `.js`
- D) Write `.ts` → compile to `.exe` → run

**Q5. Which statement is TRUE about the relationship between JavaScript and TypeScript?**
- A) All TypeScript code is valid JavaScript
- B) All JavaScript code is valid TypeScript
- C) JavaScript and TypeScript are completely incompatible
- D) JavaScript code must be rewritten fully before using it in TypeScript

**Q6. In TypeScript, types are:**
- A) Mandatory for every variable
- B) Optional features added on top of JavaScript
- C) Not supported at all
- D) Only allowed inside classes

**Q7. Which of the following is NOT a benefit of using TypeScript?**
- A) Helps catch mistakes early, before running the code
- B) Makes large projects easier to manage
- C) Works smoothly with existing JavaScript code
- D) Makes the JavaScript output run faster than hand-written JavaScript

**Q8. TypeScript helps catch mistakes:**
- A) Only at runtime
- B) Before running the code (at compile time)
- C) Only during deployment
- D) Only when unit tests are executed

---

## Section 2: Setting Up TypeScript

**Q9. Which tool is required to run the TypeScript compiler?**
- A) Python
- B) Node.js
- C) Java JDK
- D) Docker

**Q10. Which command checks the installed Node.js version?**
- A) `node --version`
- B) `npm -v`
- C) `tsc -v`
- D) `node --check`

**Q11. Which Node.js version is recommended in the setup instructions?**
- A) 8+
- B) 12+
- C) 18+
- D) 22 only

**Q12. Which command installs the TypeScript compiler globally?**
- A) `npm install typescript`
- B) `npm install -g typescript`
- C) `npm -g add tsc`
- D) `node install -g typescript`

**Q13. In `npm install -g typescript`, what does the `-g` flag mean?**
- A) Generate JavaScript files
- B) Install globally (available system-wide)
- C) Install the GitHub version
- D) Install in debug/global mode

**Q14. Which command verifies that the TypeScript compiler is installed?**
- A) `typescript -v`
- B) `tsc --version`
- C) `node tsc -v`
- D) `npm tsc -v`

**Q15. On Windows, if you get the error `'tsc' is not recognized`, what is the fix?**
- A) Reinstall Node.js
- B) Add `C:\Users\<your-username>\AppData\Roaming\npm` to System Environment Variables
- C) Rename `tsc` to `tsc.exe`
- D) Run VS Code as administrator

**Q16. Which tool lets you run TypeScript files directly without compiling them first?**
- A) `tsc`
- B) `tsx`
- C) `npx`
- D) `nodemon`

**Q17. Which command installs TSX globally?**
- A) `npm install -g tsx`
- B) `npm install tsx --save`
- C) `tsc install tsx`
- D) `npm add -g typescript-x`

**Q18. Which editor is recommended for TypeScript development?**
- A) Notepad
- B) Eclipse
- C) VS Code
- D) IntelliJ Community Edition

---

## Section 3: First TypeScript Program

**Q19. What is the correct order of steps to create your first TypeScript program?**
- A) Create `app.ts` → open folder in VS Code → compile → run
- B) Create project folder → open folder in VS Code → create `app.ts` → compile → run
- C) Compile → create folder → write code → run
- D) Install VS Code → run `node app.js` → create `app.ts`

**Q20. Which shortcut opens the terminal in VS Code?**
- A) `Ctrl + T`
- B) `Ctrl + ~` (backtick)
- C) `Ctrl + Shift + P`
- D) `Alt + F4`

**Q21. What does the command `tsc app.ts` do?**
- A) Runs `app.ts` directly
- B) Generates `app.js`, the JavaScript version of the file
- C) Deletes `app.ts` after checking types
- D) Installs TypeScript for that file

**Q22. After running `tsc app.ts`, how do you execute the generated file?**
- A) `node app.ts`
- B) `node app.js`
- C) `tsc app.js`
- D) `run app.js`

**Q23. What is the output of `console.log("Welcome to TypeScript!");`?**
- A) `Welcome to TypeScript`
- B) `Welcome to TypeScript!`
- C) `console.log("Welcome to TypeScript!")`
- D) Nothing — `console.log` is not supported in TypeScript

**Q24. Which single command runs a `.ts` file without creating a `.js` file?**
- A) `tsc app.ts`
- B) `tsx app.ts`
- C) `node app.ts`
- D) `npm run app.ts`

**Q25. Which command fixes the Execution Policy error that appears when running `tsc` in PowerShell?**
- A) `Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned`
- B) `Set-ExecutionPolicy -Scope AllUsers -ExecutionPolicy Unrestricted`
- C) `npm config set execution-policy remote`
- D) `tsc --allow-scripts`

**Q26. The Execution Policy error typically occurs on which platform?**
- A) macOS
- B) Linux
- C) Windows (PowerShell)
- D) All platforms equally

---

## Section 4: Quick Summary Recall

**Q27. Which tool converts `.ts` files into `.js` files?**
- A) Node.js
- B) `tsc` (TypeScript Compiler)
- C) VS Code
- D) `tsx`

**Q28. Which pair is correctly matched?**
- A) Node.js → best editor for TypeScript
- B) `tsc` → runs TypeScript without compiling
- C) `tsx` → runs TypeScript without compiling
- D) VS Code → converts `.ts` to `.js`

**Q29. You wrote a TypeScript file and want the fastest way to see its output during practice. What is the recommended approach?**
- A) Compile with `tsc`, then run with `node`
- B) Run it directly with `tsx`
- C) Paste the code into the browser console
- D) Rename the file to `.js` and run it

**Q30. Which statement about TypeScript adoption in an existing JavaScript project is TRUE?**
- A) The whole project must be rewritten before TypeScript can be used
- B) TypeScript works smoothly alongside existing JavaScript code
- C) TypeScript cannot be used with Node.js projects
- D) TypeScript requires removing all existing `.js` files

---
---

# Answer Key

| Q | Ans | Q | Ans | Q | Ans |
|---|-----|---|-----|---|-----|
| 1 | B | 11 | C | 21 | B |
| 2 | C | 12 | B | 22 | B |
| 3 | B | 13 | B | 23 | B |
| 4 | B | 14 | B | 24 | B |
| 5 | B | 15 | B | 25 | A |
| 6 | B | 16 | B | 26 | C |
| 7 | D | 17 | A | 27 | B |
| 8 | B | 18 | C | 28 | C |
| 9 | B | 19 | B | 29 | B |
| 10 | A | 20 | B | 30 | B |

## Explanations for the tricky ones

- **Q5 (B):** The relationship is one-directional. JavaScript is a subset of TypeScript, so any working JS is valid TS — but TS-specific syntax (type annotations, interfaces) is *not* valid JavaScript.
- **Q7 (D):** TypeScript's benefits are developer-side (early error detection, maintainability, JS interop). The compiled output is plain JavaScript, so there is no runtime speed gain.
- **Q10 (A):** `node -v` / `node --version` checks Node.js; `npm -v` checks npm; `tsc -v` checks the compiler — different tools, different checks.
- **Q15 (B):** The error means Windows can't find the global npm binaries folder. Adding `AppData\Roaming\npm` to the PATH environment variable resolves it — reinstalling Node.js does not.
- **Q24 / Q29 (B):** `tsc` compiles only (producing a `.js` file you then run separately); `tsx` compiles and executes in one step, leaving no `.js` behind.
- **Q25 (A):** PowerShell blocks running scripts by default. `RemoteSigned` at `CurrentUser` scope is the recommended minimum change — safer than `Unrestricted` for all users.

---

*Reference material: https://www.pavanonlinetrainings.com | https://www.youtube.com/@sdetpavan*
