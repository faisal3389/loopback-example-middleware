#loopback-faq-middleware
```
git clone git@github.com:strongloop/loopback-faq-middleware.git
cd loopback-faq-middleware
npm install
slc run
```

- [How do you serve static content via static middleware?](https://github.com/strongloop/loopback-faq-middleware#how-do-you-serve-static-content-via-static-middleware)

#How do you serve static content via static middleware?
1. Add static middleware to the [files property](https://github.com/strongloop/loopback-faq-middleware/blob/master/server/middleware.json#L17-L19) in middleware.json
2. Delete [`server/boot/root.js`](https://github.com/strongloop/loopback-faq-middleware/blob/master/server/boot).
3. Create [`client/index.html`](https://github.com/strongloop/loopback-faq-middleware/blob/master/client/index.html)
4. Start the server via `slc run` and browse to [`localhost:3000`](http://localhost:3000). You should see `hello world` being served.


#How do you create a custom error message for all errors?
1. Create a [single function](https://github.com/strongloop/loopback-faq-middleware/blob/master/server/server.js#L33-l41) that all errors are passed to.
2. Set [`app.get('remoting').errorHandler`](https://github.com/strongloop/loopback-faq-middleware/blob/master/server/server.js#L23-l31) to call a custom error handler.
3. Create a [`custom error middleware`](https://github.com/strongloop/loopback-faq-middleware/blob/master/server/middleware/custom-error.js) to handle errors not thrown by the `loopback.rest()` middleware.
