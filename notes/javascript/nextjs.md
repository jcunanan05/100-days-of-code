## Next JS notes

- The only special folder is pages folder.
- Link tag in next is like the react router
- You can put a button on a Link component - any component that has onClick
- withRouter includes router data on a component

### Route Masking

Route masking is arbitrary url links that points out to an original url

- `masked url` ---> `original url`

e.g. `<Link as={/`p/${props.id/`} href={/`/post?title=${props.title}/`}'} />`

- It is client-side by default.

- With node.js it can be client and server-side.

## Server-rendered components

- Server rendered components with ajax request can use the `getInitialProps` method from nextJS

## How to deploy to heroku

1. Check this [article](https://medim.com/@jacoboakley/deploy-a-next-js-app-on-heroku-69bcb01db1b7)

- Summary:
- Before pushing your changes to github, you must have a 'heroku-postbuild' script. Heroku runs this before deploying.
- Connect your github repo to heroku using heroku's dashboard

2. Check some next js [deployment examples](https://github.com/zeit/next.js/tree/3949c82bdfe268f841178979800aa8e71bbf412c/examples/custom-server-express)

## Lazy Loading

### Lazy Loading modules

- Use `await` to your modules

```javascript
// const firebase = require('firebase')
const firebase = await import("firebase");
```

- [further reading](https://nextjs.org/learn/excel/lazy-loading-modules/lazy-loading)

### Lazy Loading Components

- Use the next js _dynamic_ utility

```js
//import Highlight from 'react-highlight'
import dynamic from "next/dynamic";

const Highlight = dynamic(import("react-highlight"));
```

- [further reading](https://nextjs.org/learn/excel/lazy-loading-components/hello-dynamic-components)
