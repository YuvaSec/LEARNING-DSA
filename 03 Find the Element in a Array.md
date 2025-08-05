
- This is my over kill version.
- This will need more processing 
- This will need more memory for storing another array 
- unnecessary complexity
```js
function findelement(arr, n) {
  //Created Empty Array to store true/false
  let newarr = [];

  //Create a for loop to itratively check for matches and update the Array above.
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] !== n) {
      //Pass false to the respective index
      // e.g = newarr[0] = false
      newarr[i] = false;
    } else {
      //Pass true if the above condition fails.
      newarr[i] = true;
    }
  }
  // This logic will fill the new array with boolean values.

  //-----------------------------------------//

  //Create a while loop to check if there is any "true" value in the Array newarr.
  let i = 0;
  while (newarr[i] == false) {
    i++;
  }
  //Here we check if there is a break in the while loop.
  if (i == newarr.length) {
    console.log(-1);
  }
  //if a break is found in the while loop
  //we itiratively check for the elemnent in the array using for loop.
  else {
    for (let i = 0; i < newarr.length; i++) {
      if (newarr[i]) {
        console.log(i); //retrun index value.
      }
    }
  }
}

let arr = [4, 23, 234, 24, 23, 14, 51, 15, 34, 33, 5, 51, 3, 51];
//Random Array with repeating numbers

let n = 51; // Element to be found.

findelement(arr, n);
//pass the n and Array arr values to the function

```

# REALIZATION.
*I wrote a much simpler version without complicating it after realizing what i wrote above has too many drawbacks.*
- actually here also i found few drawbacks 
	- result +=1 will cause string concatenation.
	- it works here because the array length is non zero.
	- but it is not stored in a array format.
```js
function findelement(arr, n) {
  //Created Empty Array to store matched elements
  let result = [];

  //This loop will check for matches.
  //Prints them and also stores them in a array.
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] == n) {
    //result += i; 
    result.push(i);
	 // Use `push()` to keep elements in an array `+=` just smashes things into a string.
    console.log(i); //prints index number.
    }
  }

  //This will check if the array is empty
  if (result.length == 0) {
    console.log("-1"); //if empty prints -1
  }
}

let arr = [4, 23, 234, 24, 23, 14, 51, 15, 34, 33, 5, 51, 3, 51];
//Random Array with repeating numbers

let n = 51; // Element to be found.

findelement(arr, n);
//pass the n and Array arr values to the function
```


# AGAIN REALIZED & TIME AND SPACE OPTIMIZED  
*But later realized that i don't even need the new array to verify.*
```js
function findelement(arr, n) {
  let found = false;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] == n) {
      console.log(i); //prints index number.
      found = true;
    }
  }
  if (!found) {
    //This will check if found is not true
    console.log("-1"); //if empty prints -1
  }
}
let arr = [4, 23, 234, 24, 23, 14, 51, 15, 34, 33, 5, 51, 3, 51];
let n = 51; // Element to be found.
findelement(arr, n);
```



# To Search for One Element
```js
// Find Element and print index nubmer
// Else Print -1.
function findElement(ar1, n) {
  let found = false;
  for (let i = 0; i < ar1.length; i++) {
    if (ar1[i] === n) {
      return i;
    }
  } // Here because it did not touch the return the program will run to the next step after finishing the loop!
  if (!found) {
    return "-1";
  }
}

let ar1 = [34, 45, 34, 6, 45, 75, 45, 73, 34, 2, 31];
let n = 1;
let x = findElement(ar1, n);
console.log(x);

```