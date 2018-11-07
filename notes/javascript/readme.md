# General javascript notes

Some notes that I don't know where to put yet.

## Clean code in express, nodeJS

Escape promise, callback hell with `async/await`

```js
const express = require("express");
const axios = require("axios");
const router = express.Router();

router.use("/api-call", async (_, res) => {
  const data = await axios.get("/some-url");
  res.send(data);
});
```

## Throttling User Input

### Stephen Grider's Modern react / redux

- There's a library called `Lodash` that can help throttling (_slowing down_) function exection.
  - It's called `debounce`
  - Stephen grider used it to slow down searching when the user types

- Callback strategy is a simple way to pass functions parent to children
