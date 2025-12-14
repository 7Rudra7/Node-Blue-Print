- JS is a synchronous single threaded language

- Node.js has an event-driven architecture capable of asynchronous I/O

- JS knows how to execute code in a synchronous way

- JS doesn’t know how to wait

> **libuv**

> libuv is async I/O made simple.

> **Question:** Then how does JS read a file, take data from DB, fetch API response, or wait for a timer?
>
> **Answer:** Node gives the superpowers 😆 to do all this. At the ground level, Node.js uses the library **libuv** with the help of the OS.

```
V8  →  libuv  →  OS (File, WWW, DB, Timer)
```
