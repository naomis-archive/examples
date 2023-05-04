# Recursion

Given this code:

```js
function sum(arr, n) {
  if (n <= 0) {
    return 0;
  }
  return sum(arr, n - 1) + arr[n - 1];
}
```

The `return 0` portion is the "base case". A recursive function needs to have a base case, or it will continue on for infinity (or until the browser crashes).

In order to understand recursion, we need to understand the call stack. As each function call gets generated, it is added to the stack. When the function calls end (because the base case is reached), the stack begins resolving. This happens in a "First-In-Last-Out" basis, or in the reverse direction of the call order.

If we break this down visually... Let's create an array called `myArray` and call our function on it with an `n` value of 3.

```js
var myArray = [1, 2, 3, 4, 5];
sum(myArray, 3);
```

This function call will give us the sum of the first 3 elements in the array. But what does that look like?

```js
sum(myArray, 3); // returns another function call plus arr[n-1]
sum(myArray, 2) + myArray[3 - 1]; // returns another function call, but now n is 2
sum(myArray, 1) + myArray[3 - 1] + myArray[2 - 1]; // keep going...
sum(myArray, 0) + myArray[3 - 1] + myArray[2 - 1] + myArray[1 - 1]; // now n is 0.
//with n being 0, our base case is reached. The stack begins resolving here.
0 + myArray[3 - 1] + myArray[2 - 1] + myArray[1 - 1];
0 + myArray[2] + myArray[1] + myArray[0];
0 + 3 + 2 + 1;
6; //this is the final result of our function call
```
