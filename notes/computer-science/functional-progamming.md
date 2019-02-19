# Functional-Light Programming

Course by Kyle Simpson in FrontendMasters

## Why FP?

- Makes code more declarative

- Imperative vs Declarative
  Imperative - Focused more on teaching computer what to do
  Declarative - Focused more on what you really want to do

- Proven - 100+ years of research
- Less to read

## Intro to FP

### Side Effects

- You can't make a program made up of pure functions.
- What you can do is, put code with side effects on one place. So if your program has a bug, you'll know first where to look.

### Purifying Functions concepts

- You need to balance side-effects and pure functions. You need to make tradeoffs
- If you really need side-effects, for performance or anything, enclose them in a pure wrapper.
