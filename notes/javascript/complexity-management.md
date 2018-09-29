# Complexity Management

As your app grows, it grows more complex. So here are my notes in exploring this topic.

## Scaling your react redux app with re-ducks pattern

res: [https://medium.freecodecamp.org/scaling-your-redux-app-with-ducks-6115955638be]()

Complexity Management in React-Redux Summary

example:
[https://github.com/FortechRomania/react-redux-complete-example]()

summary:

1. Separate Views from state
   - React components are in a folder called views. State management is also in a separate folder called state.

2) Make views function-first and State feature-first
   - React components have shared component so it isn't wise to make a feature-first. Feature-first in state makes more sense along the way because you can put tests, containers, reducers, and all the code in the same folder.
