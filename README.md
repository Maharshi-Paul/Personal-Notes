# Building Genuine Codebase Fluency

A step-by-step loop to run for every issue.

## I. Read Before Touching Code
1. Find the function referenced in the issue, read it fully.
2. Trace callers (who uses this?) and callees (what does it depend on?).
3. Check `git log -p` / `git blame` on the file — past commits often explain why the code is shaped that way.

## II. Reproduce the Bug First
1. Write a minimal script that triggers it.
2. If you can't reproduce it, you don't understand it yet — don't patch blind.

## III. Form and Verify a Hypothesis
1. Use a debugger or targeted prints, not guess-and-check editing.
2. Goal: be able to say one sentence — *"This breaks because X assumes Y, but Z violates that."*

## IV. Use AI as a Socratic Partner, Not a Code Generator
1. Ask it to explain unfamiliar functions, APIs, or conventions.
2. Ask it to poke holes in your fix, not write the fix itself.
3. You should always be doing the core reasoning yourself.

## V. Write the PR Description as a Teaching Doc
1. What was broken → why → what your fix does → how you tested it.
2. If you can't write this without staring at your own diff, go back and re-trace the code.

## VI. Revisit Merged PRs a Week Later
1. Re-read cold, like reviewing someone else's code.
2. If you can still explain every line, it's actually internalized.

## VII. Keep a Personal "Internals Notes" File
1. Short notes in your own words on architecture (e.g. Artist/Axes/Figure hierarchy, backend dispatch, transforms).
2. After 10–15 issues, this becomes your own working map of the codebase.

## VIII. Compounding Effect
1. Issue #1 might take a full weekend of tracing.
2. By issue #8–10 in the same subsystem, pattern recognition kicks in and things get faster naturally.