In Node.js, the `fs` (File System) module provides an API for interacting with the file system. It allows you to perform various operations on files and directories, such as reading, writing, updating, deleting, and manipulating their metadata.

Here are some common functions provided by the `fs` module:

1. **Reading Files**:
   - `fs.readFile()`: Asynchronously reads the entire contents of a file.
   - `fs.readFileSync()`: Synchronously reads the entire contents of a file.

2. **Writing to Files**:
   - `fs.writeFile()`: Asynchronously writes data to a file, replacing the file if it already exists.
   - `fs.writeFileSync()`: Synchronously writes data to a file, replacing the file if it already exists.

3. **Appending to Files**:
   - `fs.appendFile()`: Asynchronously appends data to a file, creating the file if it does not exist.
   - `fs.appendFileSync()`: Synchronously appends data to a file, creating the file if it does not exist.

4. **File and Directory Operations**:
   - `fs.unlink()`: Asynchronously removes a file.
   - `fs.unlinkSync()`: Synchronously removes a file.
   - `fs.mkdir()`: Asynchronously creates a directory.
   - `fs.mkdirSync()`: Synchronously creates a directory.
   - `fs.readdir()`: Asynchronously reads the contents of a directory.
   - `fs.readdirSync()`: Synchronously reads the contents of a directory.

5. **File Metadata**:
   - `fs.stat()`: Asynchronously retrieves the `fs.Stats` object for a given path, providing information about the file or directory.
   - `fs.statSync()`: Synchronously retrieves the `fs.Stats` object for a given path.

6. **Renaming and Moving Files**:
   - `fs.rename()`: Asynchronously renames or moves a file or directory.
   - `fs.renameSync()`: Synchronously renames or moves a file or directory.

7. **Watching Files for Changes**:
   - `fs.watch()`: Watches for changes on a file or directory.
   - `fs.watchFile()`: Polls the file to detect changes.

These functions make the `fs` module essential for handling file system operations in Node.js applications, whether for reading configuration files, logging, data storage, or any other file-related tasks. It provides both synchronous and asynchronous methods to cater to different use cases, though asynchronous methods are generally preferred for non-blocking I/O operations in Node.js applications.


## Realtime Examples


1. **Reading Files**:
   ```javascript
   const fs = require('fs');

   // Asynchronously read contents of a file
   fs.readFile('example.txt', 'utf8', (err, data) => {
       if (err) throw err;
       console.log(data);
   });

   // Synchronously read contents of a file
   try {
       const data = fs.readFileSync('example.txt', 'utf8');
       console.log(data);
   } catch (err) {
       console.error(err);
   }
   ```

2. **Writing to Files**:
   ```javascript
   const fs = require('fs');

   // Asynchronously write data to a file
   fs.writeFile('example.txt', 'Hello, Node.js!', err => {
       if (err) throw err;
       console.log('Data written to file');
   });

   // Synchronously write data to a file
   try {
       fs.writeFileSync('example.txt', 'Hello, Node.js!');
       console.log('Data written to file');
   } catch (err) {
       console.error(err);
   }
   ```

3. **Appending to Files**:
   ```javascript
   const fs = require('fs');

   // Asynchronously append data to a file
   fs.appendFile('example.txt', '\nNew data appended', err => {
       if (err) throw err;
       console.log('Data appended to file');
   });

   // Synchronously append data to a file
   try {
       fs.appendFileSync('example.txt', '\nNew data appended');
       console.log('Data appended to file');
   } catch (err) {
       console.error(err);
   }
   ```

4. **File and Directory Operations**:
   ```javascript
   const fs = require('fs');

   // Asynchronously create a directory
   fs.mkdir('newDir', err => {
       if (err) throw err;
       console.log('Directory created');
   });

   // Synchronously remove a file
   try {
       fs.unlinkSync('toBeDeleted.txt');
       console.log('File deleted');
   } catch (err) {
       console.error(err);
   }

   // Asynchronously read contents of a directory
   fs.readdir('.', (err, files) => {
       if (err) throw err;
       console.log('Files in current directory:', files);
   });
   ```

5. **File Metadata**:
   ```javascript
   const fs = require('fs');

   // Asynchronously get file stats
   fs.stat('example.txt', (err, stats) => {
       if (err) throw err;
       console.log('File size:', stats.size);
       console.log('Is file:', stats.isFile());
       console.log('Is directory:', stats.isDirectory());
   });

   // Synchronously get file stats
   try {
       const stats = fs.statSync('example.txt');
       console.log('File size:', stats.size);
       console.log('Is file:', stats.isFile());
       console.log('Is directory:', stats.isDirectory());
   } catch (err) {
       console.error(err);
   }
   ```

6. **Watching Files for Changes**:
   ```javascript
   const fs = require('fs');

   // Watch for changes on a file
   fs.watch('example.txt', (eventType, filename) => {
       console.log(`File ${filename} changed:`, eventType);
   });

   // Watch for changes on a directory
   fs.watch('.', (eventType, filename) => {
       console.log(`File ${filename} changed:`, eventType);
   });
   ```
