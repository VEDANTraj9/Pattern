# Copilot / Agent Instructions — Java Pattern Examples

Overview
- This repo contains a set of small, single-class Java programs that print console patterns (e.g., `Butterfly_P`, `Pyramid_P`, `Pascal_Triangle_P`).
- Files live in the root of the `Pattern` folder and are simple programs (no packages, no build system).

What to expect
- Each file typically defines a `public class` whose filename matches the class (e.g., `Butterfly_P.java` -> `public class Butterfly_P`).
- Programs use hard-coded `int n = ...` values to set pattern size; change `n` or add command-line parsing if needed.
- Outputs are printed to stdout; some files include illustrative output in comments.

Build & run (Windows / PowerShell)
- Compile everything quickly:

```powershell
javac *.java
```
- Run a program (example):

```powershell
java Butterfly_P
```

VS Code workflow
- No `pom.xml`/`gradle` present — use the Java extension or the `javac`/`java` commands above.
- To debug, set a launch configuration that runs the target class (launch.json) or use the Java extension's Run/Debug code lens.

Conventions and patterns to preserve
- Keep the filename == public class name. Renaming a class must update its file name accordingly.
- New pattern files should follow the `* _P.java` naming style used here (e.g., `MyPattern_P.java`) and include a `main` method for easy execution.
- Prefer printing to stdout for patterns; tests and frameworks are not present in this repo.

Examples worth copying
- `Butterfly_P.java`: symmetric upper/lower halves built from nested for-loops.
- `Pyramid_P.java`: centers rows by printing leading spaces then `2*i-1` stars.
- `Pascal_Triangle_P.java`: computes combinatorial values inline (`num = num * (i-j)/(j+1)`).

Agent authoring tips (targeted)
- When adding or editing a pattern, return a minimal, runnable file: single public class, `main(String[] args)`, no package.
- For usability improvements, consider adding simple CLI parsing (use `args[0]` as `n`) but preserve the original hard-coded default for backward compatibility.
- Avoid adding external libraries; these samples are intentionally dependency-free.

Missing pieces / manual checks
- There are no unit tests or CI. If you add tests, include a `README.md` and a simple `javac`-based test runner or add a lightweight `pom.xml`.
- Confirm that any renamed classes are updated in repository references (there are no imports now, but keep this in mind if introducing packages).

If something is unclear
- Tell me which sections you'd like expanded (examples, debug steps, or a sample `launch.json`) and I will iterate.
