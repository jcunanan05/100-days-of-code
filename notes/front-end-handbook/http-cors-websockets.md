## HTTP Networks / CORS, Websockets

### An overview of HTTP

res: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview]()

- Protocol which allows fetching of resources, like JPG, HTML, CSS, JS
- Foundation of any data exchange on the web, and on client-server protocol

#### Client Server communication

- By exchanging individual messages
- Client - usually web browsers
- Client messages are called **requests**
- Server answers are called **responses**
- Messages sent over TCP or over TLS encrypted TCP
- Fetches hypertext documents, images, videos, post content (forms)
  *some diagram*
  ![client server exchange diagram](https://mdn.mozillademos.org/files/13673/HTTP%20&%20layers.png)

### Overview of HTTP Status codes

res: [https://webdesign.tutsplus.com/tutorials/http-status-codes-in-60-seconds--cms-24317]()

1. 1xx - gives info while connection is still in progress

- 100: continue

2. 2xx - Connection has been made

- 200: OK
- 201: Created
- 204: No content

3. 3xx - redirection

- 301: Moved Permanently
- 307: Temporary redirect

4. 4xx - client-side errors

- 401: Unauthorized
- 403: Forbidden
- 404: Not found

5. 5xx - server-side errors

- 500: Internal server error
- 503: Service Unavailable

### CORS wiki

res: [https://en.wikipedia.org/wiki/Cross-origin_resource_sharing]()

- Mechanism that allows restricted resources outside of your domain
- By default, cross-domain AJAX requests are forbidden
- Enforced by the Security policy called _**same-origin security policy**_

### CORS by the W3C standards

res: [https://www.w3.org/TR/cors/]()

- Allows client-side cross-origin requests (or requests from other domains)
- The server-side app enforces the limitations via the `Access-Control-Allow-Origin` header response
- The server-side app can also set different restrictions of how long, what requests only, what sites can only access the resource, example:

```
  Access-Control-Allow-Origin: http://hello-world.example
  Access-Control-Max-Age: 3628800
  Access-Control-Allow-Methods: PUT, DELETE
```

### MDN CORS

res: [https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS]()

#### Simple requests

- Requests that doesn't trigger CORS preflight
- Methods Allowed:
  - GET
  - HEAD
  - POST

#### Preflighted requests

- There's an initial request to know if it's safe to send.
- Preflight requests send an HTTP requests firsts by putting `OPTIONS` method
- Other methods that triggers preflight:
  - `PUT`
  - `DELETE`
  - `CONNECT`
  - `OPTIONS`
  - `TRACE`
  - `PATCH`

### Websockets wiki

res: [https://en.wikipedia.org/wiki/WebSocket]()

- Is a computer communications protocol over TCP
- Different protocol than _HTTP_, but is designed to work on ports 80 and 443
- Facilitates real-time data transfer from and to server

### Websockets with tuts

res: [https://code.tutsplus.com/courses/connect-the-web-with-websockets]()

- two-way communication sessions between browser and server
- with websockets, you can receive updates without having to ask the server for updates
- popular library: [https://socket.io]()
- Persistent connection. You only connect once
- Best for systems needing real-time data ex. _chat application_
