# Mobx

Mobx uses the concept of decorators / observables. And in the tutorial, steve also uses getters and setters.

- Getters and setters - a way to fix inconsistensies.
- decorators - design pattern, provide a syntatictic sugar for a HOF (Higher-Order Functions)
- observables - a way to know that something's changed.

## Major Concepts

- Observable State - State / data that is being watched for changes
- Actions - anything that changes the state
- Derivations
  - Computed Properties - Combined properties from the state that will only change if one of they're watching changes
  - Reactions - Side effects from changed state.

### Tips

- You can sometimes omit `@action` annotation, but it is recommended to be used.
- You can pass most common data structures to mobx observables. (Objects, Arrays, Maps)

#### What is a `Map`?

Slightly more flexible version of objects

> Caution: If you add properties to an object after passing it to an observable, that won't be observed. Use a `Map` instead.

## Mobx with React

### Hooking up Mobx with react

1. You need the `<Provider>` Component from `mobx-react` package
2. To have a reactive component, use `@observable`
3. To inject methods on a component, use `@inject`

#### Examples on a class component

```js
// observer
@observer
class Counter extends Component {
  render() {
    return (
      <section>
        <h1>Count: {counter.count}  h1>
        <button onClick={counter.increment}>Increment</button>
        <button onClick={counter.decrement}>Decrement</button>
        <button onClick={counter.reset}>Reset</button>
      </section>
    );
  }
}
```

injecting

```js
@inject('itemStore')
class NewItem extends Component {
  state = { ... };
  handleChange = (event)    { ... }
  handleSubmit = (event)    { ... }
  render() { ... }
}
```

#### examples on a functional component

With inject and observe

```js
const UnpackedItems = inject('itemStore')(
  observer(({ itemStore }) => (
    <Items
      title="Unpacked Items"
      items={itemStore.filteredUnpackedItems}
      total={itemStore.unpackedItemsLength}
    >
      <Filter
        value={itemStore.unpackedItemsFilter}
        onChange={itemStore.updateUnpackedItemsFilter}
      />
    </Items>
  ))
);
```

## Handling Async?

You can just `await` a network request and fire the action when if it succeeded.
