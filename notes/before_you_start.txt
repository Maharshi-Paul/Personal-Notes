Building genuine codebase fluency (step-by-step loop for every issue):

I. Read before touching code
    1. Find the function referenced in the issue, read it fully
    2. Trace callers (who uses this?) and callees (what does it depend on?)
    3. Check git log -p / blame on the file — past commits often explain why code is shaped that way
II. Reproduce the bug first
    1. Write a minimal script that triggers it
    2. If you can't reproduce it, you don't understand it yet — don't patch blind
III. Form and verify a hypothesis
    1. Use a debugger or targeted prints, not guess-and-check editing
    2. Goal: be able to say one sentence — "This breaks because X assumes Y, but Z violates that"
IV. Use AI as a Socratic partner, not a code generator
    1. Ask it to explain unfamiliar functions, APIs, or conventions
    2. Ask it to poke holes in your fix, not write the fix itself
    3. You should always be doing the core reasoning yourself
V. Write the PR description as a teaching doc
    1. What was broken → why → what your fix does → how you tested it
    2. If you can't write this without staring at your own diff, go back and re-trace the code
VI. Revisit merged PRs a week later
    1. Re-read cold, like reviewing someone else's code
    2. If you can still explain every line, it's actually internalized
VII. Keep a personal "internals notes" file
    1. Short notes in your own words on architecture (e.g. Artist/Axes/Figure hierarchy, backend dispatch, transforms)
    2. After 10-15 issues this becomes your own working map of the codebase
VIII. Compounding effect
    1. Issue #1 might take a full weekend of tracing
    2. By issue #8-10 in the same subsystem, pattern recognition kicks in and things get faster naturally