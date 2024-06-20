### Callback Function (Original)

```javascript
function getData(callback) {
    setTimeout(() => {
        const data = 'Some data';
        callback(null, data); // Pass null for error and data for success
    }, 1000);
}
```

### Async/Await Conversion (With Callback Pattern)

```javascript
function getDataAsync() {
    return new Promise((resolve, reject) => {
        getData((err, data) => {
            if (err) {
                reject(err);
            } else {
                resolve(data);
            }
        });
    });
}

async function fetchData() {
    try {
        const data = await getDataAsync();
        console.log('Data received:', data);
        // Further operations with 'data' can be done here
    } catch (error) {
        console.error('Error fetching data:', error);
    }
}

// Call the fetchData function to use async/await
fetchData();
```

### Explanation

1. **Promise Wrapper (`getDataAsync`)**: Here, `getDataAsync` wraps the original callback-style function (`getData`) into a Promise. Inside `getDataAsync`, `getData` is called with a callback function that handles both success (`data` received) and failure (`err` received).

2. **Async Function (`fetchData`)**: This async function `fetchData` uses `await` to wait for the Promise returned by `getDataAsync` to resolve. It then proceeds to log the received data and handle any errors that might occur during the asynchronous operation.

This conversion maintains the callback-style interface for `getData`, allowing you to integrate it seamlessly with existing callback-based code while utilizing the benefits of async/await for cleaner asynchronous control flow.
