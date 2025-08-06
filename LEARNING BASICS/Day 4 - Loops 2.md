
# Find Element in an Array
```js
// find an Arry of Found Element
// If not print "-1"
function findElements(ar1, n) {
  let found = false;
  let result = [];
  for (let i = 0; i < ar1.length; i++) {
    if (ar1[i] === n) {
      result.push(i);
      found = true;
    }
  }
  if (!found) {
    console.log("-1");
    return;
  }
  console.log(result);
}
//----------------------------------------------------------------------------//
// Find Element and print index nubmer
// Else Print -1.
function findElement(ar1, n) {
  let found = false;
  for (let i = 0; i < ar1.length; i++) {
    if (ar1[i] === n) {
      return i;
    }
  }
  if (!found) {
    return "-1";
  }
}

let ar1 = [34, 45, 34, 6, 45, 75, 45, 73, 34, 2, 31];
let n = 1;

findElements(ar1, n);
let x = findElement(ar1, n);
console.log(x);

```

# Total no of negative numbers.
```js
// Find and Return total number of negative numbers in a array.
function findNeg(arry) {
  let tot = 0;
  for (let i = 0; i < arry.length; i++) {
    if (arry[i] < 0) {
      tot += 1; //This will itratively add up to the existing nubmer in tot.
    }
  }
  return tot;
}

let arry = [1, -4, 5, 4, 6, -4, 64, 34, -34, 32, 45, -23, 22, -34, 43];
let totNegs = findNeg(arry);
console.log(totNegs);

```

# Largest/Smallest Number in an Array
```js
// Find and Return largest of an Array

function findLarge(arry) {
  let large = 0;
  for (let i = 0; i < arry.length; i++) {
    if (arry[i] > large) { //just change to < for smallest nubmer
      large = arry[i];
    }
  } //After the loop completes it ruturns
  return large;
}

let arry = [-3, -2, -1, 0, 1, 2, 3, 4, 5, 10, -10];
let largestNumber = findLarge(arry);
console.log(largestNumber);
```
#### Realized that i cant use all Negative Numbers
```js
function findLarge(arry) {
  let large = arry[0]; //This will assumbe the first number as the largest number.
  for (let i = 0; i < arry.length; i++) {
    if (arry[i] > large) {
      large = arry[i];
    }
  } //After the loop completes it ruturns
  return large;
}

let arry = [-31, -1, -2, -12, -10];
let largestNumber = findLarge(arry);
console.log(largestNumber);
```
## But the Teacher prefers -infinity
```js
let large = -Infinity; //This will find the largest number 
```
