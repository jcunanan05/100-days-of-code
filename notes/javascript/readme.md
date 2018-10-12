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
