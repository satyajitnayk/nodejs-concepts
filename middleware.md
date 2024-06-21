Middleware functions in Node.js can execute code. 
Middleware functions are functions that have access to the request object (`req`), the response object (`res`), and the `next` function in the application's request-response cycle. 
They can perform various tasks, such as:

1. **Executing Code**: Middleware functions can execute code to manipulate request and response objects, perform authentication, logging, validation, or any other custom logic required by the application.

2. **Modifying Request and Response Objects**: They can modify the request (`req`) and response (`res`) objects. For example, adding properties to the request object, modifying headers, or sending a response.

3. **Ending the Request-Response Cycle**: Middleware functions can also end the request-response cycle by sending a response (`res.send()`, `res.json()`, etc.) or by calling `next()` to pass control to the next middleware function in the stack.

Here's a basic example of a middleware function in an Express.js application:

```javascript
const express = require('express');
const app = express();

// Example middleware function
app.use((req, res, next) => {
    // Execute code
    console.log('Middleware executed.');

    // Modify request object
    req.customProperty = 'Custom value';

    // Continue to the next middleware or route handler
    next();
});

// Route handler
app.get('/', (req, res) => {
    res.send('Hello World');
});

app.listen(3000, () => {
    console.log('Server is running on http://localhost:3000');
});
```

In this example:
- The middleware function `app.use()` is registered to run for all HTTP requests (`app.use((req, res, next) => { ... })`).
- Inside the middleware function, code can be executed (e.g., logging, modifying objects).
- The `next()` function is called to pass control to the next middleware function (`app.get('/', ...)`) or route handler (`app.get()`).
