# Diving into the Node.js GitHub Repository

- Every module, behind the scenes, is wrapped inside a function.\
  That's why even without exporting, variables remain scoped to the
  module.

- Example usage of `require`:

  ```js
  // require("./path")
  ```

- The function that Node.js creates for each module is an **IIFE**
  (Immediately Invoked Function Expression).

- **IIFE**: A function that gets invoked as soon as it is created.

### This is how Node.js internally wraps a module:

```js
(function () {
  // All code of the module goes here
})();
```
