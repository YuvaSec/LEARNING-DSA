
# Second Largest Number in an Array
```js
function findSecLarge(arry) {
  let large = -Infinity;
  let secLarge = arry[0];

  for (let i = 0; i < arry.length; i++) {
    if (arry[i] > large) {
      secLarge = large; //will take the large
      large = arry[i]; //will take the current largest number
    }
  }
  return secLarge;
}

let arry = [-5, 5, 10, -10, 23, -343];
let secLargestNumber = findSecLarge(arry);
console.log(secLargestNumber);
```


# Realized a BUG during a test with [5,3,5] or [-5,3,-5]
- My code cannot detect "3" because
	- There is no larger number than "5" and the if condition did not run.
- SO i have added another if condition to check for second largest if it got stuck with -infinite.

```js
function findSecLarge(arry) {
  if (arry.length < 2) {
    return null;
  }
  let large = -Infinity;
  let secLarge = -Infinity;

  for (let i = 0; i < arry.length; i++) {
    if (arry[i] > large) {
      secLarge = large; //will take the large
      large = arry[i]; //will take the current largest number
    } else if (arry[i] > secLarge && arry[i] != large) {
      secLarge = arry[i];
    }
  }
  return secLarge;
}

//let arry = [-5, 5, 10, -10, 23, -343];
//Corner case
let arry = [5, 3, 5];
//let arry = [5, 5, 5]
// let arry = [-1, -5, -10]
// let arry = [10]

let secLargestNumber = findSecLarge(arry);
console.log(secLargestNumber);

```