A transform stream in Node.js is a type of stream that is both readable and writable, but it also introduces an additional feature: data transformation. Unlike duplex streams, which pass data through without modification, transform streams allow you to modify or transform the data as it is being read or written.

### Key Characteristics of Transform Streams:

1. **Readable and Writable**:
   - Like duplex streams, transform streams can be both read from (`_read()` method) and written to (`_write()` method).

2. **Data Transformation**:
   - Transform streams include an additional method called `_transform(chunk, encoding, callback)` where you can modify or transform the data chunk before pushing it downstream or passing it to the next stream in the pipeline.

3. **Efficiency**:
   - Transform streams are designed to efficiently handle data transformation operations, making them ideal for tasks such as compression, encryption, decompression, or parsing data formats like JSON or CSV.

4. **Backpressure Handling**:
   - Similar to other types of streams in Node.js, transform streams handle backpressure automatically to ensure that data is processed at an appropriate rate, preventing memory overload when consumers are slower than producers.

### Example of a Transform Stream:

Here’s a simplified example of a transform stream that converts text to uppercase:

```javascript
const { Transform } = require('stream');

class UpperCaseTransform extends Transform {
    _transform(chunk, encoding, callback) {
        const transformedChunk = chunk.toString().toUpperCase();
        this.push(transformedChunk);
        callback();
    }
}

// Usage of the custom transform stream
const upperCaseTransform = new UpperCaseTransform();

upperCaseTransform.on('data', chunk => {
    console.log('Transformed chunk:', chunk.toString());
});

upperCaseTransform.write('hello\n');
upperCaseTransform.write('world\n');

upperCaseTransform.end();
```

### Output

```shell
Transformed chunk: HELLO

Transformed chunk: WORLD
```

### Explanation:

- **Custom Transform Stream (`UpperCaseTransform`)**:
  - Extends `Transform` from the Node.js `stream` module and overrides the `_transform()` method.
  - `_transform()` method receives chunks of data (`chunk`), transforms it to uppercase (`chunk.toString().toUpperCase()`), and pushes the transformed data downstream using `this.push()`.
  - Calls `callback()` to indicate the completion of the transformation operation.

- **Usage**:
  - Creates an instance of `UpperCaseTransform`.
  - Listens for `'data'` events to consume transformed chunks of data.
  - Writes data (`'hello\n'` and `'world\n'`) to the transform stream using `write()` method.
  - Ends the stream with `end()` method to signal no more data will be written.

In this example, `UpperCaseTransform` demonstrates a simple use case where incoming text data is transformed to uppercase before being passed downstream. Transform streams are versatile and can be customized to perform various types of data manipulation or processing as needed in Node.js applications.
