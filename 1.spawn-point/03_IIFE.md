> Diving into Node.js github repo

- Every module behind the scene wraps inside one function thats why without export you can access the variables

-// require("./path")

- the function which gets created is a function(IIFE)
- IIFE Immediately Invoked Function Expression.
- Function gets invoked as soon as it is created

(function () {

// All code of the module gets here

})();
