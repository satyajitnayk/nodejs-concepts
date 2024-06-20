Node.js supports several types of API functions that developers commonly use to interact with different aspects of the runtime environment, perform I/O operations, and manage asynchronous tasks. Here are some key types of API functions supported by Node.js:

1. **File System (fs) API**:
   - Node.js provides a comprehensive set of functions through the `fs` module to perform file system operations such as reading from and writing to files, creating directories, and managing file permissions. Examples include `fs.readFile`, `fs.writeFile`, `fs.readdir`, and `fs.stat`.

2. **HTTP and HTTPS API**:
   - Node.js includes built-in modules (`http` and `https`) for creating HTTP and HTTPS servers and making HTTP/HTTPS requests. Developers can use functions like `http.createServer`, `http.request`, `https.createServer`, and `https.request` to handle incoming HTTP requests and make outbound HTTP requests.

3. **Network Communication (Net) API**:
   - The `net` module in Node.js provides functions for creating TCP servers (`net.createServer`) and TCP clients (`net.createConnection`). It allows developers to establish low-level network connections, handle incoming connections, and manage data streams over TCP.

4. **Operating System Utilities (os) API**:
   - Node.js exposes operating system-related functionalities through the `os` module. Developers can use functions like `os.platform`, `os.totalmem`, `os.cpus`, and `os.hostname` to retrieve information about the operating system, system resources, and environment variables.

5. **Path API**:
   - The `path` module in Node.js provides functions for working with file and directory paths in a platform-independent manner. Functions such as `path.join`, `path.resolve`, and `path.basename` are used to manipulate and construct paths based on the operating system's conventions.

6. **Process API**:
   - Node.js provides the `process` global object, which contains functions and properties related to the current Node.js process. Developers can use functions like `process.argv`, `process.exit`, `process.cwd`, and `process.env` to access command-line arguments, terminate the process, retrieve the current working directory, and manage environment variables.

7. **Buffer API**:
   - Node.js includes the `Buffer` class for working with binary data directly. Developers can create buffers, manipulate buffer contents, and convert buffers to and from strings or other data types using functions like `Buffer.from`, `buf.toString`, `buf.slice`, and `Buffer.concat`.

These are just a few examples of the types of API functions supported by Node.js. Each module in Node.js typically provides a specific set of functions tailored to a particular area of functionality, making it versatile for building a wide range of applications, from simple scripts to complex server-side applications.
