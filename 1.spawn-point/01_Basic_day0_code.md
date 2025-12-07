# Node REPL (Read--Evaluate--Print Loop)

To enter REPL mode, open **CMD** and type:

    node

You will see:

    Welcome to Node.js v24.11.1.
    Type ".help" for more information.

## Basic REPL Usage

    > 1 + 1
    2

    > var o = "rudra"
    undefined

    > o
    'rudra'

---

# Node.js Overview

**Node.js is a JavaScript runtime environment**\
It allows JavaScript to run outside the browser using the **V8 engine**
plus additional Node APIs.

---

# The `global` Object in Node.js

Using:

```js
console.log(global);
```

Outputs something like:

    <ref *1> Object [global] {
      global: [Circular *1],
      clearImmediate: [Function: clearImmediate],
      setImmediate: [Function: setImmediate] {
        Symbol(nodejs.util.promisify.custom): [Getter]
      },
      clearInterval: [Function: clearInterval],
      clearTimeout: [Function: clearTimeout],
      setInterval: [Function: setInterval],
      setTimeout: [Function: setTimeout] {
        Symbol(nodejs.util.promisify.custom): [Getter]
      },
      queueMicrotask: [Function: queueMicrotask],
      structuredClone: [Function: structuredClone],
      atob: [Function: atob],
      btoa: [Function: btoa],
      performance: [Getter/Setter],
      fetch: [Function: fetch],
      crypto: [Getter],
      navigator: [Getter]
    }

### Key Notes

- `global` is **not part of the V8 engine**.
- It is a **Node.js-specific** global object.

---

# `this` in Node.js

```js
console.log(this);
```

prints:

    {}

In Node.js (outside modules), `this` is an empty object --- not the
global object.

---

# Global Object Comparison (Browser vs Node)

In browsers:

- `window`
- `this`
- `self`
- `frames`

All point to the **global object**.

This inconsistency caused confusion across JS runtimes (Node, browsers,
Deno, Bun, etc.).

To standardize this, JavaScript introduced:

# `globalThis`

A **unified global object** across all JavaScript environments:

- Works in **Node.js**
- Works in **browsers**
- Works in **Web Workers**, **Deno**, **Bun**, etc.
