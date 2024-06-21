In Node.js, the `os` module provides a way to interact with the operating system's information and functionalities. It allows you to access various system-related information such as CPU architecture, memory, network interfaces, operating system platform, and more.

Here are some common functionalities provided by the `os` module in Node.js:

1. **Platform Information**:
   - `os.platform()`: Returns the operating system platform (e.g., 'darwin', 'win32', 'linux').

2. **Operating System Release**:
   - `os.release()`: Returns the operating system release version.

3. **CPU Information**:
   - `os.cpus()`: Returns an array of objects containing information about each CPU/core, such as model, speed, and times (user, nice, sys, idle, etc.).

4. **Memory Information**:
   - `os.totalmem()`: Returns total system memory in bytes.
   - `os.freemem()`: Returns free system memory in bytes.

5. **Network Interfaces**:
   - `os.networkInterfaces()`: Returns an object containing network interfaces as properties, where each property is an array of network addresses.

6. **User Information**:
   - `os.userInfo()`: Returns information about the currently effective user, such as username, uid, gid, shell, and home directory.

7. **Hostname**:
   - `os.hostname()`: Returns the hostname of the operating system.

8. **Load Average**:
   - `os.loadavg()`: Returns an array containing the 1, 5, and 15 minute load averages.

9. **Temporary Directory**:
   - `os.tmpdir()`: Returns the operating system's default directory for temporary files.

10. **Endianness**:
    - `os.endianness()`: Returns the endianness of the CPU ('BE' for big endian or 'LE' for little endian).

These functions allow Node.js applications to gather and utilize system-level information, which can be useful for tasks such as system monitoring, performance optimization, environment-specific configurations, and more.

Here's a simple example demonstrating the usage of the `os` module to fetch and display basic system information:

```javascript
const os = require('os');

console.log('Platform:', os.platform());
console.log('Release:', os.release());
console.log('Total Memory:', os.totalmem() / (1024 * 1024 * 1024), 'GB');
console.log('Free Memory:', os.freemem() / (1024 * 1024 * 1024), 'GB');
console.log('CPU Information:');
const cpus = os.cpus();
cpus.forEach((cpu, index) => {
    console.log(`CPU ${index + 1}:`);
    console.log(`  Model: ${cpu.model}`);
    console.log(`  Speed: ${cpu.speed} MHz`);
});
console.log('Network Interfaces:', os.networkInterfaces());
console.log('User Info:', os.userInfo());
console.log('Hostname:', os.hostname());
console.log('Load Average:', os.loadavg());
console.log('Temporary Directory:', os.tmpdir());
console.log('Endianness:', os.endianness());
```

### Output

<img width="755" alt="image" src="https://github.com/satyajitnayk/nodejs-concepts/assets/32722867/872957d7-b0e8-4351-9bb5-65422a1d0ca7">

<img width="645" alt="image" src="https://github.com/satyajitnayk/nodejs-concepts/assets/32722867/d5585392-3519-4459-ae18-b78ed96f6f21">

