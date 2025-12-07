# Module System Notes

> Every file can be exported as a module and imported in another file using `require()` with a path.

Example:

```js
require("./mod1.js"); // import one module into another
require("./sum.js");

console.log("hello from app.js module");

var a = 10;
var b = 20;

sum(a, b); // this won't work because sum is not defined in this file
```

Why?  
We **cannot access functions or variables from one module to another** just by using a `require` statement.  
**Modules are protected by default** to avoid functions leaking into the global scope.

---

## How to use the function? → `exports` and `module.exports`

### CJS (CommonJS Modules)

- Uses **require()**, **module.exports**, **exports**
- Works in **sync** and **non-strict** mode by default

Example:

**sum.js**

```js
function sum(a, b) {
  console.log(a + b);
}
module.exports = sum;
```

**app.js**

```js
const sum = require("./sum.js");
sum(10, 20);
```

Now it works because you required the exported module.

---

## ES Modules (MJS)

- Uses **import/export**
- Works in **async** and **strict** mode
- Needs `"type": "module"` in `package.json`

`package.json`:

```json
{
  "type": "module"
}
```

**sum.js**

```js
export function sum(a, b) {
  console.log(a + b);
}
```

**app.js**

```js
import { x, sum } from "./sum.js"; // ES6 module import
```

---

## Grouping Multiple Modules

To combine multiple modules into one:

1. Create a folder
2. Put all the modules inside
3. Create an `index.js` file inside that folder

**calculate/index.js**

```js
const { sum } = require("./sum");
const { multiply } = require("./multiply");

module.exports = { sum, multiply };
```

Now import in `app.js` as:

```js
const { sum, x, multiply } = require("./calculate");
// index.js file auto-loads
```
