# `Array.reduce()`

Say we have this `reduce()` call:

```js
const result = [1, 2, 3].reduce((acc, el) => acc + el), 0);
```

On our first iteration, we are here in the array:

```js
[1, 2, 3]
 ^
```

`acc` starts with the value `0` (our initial value), and `el` will be `1`.

`(0, 1) => 0 + 1` - this returns `1` (note the lack of {}, it's an implicit return)

On our second iteration, we are here in the array:

```js
[1, 2, 3]
    ^
```

`acc` starts with the value `1` (the return value from the last iteration), and `el` is now `2`.

`(1, 2) => 1 + 2` - this returns `3`

On our third iteration, we are here in the array:

```js
[1, 2, 3]
       ^
```

`acc` has the value `3`, and `el` is also `3`.

`(3, 3) => 3 + 3` - this returns `6`.

We've now finished iterating through the array. Our callback has returned `6` on the final iteration, which is now the last value of `acc`. That gets passed up as the return value of the `.reduce()` call, and is assigned to our `result` variable.

So:

```js
const result = [1, 2, 3].reduce((acc, el) => acc + el), 0);
console.log(result); //prints 6
```
