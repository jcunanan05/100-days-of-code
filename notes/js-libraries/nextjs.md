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
