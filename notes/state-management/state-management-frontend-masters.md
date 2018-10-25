# Summary / High Order takeaways

## Mobx vs Redux

They are not battle of frameworks, they are patterns on a framework called Dependency Graphs vs Immutable state trees

## Dependency Graphs

### Advantages

- Easy to update
- Nodes can talk to each other
- Actions are simpler and colocated with data
- reference by identity

### Disadvantages

- Hard to track changes
- Hard to redo / undo
- Hard to serialize data

## Immutable state tree

### Advantages

- Snapshots are cheap and easy - because it lives on a 1 tree only
- Easy to redo / undo
- You can serialize the whole tree
- Reference by data

## Normalizing data

You don't wanna filter an array of objects again and again. That's why we assign keys to them.

## When to use?

Depends on what tradeoffs you're willing to take. But Good news, You can use both.
