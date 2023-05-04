# `return`

Functions declared with the `function` keyword need a `return` statement to return a value.

```js
function myFunction() {
  return "value";
}
```

`myFunction()` would return the string `value`.

```js
function myConditional(number) {
  if (number > 10) {
    return "Greater than 10";
  }
  if (number < 5) {
    return "Less than 5";
  }
}
```

`myConditional(15)` would return the string `Greater than 10`. `myConditional(3)` would return the string `Less than 5`.

BUT `myConditional(7)` would return `undefined`. This is because the function doesn't have a `return` statement for the case where `number` is between 5 and 10. If a function doesn't have a `return` statement, it returns `undefined`.

You can return anything you want from a function... An object?

```js
function returnAnObject() {
  return {
    name: "Naomi",
  };
}
```

Another **function**?!?!

```js
function returnAFunction() {
  return function hi() {
    return "hi";
  };
}
```

Arrow functions can also have a `return` statement.

```js
const myArrowFunction = () => {
  return "Hello!";
};
```

However, arrow functions can also _implicitly_ return a value. To do this, the function **cannot** use curly braces to declare its block scope.

```js
const myImplicitFunction = () => "Hello!";
```

`myImplicitFunction` and `myArrowFunction` do the exact same thing. Implicit returns can _also_ return objects, but you must wrap the object in parentheses - otherwise JavaScript parses it as the function body.

```js
const myImplicitObjectFunction () => ({
    name: "Naomi"
})
```

Implicit returns are helpful for things like callback functions, but they can be confusing to read. If you're not sure what's going on, it's better to use a regular function with a `return` statement.
