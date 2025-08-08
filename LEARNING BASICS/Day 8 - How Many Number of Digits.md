# Using WhileLoop to Find how many digits.
```js 
function howMany(arry) {
  for (let i = 0; i < arry.length; i++) {
    let num = arry[i];
    let counter = 0;
    // CHECKS IF NUMBER IS 0 //
    if (arry[i] == 0) {
	counter = 1
	}
	// CHECKS IF NUMBER IS LESS THAN 0 //
    if (num < 0) {
      num = num * -1;
    }
    // COUNTS TOTAL NUMBER OF DIGITS //
    while (num > 0) {
      num = Math.floor(num / 10);
      counter++;
    }
    // PRINTS TOTAL NUMBER OF PASSES. //
    console.log(counter);
  }
}

let arry = [0, 10, 100, 101, 123, -1, -123];
howMany(arry);
```

# MATH.ROUND
```js
MATH.ROUND //ROUNDS TO CLOSEST (PROXIMITY)
```
# MATH.FLOOR
```js
MATH.FLOOR //ROUNDS DOWN TO THE LOWER VALUE. (TRUNKATING)
```

# MATH.CEIL
```js
MATH.CEIL //ROUNDS UP TO THE HIGHER VALUE (EXPANDING)
```


# REVISING TO CHECK FOR NEGATIVE NUBMER USING INBUILT FUNCTION
```js
function howMany(arry) {
  for (let i = 0; i < arry.length; i++) {
    let num = arry[i];
    let counter = 0;
    // CHECKS IF NUMBER IS 0 //
    if (arry[i] == 0) {
	counter = 1
	}
	// CHECKS IF NUMBER IS LESS THAN 0 //
    num = Math.abs(num);
    // COUNTS TOTAL NUMBER OF DIGITS //
    while (num > 0) {
      num = Math.floor(num / 10);
      counter++;
    }
    // PRINTS TOTAL NUMBER OF PASSES. //
    console.log(counter);
  }
}

let arry = [0, 10, 100, 101, 123, -1, -123];
howMany(arry);
```

# MATH.ABS
```js
MATH.ABS // CONVERTS NEGATIVE NUMBERS TO POSITIVE //
```