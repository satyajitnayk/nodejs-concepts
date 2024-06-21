In Node.js, global objects are objects that are available globally throughout the entire Node.js application. 
These objects provide core functionalities and utilities that are accessible without the need for explicit import statements in every module. 
They are part of the global scope in Node.js and can be accessed from any module within the application.

```shell
> global
<ref *1> Object [global] {
  global: [Circular *1],
  queueMicrotask: [Function: queueMicrotask],
  clearImmediate: [Function: clearImmediate],
  setImmediate: [Function: setImmediate] {
    [Symbol(nodejs.util.promisify.custom)]: [Getter]
  },
  structuredClone: [Function: structuredClone],
  clearInterval: [Function: clearInterval],
  clearTimeout: [Function: clearTimeout],
  setInterval: [Function: setInterval],
  setTimeout: [Function: setTimeout] {
    [Symbol(nodejs.util.promisify.custom)]: [Getter]
  },
  atob: [Function: atob],
  btoa: [Function: btoa],
  performance: Performance {
    nodeTiming: PerformanceNodeTiming {
      name: 'node',
      entryType: 'node',
      startTime: 0,
      duration: 2225.0270829200745,
      nodeStart: 32.32558298110962,
      v8Start: 50.347875118255615,
      bootstrapComplete: 94.29358291625977,
      environment: 74.60958290100098,
      loopStart: 112.08562517166138,
      loopExit: -1,
      idleTime: 2044.710832
    },
    timeOrigin: 1718983533887.083
  },
  fetch: [AsyncFunction: fetch]
}
```
